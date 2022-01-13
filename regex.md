# regex

regex ::= [^|\A]<expression>[$|\Z]
expression ::= <alternative>{|<alternative>}
alternative ::= {<quantified>|<q-e-escape-sequence>}
quantified ::= <quantifiable>[<quantifier>]
quantifiable ::= <character-class>|<group>|<character>|<reference>|<recursion-token>

| marks alternation, where one alternative must match

## the regex engine

In general, the regex engine proceeds from left to right through the regex, matching the next token in the regex to the next token in the string.
The regex engine always returns the first (leftmost) string that matches all our constraints (though of course that is also the longest match e.g. if our quantifiers are greedy).

### backtracking

As the regex goes through the regex, it inserts a backtracking position at any point in the regex/string where it could have tried to match differently.
If a regex tries a certain match, and this fails at some point, it backtracks.
Backtracking is when regex goes to the last backtracking position and tries a different alternative.

### zero length

In regex, some things, e.g. assertions as well as some quantifiers allow matching things of zero length. These are known as zero-length matches.
Some flavors of regex always skip zero-legnth matches = don't return zero-length matches.
When a regex engine can find multiple zero-length matches at the same position, it could concievably get stuck there forever.
To prevent the regex engine from getting stuck matching zero-length matches at the same position until the heat death of the universe, there are two strategies: Either attempt the next match one character after the end of the previous match, or start the next match at the same position, but make note of the fact that the previous match was zero-length, and forces the thing to give up its zero-length match if it tries to match the same zero-length position agaoin.

## regex syntax

### characters

a literal character matches/represents itself (unless it is a metacharacter in that position, in which case it needs to be esxaped)
The . character matches all characters (including newlines if the dotall flag is enabled, excluding newlines otherwise)
It is often more sensible to use a negated character class instead of .
The sequence q-e-escape-sequence ::= \Q{<character>}\E forces everything within to be treated as literal and not as metacharacters

### character class

A character class matches exactly one of several characters.
There built-in character classes, or you may specify one with a character class literal.
The character class literal may begin with ^ which matches any one character that is not the specified character
Within the character class literal, <character>-<character> matches a range (if semantically sensible)
character-class ::= (\<built-in-character-class-character>)|<character-class-literal>|<escape-character-classes>
character-class-literal ::= \[[^]<character>{<character>}\] # slight simplification
built-in-character-class-character|meaning/equivalent character class literal
d|[0-9]
D|[^0-9]
w|[A-Za-zO-9_]
W|[^A-Za-zO-9_]
s|any number of different space characters
S|^any number of different space characters
X|a single unicode codepoint

Whether built-in character classes such as \d and \w match non-ASCII characters/numbers depends on the regex flavor.

Character classes that contain a built-in character class and its negation match everything, and are sometimes used when dotall is not available.

There are a special kind of character class called a posix bracket expression, which has the syntax [:<name>:]
In many langauges \p{} is a character class that takes an argument of a certain unicode category matches all relevant unicode characters. Java uses the same type of notation for posix bracket expressions 

### group

a group allows an expression to be acted upon.
Capturing stores a matched string for further use.
Atomic groups throw away all backtracking positions within the group once the regex engine has exited the group.
Groups may be capturing or noncapturing.
By default, capturing groups are numbered starting at 1, counting opening parentheses.
Capturing groups are often limited to 99 per regex.
As an alternative to numbered capturing groups, capturing groups may also be named.
Mixing numbered and named capture groups is not recommended, as it is inconsistent between flavors whether named capture groups will consume a number or not.
group-specifier|meaning
ø|capturing
?:|non-capturing
?>|atomic
?<expression>|conditional group
?bar|branch reset groups
?<flags>|activates certain flags from within a regex
group ::= \(<group-specifier><expression>\)

#### lookaround assertions

lookaround assertions live in groups that are non-capturing and atomic by default (and unalterably so)
the four lookaround assertions are assertions testing whether the environment before or after the string is a certain way.
lookaround assertions may be lookahead (after the current positon) or lookbehind (before the current position)
lookaround assertions may be positive (true if it is the case) or negative (true if it is not the case)
=|positive
!|negative
ø|ahead
<|behind

lookassertion-specifier ::= ?<behind-ahead><positive-negative>
behind-ahead ::= <|ø
positive-negative ::= =|!

SOme regex flavors require lookaround assertions to be fixed length and so disallow quantifiers, alternaton and backreferences

#### modfies |

conditional and branch rest groups modify the meaning of the | within.
A conditional gropu looks like (?<expression>|<expression>[|<expression]) and works much the same way as an if-conditional in usual programming languages
A branch reset group matches one of the alternatives indicated with | as alternation would normally.
A branch reset group resets the index of capture groups to the index it would have had at the beginning at each |.
The index of the next group after the branch reset group is the maximum index that a capture group could have within +1

<table style="text-align: left;">
  <tbody>
    <tr style="font-family: monospace">
      <th style="font-family: sans-serif">Regex</th>
      <td>(a)</td>
      <td>(? x</td>
      <td>(y)z|</td>
      <td>(p</td>
      <td>(q)r)|</td>
      <td>(t)u(v))</td>
      <td>(z)</td>
    </tr>
    <tr>
      <th>Group index</th>
      <td>((c:1;::1))</td>
      <td>((c:2;::2))</td>
      <td>((c:3;::2))</td>
      <td>((c:4;::3))</td>
      <td>((c:5;::2))</td>
      <td>((c:6;::3))</td>
      <td>((c:7;::4))</td>
    </tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}</span>

### reference

references are macros replaced with the content of the group they're referring to
references to nonexistant capture groups produce errors in most regex flavors, in JS they match an octal number up to \7.
backreferences refer to groups coming beforehand in the regex.
forward refer to groups coming afterward in the regex, they only match if inside of some sort of repetition, since the first time around there won't be anything to match in the group.
Most references are backreferences, not all regex flavors support forward references.
reference ::= <numeric-reference>|<nonnumeric-reference>
numeric-reference ::= \<positive-integer>
nonnumeric-reference ::= \k(<|')<name-or-negative-integer>('|>)|\g[\{]<name-or-negative-integer>[\}]
Most regexes that support the \k or \g flavors support them for both relative backreferences and named references
Some regexes support only the \k or \g flavors for relative/named refs, some support both, and some use a completely different syntax all together.
Relative backreferences use a negative number to count back from that position.

### Assertions 

Assertions in regex test if a condition is the case, but themselves only produce zero-length matches.
Assertions is a group consisting of the lookaround assertions, anchors

Anchors are a type of assertion that make sure the match starts/ends at a certain point.
A subtype of anchors makes sure the match starts/ends at the start/end of the line/string
^|start of line with multiline flag, start of string without multiline flag
$|end of line with multiline flag, end of string without multiline flag
\A|start of string (always)
\Z|end of string (always)
\b|word boundary
\B|not word boundary
\G|end of previous match/start of string

Notably, JS regex does not support \A and \Z.

\K keeps the text matched so far out of the overall regex match. 
keep-out ::= <expression>\K

### quantifiers

quantifier ::= (?|+|*|<range>)<quantifier-mode>
range ::= \{[<integer>][,][<integer>]\}

?|0 - 1
*|0 - ∞
+|1 - ∞
{n}|n
{n,}|n - ∞
{n,m}|n - m

quantifier-mode
ø|greedy
?|lazy
+|posessive

greedy|get longest possible match|tries token as many times as possible, and gradually shrinks match if backtracking
lazy|get shortest possible match|tries token as few times as possible, and gradually expands match if backtracking
posessive|get longest possible match, or none at all|tries token as many times as possible, does not backtrack

### recursion tokens

recursion-token ::= \(?(R|0)\)|\g&lt;0&gt;
recursion tokens must be marked optional, or they will always reach a point where they have consumed the whole string and want more, and thus the regex will fail
recursion in regex is most often used to match things that need to be balanced
The recursion token basically says "go one level deeper and start the match from the start"
Once the recursion token fails to match (assuming we have made it optional), the regex engine will backtrack back one level up the recursion hierarchy.

## flags

m|multiline|make ^ and $ match line boundaries
s|dotall/single-line mode|make . also match linebreaks
x|free-spacing mode|ignore whitespace (to match, spaces must be escaped); enable # comments
i|case-insensitive
g|global|more than one match

c|confirm before replacing|vim

## flavors

BRE treats most characters that would be metacharacters in other flavors as literals and as metacharacters only when escaped.
ERE does not have BRE's weird metacharacter behavior.
Both ERE and BRE are feature-poor compared to modern regex flavors.
both sed and grep default to BRE.

## the whole regex

Often, regexes are given in the pattern /<regex>/<replacement>/<flags>
sed uses the