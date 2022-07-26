#### nested rules

In SCSS/Sass and other CSS preprocessors, to achieve ⟮nested selectors⟯, you can ⟮nest entire rules⟯. 
```
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

In ⟮nested rules⟯'s selectors, ⟮c+;＆⟯ refers to ⟮the parent selector⟯. 
In nested rules's selectors, ⟮c+;＆⟯ is useful if ⟮you want to combine selectors in complex ways⟯ 
In ⟮nested rules⟯'s selectors, ⟮@at-root⟯ ⟮goes back up to the nesting tree.⟯ 

```
.parent {
  .child {
    ⟮c+;＆ div ＆ ＆ › a⟯ {}
  }
}
```
compiles to `⟮c+;.parent .child div .parent .child .parent .child › a {⟯}`

```
.grand-parent {
  .parent {
    @at-root .child {}
  }
}
```
compiles to `⟮.child {}⟯`

```
.button {
  ＆:visited { }
  ＆:hover { }
  ＆:active { }
}
``` compiles to `⟮.button:visited { } .button:hover { } .button:active { } ⟯`

```
.btn {
  ＆-primary {}
  ＆-secondary {}
}
``` compiles to `⟮.btn-primary {} .btn-secondary {} ⟯`