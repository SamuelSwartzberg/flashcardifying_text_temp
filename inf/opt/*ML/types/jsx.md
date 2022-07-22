# JSX

⟮JSX⟯ is ⟮HTML⟯-like syntax to be used in ⟮JS⟯
⟮any values⟯ embedded in JSX are ⟮auto-escaped⟯, and thus provide ⟮a degree of safety against XSS attacks⟯
You can put ⟮any valid JS expression⟯ within ⟮curly braces⟯ in ⟮JSX⟯
⟮JSX⟯ use ⟮camel case⟯ for ⟮HTML attribute names⟯ (including ⟮events⟯) (which would normally use ⟮kebap-case⟯)
In JSX, ⟮self-closing tags⟯ must be closed with ⟮c+;/›⟯, however ⟮every react component may⟯ be ⟮self-closing⟯
⟮JSX⟯ is either said to be short for ⟮JavaScript Syntax Extension⟯ or ⟮JavaScript XML⟯
Using JSX, you generally assign events via the on‹Event› handlers, but pass a function (instead of calling a function) , and wrap it in curly braces

## style props

style props is using react props to change the style of a component
style props are not enabled by default, but are used extensively in various react styling frameworks
style props mostly are named as the css properties are (subject to the camelcaseification/abbreviation described elsewhere)
style props also offer some abbreviated values:
linear/radial-gradient() → linear/radial()
to top, to top right, ... → to-t, to-tr...
using style props, we can also define 'states'. (not called that, this is my term)
style props 'states' could be pseudo-classes, aria states or custom chakra 'states'
style props 'states' take a leading underscore, and the actual style prop declarations go within an object within the state.
e.g. _hover={{ fontWeight: 'semibold' }}
flex-container:✫sm_2021-09-17--19-05-46-screenshot.jpg✫

⟮chakra⟯ provides some ⟮predefined shadows⟯ as style props with ⟮boxShadow⟯⟮="name"⟯

the sx prop is an escape hatch to CSS when style props are not enough.
the sx prop takes an object whose keys can be CSS or the style prop superset.
sx={{ filter: 'blur(8px)' }}
use-cases for the sx prop are css variables, css properties for which there are no style props, nested selectors and custom media queries.

## (Bootstrap) components via JSX

react-bootstrap implements boostrap components as react/JSX components
for react-bootstrap, components must be individually imported via react-bootstrap/ComponentName
ergo, components named via class names become ‹ComponentName›
parts of components become ‹ComponentName.Part›
properties that were implemented as key-value classes in Bootstrap become normal key="value" porps
react-bootstrap specifically, theme-color becomes `variant` (prob inspired by other react libraries)
