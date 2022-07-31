# text expanders

Text expanders are programs which allow OS-wide macros.
espanso is a FOSS cross-platform expansion manager.

## espanso

### config files

espanso config files are YAML flies.
The basic unit of espanso is the match.
Matches are contained in an espanso config file in the array matches.
the default config file is `default.yml`
Espanso allows breaking up its config into multiple files.

#### multiple component configs

Any component config file of espanso should have a top level `name` key.
In a component config file, `parent: default` merges it into the generic config 'namespace'

##### app-specific config

To apply certain config files to only certain apps, use app-specific configurations.
App-specific configurations use one of three top-level config keys {`filter_title`, `filter_exec`, `filter_class`}
Any app-specific config key takes a string or regex and addtionally allow the vertical bar to provide a list of applications
To help detect the filter_whatever, expanso comes with the command line util espanso detect

table:key|function|platform
filter_title|current window title|win, mac (uses app identifier), linux
filter_exe|application's executable path. For example, C:\Programs\Telegram.exe|win, mac, linux kinda
filter_class|window class|only usefully linux

### global config

the global config key auto_restart specfies whether espanso should restart on config change
the global config key backend specfies how the insertion takes place and takes the values {Clipboard, Inject, Auto}


table:backend|function
Clipboard|works like pasting
Inject|works like keypresses
Auto|linux only autochoosing

### match structure

#### basics

The main two fields of an espanso match are `replace` and `trigger`.
`trigger` represents the thing that will be replaced by `replace`.
when you have multiple triggers, pass an array to `trigger⁑s⁑`
Within `replace` one can determine the cursor position after via `$|$`

#### other match related properties

If you specify `word: true` on  a match, it will only match if surrounded by word boundaries.
The propagate_case property of a match will match on and preserve any case, so that "alh" will expand to "although", "Alh" will expand to "Although" and "ALH" will expand to "ALTHOUGH"

#### image matches

Image matches have an `image_path` instead of a `replace`.

#### vars

the vars array of a match contains vars for that match.
Each var has at least a key `name` identifying it and a key `type` indicating the type of variable.
One can refer to any var within `replace` by `{{‹name›}}`
Any further specification of an espanso variable goes into the `params` key.

##### globals

global variables may be specified within the `global_vars` sequence of the `default.yml`.
global vars can just be referred to as any other variable without mentioning them in `vars`, however they are evaluated before local variables. To make them evaluate at a specific point, there is the type `global`

```
global_vars:
  - name: "reversed"
    type: shell
    params:
      cmd: "echo $ESPANSO_VARNAME | rev"

matches:
  - trigger: ":rev"
    replace: "{{reversed}}"
    vars:
      - name: "varname"
        type: echo
        params:
          echo: "hello"
      - name: "reversed"
        type: "global
```

##### date

The `date` type for espanso allows outputting formatted datetimes using rust's chrono as the backend.
`params.format` for espanso's `date` type takes a format string

##### script

The `script` type for espanso allows running external scripts (i.e. in languages that are not shell)
`params.args` for `script` espanso variables is a sequence of the programming language executable and the path to the script

```
- trigger: ":pyscript"
  replace: "{{output}}"
  vars:
    - name: output
      type: script
      params:
        args:
          - python
          - /path/to/your/script.py
```

##### shell

The `script` type for espanso allows running cli commands.

params.cmd|the command
params.shell|which shell to use
params.trim|trim the shell output of newlines
debug|populate espanso's log file

```
- trigger: ":ip"
  replace: "{{output}}"
  vars:
    - name: output
      type: shell
      params:
        cmd: "curl 'https://api.ipify.org'"
        debug: false
        trim: false
        shell: bash
```

###### env vars

⟮Espanso variables⟯ are made available in the ⟮environment⟯ of the `shell` type. 
$CONFIG|the path of the config file
$ESPANSO_FOO|A `var` with name foo
$ESPANSO_FOO_BAR|A field of a form foo with name bar


```
lang=yaml;
- trigger: ":reversed"
  replace: "Reversed {{myshell}}"
  vars:
    - name: mytime
      type: date
      params:
        format: "\%H:\%M"
    - name: myshell
      type: shell
      params:
        cmd: "echo $ESPANSO_MYTIME | rev"
```

##### random

to ⟮insert a random choice of different options⟯ use the type ⟮random⟯, ⟮the options⟯ are specified ⟮in the choices sequence of params⟯ 
```
  - trigger: ":quote"
    replace: "{{output}}"
    vars:
      - name: output
        type: random
        params:
          choices:
            - "Every moment is a fresh beginning."
            - "Everything you can imagine is real."
            - "Whatever you do, do it well."
```

#### forms

When using espanso forms, ctrl (yes, really) enter to submit on mac.
When using forms, instead of using `replace`, we instead use `form`.
Espanso's `form` key includes a string with blanks signified by the usual {{‹name›}} syntax
Espanso allows customization of its form fields via the `form_fields` mapping.
The `form_fields` mapping can have a key for each blank in the form, I will be calling each of these a field specifier.

##### field specifiers

field specifiers, similar to vars, take a `type`.


table:field specifier `type`|function
text|text only
choice|dropdown menu
list|list box

any field specifier that allows multiple choices takes these choices as a `choices` array

using espanso, I've created an expansion that uses `!!!` to run an arbitrary shell command and insert the results

### caveats

espanso does not source any of the usual files and so doesn't get any environment variables.
espanso also doesn't seem to set any LANG or LC variables, which may cause some issues.