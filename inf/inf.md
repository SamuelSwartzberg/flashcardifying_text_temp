# general UI elements for some reason


#### CSSStyleDeclaration


## related technologies

### features

#### web typography

In most modern ＿styling frameworks＿ and generally in web design native fonts are now used.
The rise in using native fonts is in part attributable to the rise of more high-quality system fonts.

#### system UI themes

the ⟮System UI Theme Specification⟯ is a ⟮reasonably widely⟯ adopted spec for ⟮a style object⟯ that stores things for ⟮design systems⟯, especially ⟮scales⟯
at the heart of the ⟮System UI Theme Specification⟯ are ⟮scales⟯ - 
scales are ⟮arrays⟯ or ⟮objects⟯ of ⟮predefined sets of values⟯, for things such as ⟮font sizes⟯, ⟮colors⟯, etc.
According to the ⟮System UI Theme Specification⟯, the ⟮CSS properties⟯ that accept ⟮only a small, finite number⟯ of valid CSS values ⟮should not be included as a scale object⟯.
According to the ⟮System UI Theme Specification⟯, a ⟮key⟯ defining a ⟮scale⟯ should be called the ⟮same thing as the css property⟯, except ⟮plural⟯ (except for the weirdly-named `⟮space⟯`) and ⟮camelCase⟯, unless there are ⟮multiple css properties it might be used for⟯
```
// example fontSizes scale as an array
fontSizes: [
  12, 14, 16, 20, 24, 32 
]
// example colors object
colors: {
  blue: '#07c',
  green: '#0fa',
}
// example nested colors object
colors: {
  blue: '#07c',
  blues: [
    '#004170',
    '#006fbe',
    '#2d8fd5',
    '#5aa7de',
  ]
}
```
scales|CSS Properties
`space`| `margin`, `margin-top`, `margin-right`, `margin-bottom`, `margin-left`, `padding`, `padding-top`, `padding-right`, `padding-bottom`, `padding-left`, `grid-gap`, `grid-column-gap`, `grid-row-gap`
`fontSizes`|`font-size`
`colors`| `color`, `background-color`, `border-color`
`fonts`|`font-family`
`fontWeights`|`font-weight`
`lineHeights`|`line-height`
`letterSpacings`|`letter-spacing`
`sizes`| `width`, `height`, `min-width`, `max-width`, `min-height`, `max-height`
`borders`| `border`, `border-top`, `border-right`, `border-bottom`, `border-left`
`borderWidths`|`border-width`
`borderStyles`|`border-style`
`radii`|`border-radius`
`shadows`|`box-shadow`, `text-shadow`
`zIndices`|`z-index`
`transitions`|`transition`

#### colors

##### theme-color

some styling frameworks (e.g. bootstrap) use a system of semantic names for colors such as primary, secondary, success, danger, warning, info, light, dark...
In bootstrap the system of semantic colors is called theme-colors.

#### components

Pretty much any styling framework features pre-existing components and/or allows the creation of custom components.

##### variants

Many style frameworks have lg and sm version of some components.


#### z-indices

Z-index in bootstrap and perhaps in other frameworks exists on two scales: ⟮within elements, for states (for :hover, :active, :focus) ⟯, to prevent e.g. overlapping borders and ⟮for overlay components (modals, tooltips, etc.)⟯

situation|values
within elements|0-3
overlay components|1000-1080

#### abbreviation

styling frameworks tend to abbreviate things, especially CSS properties/values where possible.
However, not every CSS property/value is abbrevaited in each styling framework.
In styling frameworks property names often become a list of the first chars separated by hyphems when shortened.
E.g. something like `margin-end` would become `me`.
In react/style props based frameworks, CSS properties become camelCased unless abbreviated to chars only.
e.g. margin-top → marginTop / mt


##### things that are pretty much always abbreviated in every system

margin|m
padding|p
width|w
height|h
background|bg
gutters|g
top/bottom/left/right/start/end|t/b/l/r/s/e
top ＆ bottom / left ＆ right|y/x
no character|all four sides

#### active/disabled

Many styling frameworks, e.g. bootstrap, may take an active/disabled class (or whatever) to indicate that something is currently active/cannot be interfaced with.

#### theming

### CSS frameworking

Most CSS frameworks apply most things via CSS classes.
The most basic style of class most CSS frameworks use is .‹key›-‹value›.

#### conditional classes

There are two philosophies as regards adding conditions to CSS framework classes, colon-based and infixing.
colon-based|‹condition›:‹key›[-‹value›]|Tailwind
infixing|‹key›-‹condition›-‹value›|Bootstrap

`‹img class="w-16 md:w-32 lg:w-48" src="..."›`
Breakpoints might be the most common condition for CSS conditional classes.

#### types of classes


##### utility classes

Utility classes are common feature of css frameworks.
Utility classes change one specific aspect of a thing (background, font size, padding, etc.)
Utility classes either apply CSS classes more or less directly (e.g. `bg-white`), or offer light syntactic sugar for CSS to apply somewhat more semantic classes (e.g. `text-xl`, `font-medium`)
Systems that feature utility classes generally strongly recommend using them instead of custom css.

##### helpers

Helper classes in CSS frameworks are classes that achieve a single effect, albeit one that doesn't correspond neatly to a CSS property/aspect of an element (ergo not components).s

###### spacer

Spacers are a special type of utility in some styling frameworks.
Spacers apply margin or padding to one or more sides.
In bootstrap, spacers controlled by $spacer.

##### components

In CSS frameworks, typically a class .‹component-name› defines a component.
In CSS frameworks, typically parts of components are indicated by .‹component-name›-‹part›

#### implementation

Many CSS frameworks, amongst others bootstrap, are implemented by generating them from Sass (or other CSS preprocessors).
Since they are generated from Sass, to change functionality of Bootstrap or other CSS frameworks, change the Sass code.
For CSS frameworks, to change the Sass, import the code and then override whatever you want to change, then merge it back in, e.g. with map-merge.
Specifically, in bootstrap, utilities are stored in a $utilities assoc arr stored in a _utilities.scss.
Specifically, in bootstrap, the $utility assoc arr has each utility name as a key, and then a further assoc array with keys property, values.

### CSS reset

A CSS reset is a piece of CSS to reset browser's default styling.


### CSS syntax supersets

#### SCSS/Sass

⟮Sass⟯ is a ⟮CSS preprocessor⟯ that works with the two syntaxes ⟮Sass (the syntax)⟯ and ⟮SCSS⟯
⟮SCSS/Sass⟯'s ⟮scripting language⟯ which ⟮is its syntax superset⟯ is called ⟮SassScript⟯. 
Sass syntax that is indented rather than curly-braced   Sass
Sass syntax that is a CSS superset   SCSS (Sassy CSS)

While ⟮CSS⟯ will ⟮recover⟯ if ⟮an error is found⟯, ⟮SCSS⟯ will ⟮throw an error and refuse to compile⟯ 

##### @extend and placeholder classes

`⟮@extend⟯` is the keyword ⟮for inheriting styles of other selectors⟯. 
In common language ⟮`@extend foo`⟯ is saying ⟮you want something to have the same declarations as foo⟯. 
Internally, ⟮`@extend`⟯ works ⟮on selectors (instead of copying declarations⟯) 
A SCSS/Sass ⟮placeholder selector⟯ has the syntax ⟮`%foo`⟯. 
You put SCSS/Sass ⟮placeholder selector⟯ where ⟮selectors⟯ would go. 
An SCSS/sass ⟮placeholder selector⟯ itself is a ⟮selector⟯ that ⟮doesn't select anything⟯. 
An SCSS/sass ⟮placeholder selector⟯ is designed to be ⟮`@extend`ed⟯. 
```
%toolbelt {
  box-sizing: border-box;
  border-top: 1px rgba(#000, .12) solid;
  padding: 16px 0;
  width: 100%;

  ＆:hover { border: 2px rgba(#000, .5) solid; }
}

.action-buttons {
  @extend %toolbelt;
  color: #4285f4;
}

.reset-buttons {
  @extend %toolbelt;
  color: #cddc39;
}
```

##### mixins

⟮@mixin⟯ at its most simple defines ⟮a set of styles that can be reused⟯. 
⟮@include⟯ ⟮copies the styles⟯ defined by ⟮@mixin⟯ ⟮into the current block⟯. 
⟮@mixin⟯ can take ⟮arguments⟯, both ⟮sassscript⟯ and ⟮a block of css⟯. 
⟮@mixins⟯ and ⟮@include⟯ have ⟮functionally the same syntax⟯ as ⟮declaring⟯ and ⟮calling a function⟯ in other languages 
^though using the @mixin and @include keywords, as SCSS/Sass also has @function
⟮@content⟯ refers to ⟮a passed-in css block⟯ in @⟮mixin⟯. 

```
@mixin button() {
    ...
    @content;
}

.alert {
    @include button {
        color: #F00;
    }
}
```
```
@mixin replace-text($image, $x: 50%, $y: 50%) {
  text-indent: -99999em;
  overflow: hidden;
  text-align: left;

  background: {
    image: $image;
    repeat: no-repeat;
    position: $x $y;
  }
}

.mail-icon {
  @include replace-text(url("/images/mail.svg"), 0);
}
```


### CSS naming schemes

BEM = Block Element Modifier
BEM is a CSS naming convention
BEM uses kebap-case in naming individual things.
BEM requires all our selectors to only use BEM classes and nothing else, with the possible exception of generated HTML we have no control over.
in BEM, a block is a logically and functionally independent page component.
in BEM, a block is the equivalent of a component in Web Components.
BEM Blocks can be nested inside any other blocks.
BEM Blocks can be moved or reused, as they are independent of their surroundings.
in BEM, an element is a constituent part of a block that can't be used outside of it.
in BEM, an element without a block has no meaning.
in BEM, a modifier defines the appearance and/or behavior of a block or element
BEM Entities = {block, element, modifier}
in BEM, a mix is having multiple BEM entities on a single node
bem-name ::= ‹block-name›[__‹elememt-name›][_‹modifier-name›[_‹modifier-value›]]
the modifier-value of BEM can be dropped if it's just a boolean value
BEM names are set in classes
It is important to keep in mind that a BEM entity is not a part of the name, rather one BEM name always refers to one entity, even if it includes the names of other entitites.

### types of frameworks


#### bootstrap

Bootstrap has been the most common CSS-first framework in the 2010s and going into the 2020s
next to its own technologies, bootstrap may require popper
By default, bootstrap only uses margin-bottom.

#### chakra

⟮Chakra⟯ provides a sensible ⟮default⟯ theme inspired by ⟮Tailwind CSS⟯

##### components

##### unsorted

{{c3::Chakra UI}}&nbsp; converts {{c2::theme tokens (colors, font sizes, stc)}} to {{c1::CSS variables}}.

{{c1::useColorMode}} is a React {{c2::hook}} that gives you access to {{c3::colorMode}}, {{c3::toggleColorMode}}

{{c1::useColorModeValue}} is a React hook used to {{c2::change any value or style based on the color mode}}. It {{c4::takes 2 arguments}}: {{c3::the value in light mode}}, and {{c3::the value in dark mode}}.

{{c1::baseStyle}}, {{c1::sizes}} and {{c1::variants}} of your {{c2::theme.components}} entry can also take a {{c3::function}} so you can {{c3::generate}} them based on the current {{c4::theme}}, {{c4::colorMode}} or {{c4::colorScheme}}

{{c1::Themera}} is a web app to {{c2::generate chakra UI color schemes}} (there are also many others tho)

{{c1::Color mode}} is chakras way for managing {{c2::light and dark mode}}. It accepts the values {{c3::light}}, {{c3::dark}}, and {{c3::system}}

{{c1::Chakra}}'s {{c3::default}} {{c2::theme}} (and {{c3::any other}} {{c2::theme}}) includes defaults for all the {{c4::System UI Theme Specification scales}}

{{c1::&lt;Container&gt;}}s by default {{c2::constrain the size of the content}} to {{c3::60ch}}, but can take the {{c4::maxW}} prop with the value {{c5::container.&lt;breakpoint&gt;}} to {{c2::constraine the content}} to that breakpoint instead. It can also center its content via the {{c6::centerContent}} property.

{{c1::&lt;ColorModeScript&gt;}} is necessary {{c2::for color mode in chakra to work}}, and needs to be {{c3::one of the first things in the &lt;body&gt;}}

you customize components {{c1::globally}} by editing {{c2::the relevant component}} within <code>{{c3::theme.component}}</code><br/><div class="sub">
<div class="sub all-b"><pre><code>const theme = extendTheme({
  components: {
    Button: {
      // 1. We can update the base styles
      baseStyle: {
        fontWeight: "bold", // Normally, it is "semibold"
      },
      // 2. We can add a new button size or extend existing
      sizes:

#### tailwind

⟮Tailwind CSS⟯'s main idea is ⟮using preexisting CSS classes⟯ for styling, instead of ⟮switching to CSS⟯ 
⟮Tailwind config⟯ is done in the ⟮tailwind.config.js⟯ file, which works similarly to ⟮the webpack config file⟯ 
Using ⟮Tailwind CSS⟯, code might look like this:
```lang=html;
‹div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4"›
  ‹div class="flex-shrink-0"›
    ‹img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo"›
  ‹/div›
  ‹div›
    ‹div class="text-xl font-medium text-black"›ChitChat‹/div›
    ‹p class="text-gray-500"›You have a new message!‹/p›
  ‹/div›
‹/div›
```

# data

open data is data available to everyone freely.
linked data is data that is interlinked usefully.

# data models

A data model is a model that provides structure to data, and to their properties, how they relate amongst each other, and how they relate to RL.

## fundamentals

### ＆ databases

A database is an organized collection of data.
Any database implements a data model.

#### DBMS

A DBMS (database management system) is the software used to manage a database.

### query languages

A (data)(base) query language is a language used to query data in databases/information systems.

### operations

⟮CRUD⟯ is short for ⟮create⟯, ⟮read⟯, ⟮update⟯, and ⟮delete⟯, the four operations that ⟮persistent storage⟯ pretty much always has.

### schemata

A schema is a format that describes/constrains/validates data/data structures

## various data models

### relational data model

#### fundamentals

##### relational data model itself

https://upload.wikimedia.org/wikipedia/commons/7/7c/Relational_database_terms.svg

in a relational data model, a tuple is an ordered set (lol) of attribute values
in a relational data model, a relation is made up of a heading and body.
in a relational data model, a heading is a set of attributes.
The number of attributes constituting a heading is called the degree, which term also applies to tuples and relations. 
in a relational data model, a body is a set of n-tuples of the length of the degree of the heading.
The heading of the relation is also the heading of each of its tuples.
in a relational data model, an attribute is an ordered pair of attribute name and type.
relation|table
tuple making up the body|collection of rows
n-tuple|row
attribute|column

##### database

a relational database is a database with a relational data model.
In a relationnship database each n-tuple/row has its own unique key known as the primary key.
A foreign key is a column used in a relational database to link tables/relations by referencing a primary key of a row in a different relation/table.
A child table uses a foreign key to reference a primary key in the parent table. (parent ← child)
Foreign keys can be used for one-to-one or one-to-many relationships

##### tabular data

A table is an accepted visual representation of a relation.
TODO revise in light of above info
tsv|tab-separated values
csv|comma-separated values

⟮A table⟯ (e.g. in ⟮database or spreadsheet⟯ contexts) is ⟮a collection/sequence/whatever of⟯ ⟮records⟯. 
⟮A record⟯ is ⟮a collection/sequence/whatever of⟯ ⟮fields⟯, which ⟮each contain an item of data⟯. 
A ⟮record⟯ is ⟮more or less kinda⟯ synonymous to ⟮row⟯. 
⟮Field⟯ is ⟮sometimes used⟯ as a synonym for ⟮column⟯, though following ⟮the above differentiation⟯, this is of course ⟮incorrect⟯. 
⟮csv⟯ and ⟮tsv⟯ both store ⟮tables/tabular data⟯. 
⟮csv/tsv⟯ separate ⟮records⟯ via ⟮newlines (generally CRLF⟯) 
The ⟮first line⟯ of ⟮csv/tsv⟯ may be ⟮a header⟯. 
⟮the csv/tsv header⟯ should have ⟮as many fields⟯ ⟮as the other records in the documents⟯. 

name|separates fields how
⟮csv⟯|⟮with commas⟯, sometimes also ⟮arbitrary different characters⟯
⟮tsv⟯|⟮with tags⟯

Neither ⟮csv⟯ nor ⟮tsv⟯ are ⟮fully standardized⟯, or rather ⟮the specs aren't always followed⟯. 
In ⟮csv/tsv⟯, ⟮wrapping a field in double quotes⟯ commonly allows ⟮the field separator to be included in the field⟯. 
If in csv/tsv ⟮a field is wrapped in double quotes to allow the field separator to be included in the fields⟯, ⟮double qoutes⟯ are then excaped by ⟮double double quotes⟯. 
⟮Trailing newlines⟯ at the ⟮end of documents⟯ are ⟮optional⟯ for ⟮csv/tsv⟯, ⟮field separators⟯ at ⟮the end of the line⟯ will ⟮create empty fields⟯. 

tidy-viewer is a FOSS rust-based csv viewer 
-s ‹char›|delimiters

#### various relational data models / databases

##### (query) languages

SQL is a language used to manage relational databases.
SQL, despite its name, consists of a data query language, data definition language, data control langauge, and data manipulation language.

### non-relational data models

A NoSQL database is really a misnomer, it refers to a non-relational database

#### graph data models

A graph data model is one that organizes entities and their relationships as a graph.
A graph database is a database that uses a graph data model.

#### various non-relational data models / databases

##### RDF

RDF = resource description framework
RDF is a technology meant to realize the semantic web.
RDF implements a graph data model.
semantic triple = RDF triple 
semantic/rdf triple is sometimes shortened triple
a semantic triple is the atomic data unit in the RDF data model
a semantic triple has the three roles subject, predicate object
a semantic triple encodes the three roles subject predicate object as a directed graph, with the subject and object being nodes, and the relationship as an edge.
A named graph is a set of triples named by an URI
RDF is an abstract data model, which can be implemented for example by the various structured data data formats.

In rdf, a node can be a IRI, literal, or blank node

an RDF semantic triple indicating that art knows bob using the FOAF ontology might look like ex:art foaf:knows ex:bob

###### related technologies

####### OWL

OWL short for web ontology langauge
OWL, RDFS and SHACL are ontology languages for RDF

###### Query languages 

####### sparql

SPARQL = SPARQL Protocol and RDF Query Language
SPARQL is proounced sparkle
SPARQL is an RDF query language

###### applications

####### FOAF

FOAF = friend of a friend
FOAF is an ontology for people, their properties and their relations using RDF/OWL 

##### open graph

The Open Graph protocol enables any web page to become a rich object in a social graph.
open graph is based on RDFa.
Open graph metadata is specified within meta tags.
There are four required properties for open graph, which are og:image, og:title, og:type and og:url.
The property of the open graph metadata is specified within the property property, and the value of the open graph metadata is specified within the content property.

##### graphQL

GraphQL consists of a query language, a server-side runtime for executing these queries, and a type system for these queries.

###### queries

In GraphQL, a query has the same shape as the result.
A graphQL query starts at a special root object

graph-ql-query ::= \{{‹field-query›}\}
field-query :: = ‹field-name›[\(\‹query-arguments›\)] [\{{‹field-query›}\}]
query-arguments: ‹key›: ‹value›

In GraphQL, any field can take its own arguments, even if it's nested, removing the need for multiple queries.

```
{
  human(id: "1000") {
    name
    height(unit: FOOT)
  }
}
```

###### type system

object-type ::= type ‹name› \{{‹field›\}
field ::= ‹key›[]


#### document data model

a document database implements a document data model.

##### mongo db

MongoDB is the most well known document database.
IndexedDB = Indexed Database API.
IndexedDB is a document database for client-side storage.
Most document databases are based on a variant of JSON.

### related technologies

#### structured data

Structured data is a data format used for adding data to web pages.
Often, structured data is used to encode RDF.
Sometimes, structured data is used in a more abstract sense to contrast with unstructured data.
Structured data is used by search engines to provide more rich results.
Schema.org is a set of schemas for structured data.

##### implementations

###### JSON-LD

JSON-LD is an implementation of structured data.
JSON-LD is included via a script tag 
Of the structured data formats, google prefers JSON-LD.

###### Other implementations

RDFa Lite is a minimal subset of RDFa that can be directly included in HTML.
Microdata is a format to include structured data in HTML.

# semantics

## semantic web

The semantic web is sometimes known as web 3.0
The goal of the samntic web is to make internet data machine readable
A semantic query is a data query on the semantic web.
the social graph is a graph that represents social relationship between entities.
the open graph allows web pages to become objects in a social graph

A hyperlink is a reference to data which the user can follow by interacting with it.
Hypertext is text connected by hyperlinks.
Hypermedia is media connected by hyperlinks.

A ontology languages is a language that describes an ontology. 

## folksonomy

⟮Folksonomy⟯ is a system where ⟮users⟯ apply ⟮public tags⟯ to items, thus over time generating a sort of ⟮taxonomy⟯. 
Two types of ⟮folksonomies⟯ are ⟮broad⟯, where ⟮multiple users can apply the same tag⟯, thus ⟮showing which tags are the most popular⟯, and ⟮narrow⟯, where ⟮the same tag can only be applied once⟯ 

booru: image site with foksonomical tags
boorus: generally look similar to Danbooru, the original
sexual content: rating:s(afe), rating:q(uestionable), rating:e(xplicit)
Other boorus for anime pictures: danbooru(.donmai.us), zerochan, gelbooru, anime-pictures, safebooru (either safebooru.org or safebooru.donmai.us), rule34.paheal.net

flex-container:✫sm_2021-10-19--03-12-32-screenshot.jpg✫✫sm_2021-10-19--03-11-46-screenshot.jpg✫✫sm_2021-10-19--03-10-58-screenshot.jpg✫

# extracting information

⟮A hash function⟯ ⟮maps⟯ ⟮data of arbitrary size⟯ ⟮to⟯ ⟮fixed size-values⟯ ⟮deterministically⟯. 
⟮The result of a hash function⟯ is generally called ⟮a hash⟯. 
At it's most general, a fingerprint is an unique combination of features that uniquely identify something.
A fingerprinting algorithm reduces a data item to a much shorter unique identifier, often also called a fingerprint.
Often, hashing algorithms are used as fingerprinting algorithms.
A ⟮checksum⟯ is a ⟮small amount of data⟯, derived by applying ⟮a suitable algorithm⟯ the relevant data, used to ⟮check whether errors have occurred⟯, e.g. in ⟮transmission⟯, ⟮storage⟯ or ⟮data entry⟯.
Depending on its design goals, a good c⟮hecksum⟯ algorithm usually outputs ⟮a significantly different value⟯, even ⟮for small changes made to the input⟯. 
A check digit is one or more digits or characters (but generally a small amount) used as a checksum.

# HCI






#### breadcrumbs


flex-container:✫sm_2021-06-26--14-46-16-screenshot.png✫
A breadcrumb trail is a series of separated breadcrumbs, each representing a distict navigational item organized into a logical sequence.
A breadcrumb trail most commonly represents a hierarchical structure.
Each breadcrumb is usually a minimal element containing text only.
In bootstrap, breadcrumbs are created by .breadcrumb › .breadcrumb-item*n


## image rendering

Sprites are multiple graphics fused into an image, which is then masked to only show the relevant image
The two main advantages of sprites over multiple images is that  they can be easier to use and that   they take only one request to load which used to be better, but might not be anymore with HTTP/2




# design

flex-container:✫sm_paste-cb3a6dba13c1114c73bc6f0fe28db50a33115787.jpg✫✫sm_paste-d33218361257ffbf6af9622ca81f2ec76c4c892c.jpg✫✫sm_paste-77fe64317aade2f78384ed042619b7625fb24c43.jpg✫✫sm_paste-36ea8c9033d617787cf777046d06e8b5f8db3454.jpg✫

It is often said (esp. in animation) that ⟮good characters⟯ should ⟮be recognizable by⟯ ⟮their silhouette alone⟯ 


flex-container:✫sm_faces1.gif✫
flex-container:✫sm_1280px-FedEx_Corporation_logo.svg.png✫

flex-container:✫sm_Childe-Hassam-The-Flag-Outside-Her-Window-April-Aka-Boys-Marching-By-1918.jpg✫

⟮Negative space⟯ is ⟮the area without subjects/areas of focus⟯
⟮Positive space⟯ is ⟮the area with subjects/areas of focus⟯
In the image, if ⟮you see a vase⟯, the ⟮black space⟯ is the ⟮negative space⟯ and the ⟮white space⟯ is the ⟮positive space⟯
In the image, if ⟮you see two faces⟯, the ⟮white space⟯ is the ⟮negative space⟯ and the ⟮black space⟯ is the ⟮positive space⟯
In the image, the ⟮positive space⟯ is (probably/arguably) ⟮the woman.⟯

flex-container:✫sm_merlin_159438345_f559b53a-6da1-49f2-a8d8-141c8887d2a6-articleLarge.jpg✫✫sm_merlin_159438405_49d288c9-c4ea-4540-a749-adb9bb055a59-articleLarge.jpg✫✫sm_merlin_159438372_c70d27a9-7ece-413f-8e68-65aea6e57894-articleLarge.jpg✫


⟮hostile/defensive architecture/design⟯ is architecture that ⟮restricts/guides behavior⟯ to ⟮protect property⟯ or ⟮prevent crime⟯ 
hostile/defensive architecture might look like ⟮‹image›⟯ 
The most common people targeted by ⟮hostile/defensive architecture/design⟯ in the west are ⟮the homeless⟯ and ⟮young people⟯ 

# misc

mentions indicate that a user is being addressed, often linking to that user and also sending a notification.
On most platforms, mentions begin with @.


# non-standard humans or non-humans

## either






# data storage

# memory

## medium

### holes

In punch card/punched tapes, the two states of binary data represent the presence or absence of holes.
punched tape is like punched cards, but continuous

### flash memory

Solid state memory/storage in theory is any storage without any moving part.
Flash memory is the most common type of solid state memory.

## mutability ＆ volatility

ROM  Read only memory
ROM is memory that is set once, and then cannot be changed anymore, or only using a special technique.
ROM was used to store games on game cartidges, for example.
Memory that retains information after power is removed   Non-volatile memory
Memory that requires power to retain stored information   Volatile memory

## addressing

Memory is generally addressed via memory addresses.
Physical addressing is addressing memory by using addresses corresponding to actual memory addreesses
Logical Address = Virtual Address
Virtual/logical memory is addresed by virtual/logical addresses.
Logical/virtual addressing adds a layer of abstraction over physical addressing. 
Virtual memory ＆ addresses are used by the OS for primary memory, but also may be used in other circumstances.
Nearly all current implementations of virtual memory for primary memory divide virtual memory into pages.
Pages of virtual memory typically have a fixed size or a few preditermined fixed lenths.
For primary memory, virtual addresses are mapped to physical addresses in the page table.
The MMU (Memory management unit) is a hardware device typically used to handle the page table/mapping of log to phys addr.
Each process has its own section in virtual memory.
Virtual memory will appear to an application using it to be continuous, though the physical memory it occupies may be discontinous.
Today, modern OSs only expose virtual memory to user-level programs.
Virtual memory benefits security, as it means programs can't access each other's memory.
Logical block addressing is logical addressing for secondary memory using one or more blocks.
A logical block contains its binary contents and a bit of metadata.
With logical blocks addressing, a file will always be a multiple of the block size
blocks are the smalles unit your file system can write in in.
blocks are usuall between 0.5kiB and 8kiB as of 2020.
Small blocks may cause storage overhead b/c the metadata to content ratio is smaller
large blocks may cause storage wastage b/c small files still need at least a single block.


### memory management

swap/page storage are virtual memory that is secondary memory used as an extension of primary memory
swap/page storage may be a file(s) or a partition(s).
managing virtual memory pages within primary memory|paging
moving virtual memory from secondary to primary memory or v.v. (using pages)|swapping or paging
moving virtual memory from secondary to primary memory or v.v. (without using pages)|swapping
primary → secondary memory|paged/swapped out
secondary → primary memory|paged/swapped in

## fragmentation

⟮Memory fragmentation⟯ is when memory is ⟮allocated in many non-contiguous blocks⟯, meaning it has ⟮small spaces that can't store anything useful⟯ 
⟮Memory fragmentation⟯ results in ⟮the wasting of storage⟯. 

## relation to processor

The difference between primary and secondary memory is that the processor can address primary memory directly.

### primary memory/storage

The terms primary storage/memory, internal storage/memory, and main storage/memory are often used interchangeably.
As I will use the term, primary memory consists of CPU core Registers and Cache as well as main memory.
Both registers and cache are directly on the chip.
Nonvolatile RAM   NVRAM
SRAM  static random access memory
DRAM  dynamic random-access memory
RAM random-access memory
SRAM is faster than DRAM and is therefore used for the chace and internal registers.
RAM is sometimes used as a catch-all for any primary memory.
Principle of locality AKA locality of reference
principle of locality = (Principle of) Temporal Locality ＆ Spatial Locality
principle of locality relates to memory access, specifically it predicts what memory will be accessed next.
principle of spatial locality = Memory that is close (to the currently accessed memory cell) will tend to be accessed again
principle of spatial locality = Memory that has recently been referenced will be referenced again soon.
Memory closer to the processor is faster but more expensive and smaller, memory further away from the processor is slower but cheaper and larger.
memory speed:
registers › processor cache › main memory › secondary memory

### secondary memory

secondary meory is generally non-volatile memory

#### drives

HDD  Hard disk drive
SSD  Solid state drive/device/disk
clonezilla is the standard FOSS program for cloning entire drives.

##### HDD

HDDs store bits of data data via magnetic north/south.
Physically, a HDD stores the data on rotating platters.
A HDD usually includes a few platters.
HDDs are thick even though individual platters are thin because HDDs generally contain multiple platters.
HDD platters are discs usually made up of a aluminum/glass plate coated with a magnetic coating.
in a HDD, the head performs read-writing.
in a HDD, the head is mere nanometers from the platter.
⟮h1;✫sm_250px-Samsung_Harddrive_headcrash_DSCN0124b.jpg✫⟯
A head crash is the head of a HDD making contact with its rotating platter, slashing the surface and causing disk damage/failure.
Head crashes generally happen due to falling/jolts or due to dust sticking to the head.

flex-container:✫sm_hdd_w_labels.svg✫
flex-container:✫sm_1280px-Seagate_ST33232A_hard_disk_head_and_platters_detail.jpg✫✫sm_220px-Laptop-hard-drive-exposed.jpg✫
as of 2020, HDDs usually spin at 5400 or 7200 RPM.
as of 2020, HDDs are typically a few TB in size.

a HDD is made up of clusters which are made up of sectors.
A sector used to be 512 byte large normally; today, that is usually 4096 Bytes (4KiB)

flex-container:✫sm_cyl_head_sect_dia.svg✫

HDDs originally used a form of physical addressing known as CHS.
CHS = Cylinder Head Sector
CHS used the head, cylinder and sector (like coordinates) to specify a memory location.
CHS was replaced in the mid-90s by logical block addressing.

##### SSD

A flash memory device typically consists of multiple flash chips and a controller.
a flash chip is made up of blocks which are made up of pages
To write new data on a flash memory device, first you need to erase the old data.
Flash memory can either be NAND or NOR based.
NAND flash can typically erase only whole blocks, but write pages too
After a certain number of write cycles, flash memory begins to decay.
Flash memory is typically faster than magnetic memory.
SSDs are a type of flash memory device.


onion-box:
⟮c;SSD chip⟯
  ⟮c;block⟯
    ⟮c;page⟯
    ⟮c;page⟯
    ⟮c;page⟯
    ⟮c;...⟯
  ⟮c;block⟯
    ⟮c;...⟯
  ⟮c;...⟯

# secondary memory organization

## devices

RAID = Redundant Array of Inexpensive/Independent Disks
SLED = Single Large Expensive disk
RAID ↔ SLED
RAID uses multiple disks.
RAID disks are in some sort of configuration which aims to achieve one or more of the three aims reliability/redundancy, performance, capacity
RAID 0|Data is split among the drives (striped)|performance (r/w)
RAID 1|data is mirrored on all drives|reliability ＆ some read performance

`df` shows memory device storage usage


# files

















## file formats




### binary

Binary files without a specification/documentation/parser are basically meaningless/unreadable.
What the binary files contents mean is defined by the file format.
Binary files are generally smaller and quicker to process than plaintext files

#### encoding as text

⟮binary-to-text encodings⟯ represent ⟮binary data⟯ with ⟮plain text⟯ 
⟮binary-to-text encoding⟯ is ⟮inefficient⟯ but is ⟮necessary⟯ to ⟮send binary data over plaintext channels⟯, e.g. in ⟮email⟯. 
the most common ⟮binary-to-text encoding⟯ is ⟮base64⟯. 
⟮base64⟯ uses ⟮ASCII⟯ to ⟮represent binary data⟯. 
⟮base64⟯ can encode ⟮6⟯ bit of ⟮data⟯ in ⟮8⟯ bit of ⟮text⟯. 
⟮data URIs⟯ are a type of URI defined by ⟮the data scheme⟯ that provide a way to ⟮include arbitrary data inline⟯. 
⟮data URIs⟯ most commonly use the ⟮binary-to-text encoding base64⟯ to ⟮encode their data⟯. 
data URI syntax `⟮data:⟯⟮[‹media type›]⟯⟮c+;[;base64]⟯⟮,‹data›⟯` 
base64 is a command-line program to en/decode things as base64

#### bitmaps

In the technical definition, a bitmap maps some domain to some bits.
In the technical definition, a pixmap is a bitmap mapping a pixel to a set of bits.
While in the technical definition, a pixmap is a hyponym of bitmap, they also may be treated synonymously, or sometimes a bitmap is seen as a hyponym of pixmap where one uses one bit per pixel.
The common file format for a pixmap image is BMP.
Pixmap images are very large, since they don't have any compression.

#### multimedia

(multi)media files are almost always binary files

##### video/sound

Default mac japanese voice is  Kyoko

###### players

ffmpeg media player   `ffplay`

mpv|terminal based video player

mpv plays files, urls, and playlists.

Play a playlist‹filename›   --playlist=‹filename›
don't open a new video window‹filename›‹/filename›   --no-video

####### mpd mpc

mpd is short for Music Player Daemon.
mpd acts as a server, which you can start via the `mpd` command (either directly or via a service)
As a proper server, mpd occupies a port on the host.
You can interface with the mpd server with a number of clients, e.g. mpc

mpc -p port or --port=port|connect to mpd at the specified port
`mpc queue(d)`|⁑show⁑ next song
`mpc current`|show currently playing song
`mpc update`|update collectiion by scanning for changed files
`mpc stats`|display mpd playing info such as total play time up until now, etc.
`mpc rescan`|rescan whole music directory
`mpc lsplaylists`|list all current playlists
`mpc ls`|list the contents of the music directory
`mpc load ‹name›`|load a certain playlist
`mpc clear`|clear queue
`mpc shuffle`|reshuffle the playlist
`mpc single`|toggle single mode (will stop playing after one song, or repeat one song if repeat is toggled)
`mpc repeat`|toggle repeat
`mpc random`|toggle random playback (that is, pick songs from the queue at random)
`mpc prev`|go to previous song
`mpc playlist`|show the current playlist
`mpc pause`|pause
`mpc next`|go to next song
`mpc toggle`|play if paused, pause if playing

###### processing

####### ffmpeg

ffmpeg is mainly a video/audio converter

ffmpeg-command ::= ffmpeg ‹global-options› ‹input-specifier›{ ‹input-specifier›} ‹output-specifier›{ ‹output-specifier›}
input-specifier ::= [‹input-options›] -i ‹url›
output-specifier ::= [‹output-options›] ‹url›
input-options ::= {‹input-only-option›‹input-output-option›}
output-options ::= {‹output-only-option›‹input-output-option›}
input-file-option-specifier ::= ‹input-index›:‹stream-index›

ffmpeg input and stream index are zero-based

input-output-options
-ss ‹position›|seek to position
-to ‹position›|stop at position
`-preset FOO`   set the speed (and thus the effectiveness) of the encoding (values such as veryfast, medium, slow...)

##### images / combined

###### types

flex-container:✫1280px-VectorBitmapExample.svg.png✫

Vector images/graphics are images created directly from geometric shapes.
Vector images are contrasted wtih raster images/graphics.
Raster images are images created from a matrix/grid of square pixels. 
The main advantage of vector images being that they are infinitely scalabe.
The process of generating a raster image from a vector image is known as raserization.
Vector images are most commonly edited in dedicated vector graphics editors or text editors.
Adobe Illustrator|proprietary, desktop|.ai
Affinity Designer|proprietary, desktop|.afdesign
Inkscape|FOSS, desktop|SVG
SVG-edit|FOSS, web|SVG

####### SVG

SVG is the standard format for vector images
SVG is a subformat of XML.
SVG files have the file extension of .svg
SVG|Scalable Vector Graphics
The ⟮current version of SVG⟯ is ⟮1.1.⟯, with version ⟮2⟯ being ⟮in planning since forever⟯. 
Often, ⟮SVG⟯ is ⟮included in HTML⟯. This can be done by i⟮ncluding it directly in the source⟯, r⟮eferencing it in places the browser would normally take an image (‹img›, background-image⟯), or ⟮pointing to it within an ‹object› or an ‹iframe›⟯ 
⟮‹foreignObject›⟯ is an SVG element that allows you to ⟮include non-SVG XML⟯, most commonly ⟮s15;⟮HTML⟯⟯. 


######### affinity designer

flex-container:⟮h∞;✫sm_Screenshot%202020-04-05%20at%2018.40.27.jpg✫⟯

To ⟮select a color in affinity designer⟯ (must be in ⟮Pixel Persona⟯) ⟮c+;Select › Select Sample Color⟯ 
To ⟮turn a color transparent⟯ in affinity designer ⟮select a color, then delete it with backspace⟯ 

###### viewers

feh|terminal-launched image viewer
imgcat|in-terminal image viewer

###### processing

unpaper cleans/post-processes scanned pages
pdftk and qpdf are the most common CLI tools for pdf transformation
gifsicle is a CLI program to manipulate gifs
remove.bg is an AI tool that can remove the bg of images with people in them.
remove.bg is accessible via an API as well, which can be called via a command `removebg`

####### ocrmypdf

`⟮ocrmypdf⟯` is a command line tool to ⟮add OCR text to scanned PDF files⟯. 
```
ocrmypdf ⟮SOURCE DEST⟯
```
⟮specify language⟯|⟮`-l deu/fra/deu+fra...`⟯
⟮correct slight skew⟯|⟮`--deskew`⟯
⟮clean pages before ocring⟯|⟮`--clean`⟯
⟮change/correct rotation (the one in steps of 90°⟯)|⟮`--rotate-pages`⟯


####### imagemagick

⟮Imagemagick⟯ is ⟮a set of programs⟯ for ⟮modifying images.⟯ 
⟮Imagemagick⟯ mainly exists as ⟮a cli⟯, has ⟮a basic X window gui⟯, and ⟮API bindings⟯ for ⟮pretty much any programming language under the sun⟯. 
⟮imagemagick⟯ contains ⟮a bunch of subcommands⟯, which ⟮do different things⟯ but ⟮often accept similar arguments⟯ 
imagemagick options/arguments ⟮start with a single dash,⟯ regardless of length 
All imagemagick subcommands may be ⟮prefixed by magick (e.g. magick mogrify, magick animate⟯) or ⟮not⟯. 
The main two commands for ⟮image conversion⟯ w/ ⟮imagemagick⟯ are ⟮mogrify⟯ ⟮(c:49;in-place⟯) and ⟮convert⟯ ⟮(c:49;out-of-place⟯) 
Many of imagemagicks arguments needing to specify ⟮some kind of shape/size⟯ accept a ⟮geometry⟯ argument with the syntax ⟮‹size›⟯⟮[‹offset›]⟯ where the size specifier follows the syntax 
⟮‹width›⟯⟮x⟯⟮‹height›⟯⟮[‹operator›]⟯ 



table:span=2;Imagemagick subcommands
⟮`import`⟯|⟮Imagemagick screenshot utility⟯
⟮`identify`⟯|((c:4;::Imagemagick display details of an image file
```lang=text;
magick identify -verbose rose.jpg
Image: rose.jpg
  Format: JPEG (Joint Photographic Experts Group JFIF format)
  Mime type: image/jpeg
  Class: DirectClass
  Geometry: 70x46+0+0
  Units: Undefined
  Type: TrueColor
...
```
))
⟮`display`⟯|⟮Imagemagick image viewer⟯
⟮`animate`⟯|⟮Imagemagick animation creator⟯
⟮`compare`⟯|⟮Imagemagick visual comparison tool✫sm_paste-ebe2143588b596e4c4762fa1d4f79aaad9bf0665.jpg✫⟯
⟮`composite`⟯|⟮Imagemagick overlay image tools✫sm_paste-941c2b6b4528410451a2670256f0499b19879054.png✫⟯
⟮`convert`⟯|⟮Imagemagick convert between image formats✫sm_paste-8ba1c45c2dc3cc0f2cd231dfec641b7b7e64e382.jpg✫⟯
⟮`montage`::m⟯|⟮Imagemagick montage creator✫sm_paste-65d507ceb80556af17e0f02061e7f7f54fc9e73d.jpg✫⟯




table:span=2;Imagemagick options
⟮`-crop`⟯|⟮crop⟯
⟮`-trim`⟯|⟮remove borders around the image⟯
⟮`-resize SIZE-SPECIFIER`⟯|⟮resize the image to SIZE-SPECIFIER⟯
⟮`-quality QUALITY`⟯|⟮set the (e.g. jpeg) quality to QUALITY (1-100 for jpeg⟯)
⟮`-fuzz distance`⟯|⟮make matching colors more, well, fuzzy⟯
⟮`-flop`⟯|⟮Mirror along the y-axis (in x direction, text will be mirrored L‹-› R⟯)
⟮`-flip`⟯|⟮Change to upside down⟯










# hardware/low-level

# hardware only

## electrical connectors

flex-container:✫Connectors.jpg✫✫1280px-ConnectorSymbols.svg.png✫



An ⟮electrical connector⟯ is a device that ⟮joins electric conductors⟯ ⟮mechanically⟯ and ⟮electrically⟯.
In ⟮electrical connectors⟯, the ⟮mechanical connection⟯ is ⟮to allow the electrical connecton to stay in place⟯ and thus ⟮an electrical circuit to be created⟯. 
Most ⟮electrical connectors⟯ have ⟮a gender (male or female :( ⟯) 
An ⟮electrical connector⟯ that is ⟮a protusion⟯ is ⟮male⟯. 
An ⟮electrical connector⟯ that is ⟮a receptacle/indentation⟯ is ⟮female⟯. 
An ⟮electrical connector⟯ with ⟮male gender⟯ is also called ⟮a plug.⟯ 
An ⟮electrical connector⟯ with ⟮female gender⟯ is also called ⟮a socket/jack⟯. 
A ⟮terminal⟯ is ⟮the point where a conductor ends⟯. It may be ⟮an electrical connector⟯. 

## transistor → logic gate → logic circut

### transistors

A transistor has three terminals.
In a transistor, if you apply power to two certain terminals, power can flow through two other terminals. (of course, between both of the sets of the terminals, one will be the same.

flex-container:✫sm_transistor-current-explanation.png✫

BJT  Bipolar junction transistor
The three terminals in a bipolar transistor are called ⟮base⟯, ⟮collector⟯, and ⟮emitter⟯.
BJT are either PNP or NPN.
NPN transistor  Negative Positive Negative transistor
PNP transistor  Positive Negative Positive transistor
for NPN transistors, applying power (at the base) allows the current to flow.
for PNP transistors, applying negative/no power (at the base) allows the current to flow.
For NPN BJT transistors, if you apply power to the base, it will flow to the emitter, allowing a stronger current to flow between collector and emitter.

flex-container:✫sm_tmpr_uvk0fj.png✫


flex-container:✫sm_tmpadmp5k8t.png✫
The three terminals in a field-effect transistor (FET) transistor are called ⟮gate⟯, ⟮source⟯, and ⟮drain⟯.
FET  Field-effect transistor
MOSFET   metal–oxide–semiconductor field-effect transistor
CMOS|Complementary metal–oxide–semiconductor
MOSFET is the most common type of FET.
most ICs that use MOSFETs are manufactured with CMOS

today, most ICs are made with CMOS-manufactured MOSFETs

### logic gates

Logic gates are made up of a few transistors in a specific arragnement (depending on the gate).

XOR|✫sm_120px-XOR_ANSI_Labelled.svg.png✫
XNOR|✫sm_120px-XNOR_ANSI_Labelled.svg.png✫
OR|✫sm_120px-OR_ANSI_Labelled.svg.png✫
NOT|✫sm_120px-NOT_ANSI_Labelled.svg.png✫
NOR|✫sm_120px-NOR_ANSI_Labelled.svg.png✫
NAND|✫sm_120px-NAND_ANSI_Labelled.svg.png✫
AND|✫sm_120px-AND_ANSI_Labelled.svg.png✫

Either NAND or NOR gates could be used to create any possible logic circuit since they are functionally complete 
Today, NAND is the most commonly used logic gate, since it's functionally complete and can be built with few trasnistors

### circuits

A ⟮logic circuit⟯ consists of interconnected logic gates.
A combinatorial logic circuit is one whose output only¬ depends on its input.
A sequential logic circut is one whose output depends on its input, and the previous state.

## processors

### architecture

A stored-program computer stores data and instructions in the same way.
The VNA implements a stored-program computer.
VNA: CPU = CU + ALU
In the VNA, the CPU, memory and IO are connected to/via the bus.

flex-container:✫sm_tmp_xpihn7q.png✫
In the (modern revisions of) von neumann architecture, the three buses are the ⟮control bus⟯, the ⟮address bus⟯, and the ⟮data bus⟯
Stored-program computers can present a security risk due to the fact that data can contain maliscious instructions.

The harvard architecture separates instructions and data (= does not store them in the same way/treat them differently)
Modern processors are claimed to be stored-program computers (specifically VNA), but since they separate data and instructions to a certain extent, they may be considered modified Harvard architecture to a certain extent.

### electronics

#### integrated ＆ discrete circuits

IC = integrated circuit
an integrated circuit is a set of electronic circuit on a piece of semiconductor material.
A chip is the piece of semiconductor material on which an integrated circuit is realized.
Today, the chip is almost always made using silicon.
The opposite of an integrated circuit is a discrete circuit.
A discrete circuit is a 'traditional' circuit, i.e. a circuit made up of different parts.
ICs are orders of magnitude faster, smaller, less power hungry, etc. than discrete circuits.

#### processors

A processor is any circuit that performs operations.
A processor core is a self-contained processing unit.
A processor can potentially consist of multiple processor cores.
A microprocessor is a processor implemented on an IC.
Almost all modern processors are microprorcessors.

A SoC is a IC that doesn't just include the CPU, but also other components, such as the GPU, memory, radio modems, etc.
As time has been progressing, more and more things have been moving onto the SoC.
moore's law is the observation that the number of transistors in a IC doubles ⟮every two years⟯

### CPU

CPU = central processing unit

CPU is often used in three different senses: The whole unit executing instructions, potentially consisting of multiple CPU cores, a CPU core, or even the whole SOC, potentially containing the GPU, modems, etc.
to differentiate, I will call CPUs in the sense of a self-contained processing unit CPU/processor cores.
to differentiate, I will never call SOCs CPUs (if I can avoid it.).
to differentiate, I will call the main processor, potentially consisting of multiple CPU cores, a CPU.
A multi-core processor is when the chip contains multiple CPU cores.

#### registers

A processor generally has between 10-100 registers.
There are many different kinds of registers:
register|contains
General Purpose Registers|mostly whatever you like
Register: Stack Pointer|stack pointer
address register|memory addresses
data register|binary data
accumulator|intermediary results of a calculation
status/flag register|status flags for the outcome of operations

status register = flag register

The flag/status register might hold flags such as 
zero flag|ALU calculation was zero
overflow flag|ALU calculation resulted in result larger than word size
sign flag|ALU calculation resulted in negative number

Program counter (PC) is also called Instruction Pinter (IP)
The Instruction Pointer/Program counter is a register that contains the memory address of the next instruction.
The instruction Register contains the current machine language instruction (opcode + operands)

Instead of a single accumulator, modern processors generally have many registers that can be used as accumulators.

#### ALU

ALU  Arithmetic logic unit
https://upload.wikimedia.org/wikipedia/commons/0/0f/ALU_block.gif
the ALU is a combinational logic circuit.
The ALU performs arithmetic and bitwise operations.
A basic ALU takes two imputs and returns an output, generally all of the word size of the encapsulating CPU.
A basic ALU, besides its two inputs and an output, has a status flag input and output as well as an opcode input.

##### Adders

An adder is a logic circuit (I think?) that chains logic gate to perform addition.
Adders are used within the ALU.
A half-adder adds two binary digits and outputs a sum and a carry.
A full adder is like a half-adder, but also takes a carry-in.
A half and a full-adder ouptuts an output of size 2 bit.
Chaining full adders allow us to do arbitrary large binary addition.

#### CU

CU  Control Unit

### machine code ＆ instruction set

Assembly language is largely syntactic sugar for machine code.
Machine code consists of machine language instructions.
Machine code and thus machine language instructions are what run directly on the processor, at least in the classical model.
In fact, by now, there is often a layer below machine code known as microcode.
opcode is short for operation code
Within a machine language, an instruction is defined by an opcode.
Within a machine language, an instruction consists of the opcode it is defined by, plus zero or more operands.
An instruction set architecture defines the instruction set plus a bunch of other processor features (such as registers, addressing, I/O) (however, the two terms are often also used interchangably)
The instruction set is the set of operations a processor supports, which bit sequences represent which  machine language instructions, and how the arguments are organized.
Depending on the instruction set, machine langauge instructions may all be the same length or not.
In a general sense, a word is the fundamental unit used by a processor of a given ISA ≈ how many bits a PU may address at once.
The length of a word is the word size.
In general, most registers are word-sized, as are memory cells.
The largest possible memory address is also word-sized (since otherwise, how would you address them) .
what is 32 bit in a 32-bit processor and 64 bit in a 64-bit processor is the size of memory addresses and thus the ⟮the word size⟯

A Load-store architecture is a type of instruction set architecture which only has instructions that either do ALU operation ⟮access (load/store) memory⟯, never at the same time.
For a load-store architecture, all things being operated on must be in registers.

The machine code of a program depends on the ISA, but also on other things about the computer (e.g. OS)

arch with no args prints the current ISA family
the arch command can be made to run programs on other ISA families via arguments.

#### Instruction-level parallelism

Instruction-level parallelism is the parallel execution of instructions of a single thread (thus it is different from concurrency).
In general, the goal of instruction-level parallelism is to keep all of the processor busy
fors of instruction-level parallelism include Instruction pipelining, Out-of-order execution + register renaming, speculative execution + branch prediction.
Instruction pipelining attempts to keep every part of the processor busy with some instruction by dividing incoming instructions into a series of sequential steps (the eponymous "pipeline") performed by different processor units with different parts of instructions processed in parallel.
Out-of-order execution executes instructions as resources are available, rather than the order in the program, if this is possible.
register renaming is a technique that abstracts logical registers from physical registers.
Register renaming allows us to eliminate false data dependencies coming from write after read dependencies, enabling more out-of-order execution.
If compilers did not reuse registers, register renaming would not be necessary, however this is often difficult in practice.
speculative execution is executing instructions before we know if they will be needed
speculative execution is worthwhile if the cost of waiting until we know if the instructions will be needed to be executed is higher than the cost of speculatively executing.
speculative execution is most commonly referred to in the case of instuction pipelining, but may also be performed in many higher-level tasks.
speculative execution (in processors) is most often performed in the case of control flow, where branch prediction is often used to try and guess which branch is most likely.

##### RISC instruciton pipelining

Instruction fetch › Instruction decode and register fetch › Execute › Memory access › Register write back 

#### Hazards

In processors, a hazard is when the next instruction cannot execute in the following cycle, or doing so would lead to an error.
Data dependence is when an instruction depends on the data of the preceeding statement.
Data hazards ocur when instructions exhibit data dependence modify data in different stages of a pipeline, potentially leading to race conditions.
Three type of data hazards:
read after write, write after read, write after write.
read after write is a true dependency: it cannot be resolved.
write after write is an output dependency: it can be resolved by just anulling the first write.
write after read is an anti-dependency, it can be solved by register renaming.

#### RISC CISC

RISC  Reduced instruction set computer
CISC  Complex instruction set computer

The design goals of RISC and CISC are different: while CISC tries to use as few lines of assembly as possible and thus uses more complex, featureful instructions that take multiple clock cycles, RISC uses simple instructions that only take a single clock cycle to be quick.

##### CISC

x86 is a family of instruction set architectures
x86 are the most common type of CISC architectures.
x86 architectures with 64-bit word size are called x86_64
x86_64 may also be called AMD64 or Intel 64
the architecture is called x86 b/c the first processor with it was the Intel 8086.
CISC is the dominant architecture on desktop/laptops as of 2020, though it is slowly changing

##### RISC

ARM is a family of instruction set architectures
ARM ISAs are the most common type of RISC arcchitectures.
While PowerPC was also a RISC ISA and was widely used in all sorts of products, RISC largely became mobile/embedded-only in the mid 2000s until 2021, with apple's switch to ARM RISC processors and their use in in e.g. the worlds most powerfull supercomputer 富岳.
RISC chips generally have far lower power consumption than CISC chips.
Most but not all RISC ISAs, including ARM and RISC-V, are also load-store ISAs.
CPI = clocks/cycles per instruction
In general, a RISC ISA has 1 CPI, with fixed-length instructions.
⟮RISC-V⟯ is a ⟮RISC⟯ instruction set architecture that is ⟮open source⟯.

### cache

processor caches are used to speed up memory access, which is especially important since processor memory is orders of magnitude slower than processing speed.
The cache levels that are common as of 2021 are L1, L2 and L3 cache, with L4 cache slowly becoming more common.
L1 cache is the fastest cache level, and it goes downwards from there
Multi-level caches are caches that are composed of different cache levels.
The organization of multi-level caches into faster/slower cache levels is known as the cache hierarchy.
processor finds memory location in cache   cache hit
processor does not find memory location in cache   cache miss
When a cache miss occurs, the processor generally needs to wait while the data is being fetched
the ⟮Cache replacement policy⟯ is the policy that decides what to 'evict' on having to add something new to the cache on a cache miss

### clocking

A clock signal ⟮coordinates/synchronizes the circuits⟯ the circuits of the thing it's governing.
A clock signal is usually a square wave with a high and low state.
In relation to the clock signal's square wave the circuits activate on ⟮on one (or both) of the (vertical-ish) edges⟯, depending on the implementation
⟮A synchronous circuit⟯ is a circuit where the changes are synchronized by a clock signal.
processors are (made of) synchronous circuits
DDR  Double data rate
⟮DDR (double data rate)⟯ is the technology that activates the circuit. both on the rising and the falling edge of the clock signal

## chipset


flex-container:✫sm_chipset.svg✫
The chipset is responsible for data flow between the processor, memory and other components
In the past, the northbridge and southbridge made up the chipset.
The northbridge controlled/connected the faster components such as the CPU, memory, PCIe.
the southbridge controlled/connected IO, PCI/AGP.
When they still existed northbridge and the southbridge were connected.
Over time, more and more of especially northbridge chipset functions moved onto the SoC, and so the chipset is as of 2020 generally just one chip. 
Slowly, even the functions of the one chip left of the chipset are moving onto the SoC itself.

## assembler

Why don't we just write programs in machine code/assembler?  extremely mühselig and error-prone
Today, assembler/machine code is almost always generated by compilers/interpreters/etc.

## scheduling

scheduling is the action of assigning resources to perform tasks.
In the context of processors, scheduling is the assigment of processor cores to execute threads.

# layering on hardware 

firmware is software that is hard to change, often because it's physically built in.
BIOS and UEFI are both firmware, though BIOS is firmer.

## hardware interfaces

ACPI  advanced configuration and power interface
ACPI is a low-level interface to the power hardware of the computer, allowing for power management; it is currently the standard for that purpose.
ACPI executes the requests it gets as bytecode, acting like black box, and thus presenting a built-in security risk.
The ACPI exposes its interface as ACPI tables.
The Windows Platform Binary Table is an ACPI tible that allows software to persist even beyond reinstalls.
The Superfish vulnerability was enabled by the Windows Platform Binary Table.

## booting

Booting comes from bootstrap load, which itself comes from the idea of pulling yourself up by your bootstraps.
Booting is initializing the computer.
The difficulty of booting is how do you get the computer into a state where it can execute stuff without being able to execute stuff.
has ended when the OS has reached a certain state.
When the user presses the power button, the computer, and especially the CPU gets power, and executes a hardcoded JUMP fo a place in ROM (or a specific place in normal secondary memory) where the BIOS/UEFI sits (though some non-x86 ISAs may do it differently)
All x86 processors start in real mode, which has the features the intel 8086 had, with 20 bit addresses addressing memory non-virtually - this allows for backwards compatibility.

### BIOS/UEFI

UEFI  Unified Extensible Firmware Interface
BIOS  Basic Input/Output System
The BIOS/UEFI comes preinstalled.
The BIOS stores its setting in nonvolatile BIOS Memory (also inaccurately called CMOS).
One of the more important thing stored in nonvolatile bios memory is boot device priority.
UEFI stores its settings in NVRAM.
Once the BIOS/UEFI is loaded, it typically performs a POST
POST = power-on self-test
POST tests for and initializes connected peripherals.
after BIOS/UEFI are finished, they load the first-stage boot loader.
BIOS loads the first-stage boot loader by looking for the boot sector on the boot device, from then on BIOS is no longer involved in booting.
BIOS is a simple de-facto standard, UEFI is a far more complex actual standard.
UEFI loads the boot loader directly, without using a boot sector.
UEFI has largely replaced BIOS as of 2020.
UEFI is controlled by a large set of industry stakeholders known as teh UEFI forum.
CSM (UEFI context)  Compatibility Support Mode
CSM is the mode of UEFI that makes it similar to BIOS by loading MBR or something from the first-stage boot loader.

to manipulate the UEFI boot manager from linux, use the command efibootmgr
-o/--bootorder|change the boot order

#### SMBIOS

DMI  Desktop Management Interface
The original common inteface for managing components of a computer was teh DMI, but it was end-of-lifed in 2005
SMBIOS  System Management BIOS
Originally, the SMBIOS interacted with the DMi
The SMBIOS provides an interface for accessing BIOS/hardware info.
CLI command for interacting with SMBIOS (formerly with the DMI): dmidecode

### boot loader

MBR  Master boot record
The boot sector is typically one sector large
If boot sectors are still used, what sits in them is the first-stage boot loader.
Boot sectors were/are usually in the beginning of the drive
The MBR is 512 byte large, which used to be the size of the boot sector into which the MBR needed to fit.
The main purpose of the first-stage boot loader is to load the second-stage bootloader.
MBR consists both of a first-stage bootloader and a partitioning table.
THe second-stage boot loader, perhaps after some user choosing, loads the kernel.
When using GRUB, all the boot sector contains is a pointer to the next boot stage.
When using GRUB, the boot menu that allows you to choose the os is loaded in the second stage of the bootloader.

## the OS

### the kernel

Primary memory is often divided into kernel space and user space, mainly for security.
Kernel stuff runs in kernel space while user prcesses runs in userspace.
Monolithic kernels do more stuff in kernel space than micokernels.
Instead of doing stuff in kernel space, mircokernels provide servers that do things in userspace.
The daemon responsible for paging (swapper/sched) is the process with PID 0.
A system call is a request to the kernel of an OS.
system call → syscall. 

Drivers run in kernal space.
Drivers expose a well-defined interface of the hardware to the OS, but otherwise act as a black box.

### the init process

The init process is launched by the kernel.
In unix, the init process is the first processes that launches when a computer boots.
The init process is a daemon and has PID 1.
older *nixes|init
newer linuxes|systemd
macOs|launchd

# security

# authentication

## nonce

flex-container:✫300px-Replay_attack_on_hash.svg.png✫
Nonce (short for number once) is a number (generally random) that can only be used once in a cryptographic communication, to make sure an attacker can't repeat a data transmition (called a replay attack)ground

# attacks

### XSS

XSS  Cross-site scripting
Cross-site scripting (XSS) is a code-inejction attack where malicious client-side scripts are injected into web pages being viewed by users



# OSs

# global

OS|Operating System
roughly, the OS could be considered the layer between hardware and programs

## userland

### clipboard

clipboard-cli is an npm package that exposes the command clipboard which works as a shell filter for the clipboard, copying or pasting as needed.
xclip allows interaction with the X clipboard
A clipboard manager is a computer program that adds functionality to an operating system's clipboard.
Many clipboard managers allow the pinning of items, in maccy with ⟦⌥⟧ ⟦p⟧
Maccy is a FOSS clipboard manager for macOS.

### screen selection

slop|queries for a selection from the user and prints the region to stdout
maim|screenshot-taking-utility

slop or maim -s 
-t float / --tolerance=float   How far in pixels the mouse can move after clicking, and still be detected as a normal click instead of a click-and-drag
-t 9 999 999 / --tolerance=9 999 999 (spaces only for readability)   force the selection of a window (by cursor)

maim
-i string / --window=string   cature the desired window (name could be gotten dynamically via various x utilities for example)
-g string / --geometry=string   capture the selected geometry rect

### backups/snapshots

rsnapshot|Rsync based snapshot utility

### notifications

Spec for how notifications should work on linux   Desktop Notifications Specification
libnotify is the most common implementation of the Desktop Notifications Specification
To use libnotify, you need to also install a notification server/daemon.
dunst is a minimal notification server/daemon.
to send notifications on linux, you can use the CLI notify-send.

### fonts

⟮FontBook⟯ is the ⟮mac⟯ GUI for ⟮font handling⟯. 
For ⟮manual font installation⟯ on mac, you can ⟮copy them⟯ to ⟮/Library/Fonts⟯ or ⟮~/Library/Fonts⟯ 

### text expanders

Text expanders are programs which allow OS-wide macros.
espanso is a FOSS cross-platform expansion manager.

#### espanso

##### config files

espanso config files are YAML flies.
The basic unit of espanso is the match.
Matches are contained in an espanso config file in the array matches.
the default config file is `default.yml`
Espanso allows breaking up its config into multiple files.

###### multiple component configs

Any component config file of espanso should have a top level `name` key.
In a component config file, `parent: default` merges it into the generic config 'namespace'

####### app-specific config

To apply certain config files to only certain apps, use app-specific configurations.
App-specific configurations use one of three top-level config keys {`filter_title`, `filter_exec`, `filter_class`}
Any app-specific config key takes a string or regex and addtionally allow the vertical bar to provide a list of applications
To help detect the filter_whatever, expanso comes with the command line util espanso detect

table:key|function|platform
filter_title|current window title|win, mac (uses app identifier), linux
filter_exe|application's executable path. For example, C:\Programs\Telegram.exe|win, mac, linux kinda
filter_class|window class|only usefully linux

##### global config

the global config key auto_restart specfies whether espanso should restart on config change
the global config key backend specfies how the insertion takes place and takes the values {Clipboard, Inject, Auto}


table:backend|function
Clipboard|works like pasting
Inject|works like keypresses
Auto|linux only autochoosing

##### match structure

###### basics

The main two fields of an espanso match are `replace` and `trigger`.
`trigger` represents the thing that will be replaced by `replace`.
when you have multiple triggers, pass an array to `trigger⁑s⁑`
Within `replace` one can determine the cursor position after via `$|$`

###### other match related properties

If you specify `word: true` on  a match, it will only match if surrounded by word boundaries.
The propagate_case property of a match will match on and preserve any case, so that "alh" will expand to "although", "Alh" will expand to "Although" and "ALH" will expand to "ALTHOUGH"

###### image matches

Image matches have an `image_path` instead of a `replace`.

###### vars

the vars array of a match contains vars for that match.
Each var has at least a key `name` identifying it and a key `type` indicating the type of variable.
One can refer to any var within `replace` by `{{‹name›}}`
Any further specification of an espanso variable goes into the `params` key.

####### globals

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

####### date

The `date` type for espanso allows outputting formatted datetimes using rust's chrono as the backend.
`params.format` for espanso's `date` type takes a format string

####### script

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

####### shell

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

######## env vars

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

####### random

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

###### forms

When using espanso forms, ctrl (yes, really) enter to submit on mac.
When using forms, instead of using `replace`, we instead use `form`.
Espanso's `form` key includes a string with blanks signified by the usual {{‹name›}} syntax
Espanso allows customization of its form fields via the `form_fields` mapping.
The `form_fields` mapping can have a key for each blank in the form, I will be calling each of these a field specifier.

####### field specifiers

field specifiers, similar to vars, take a `type`.


table:field specifier `type`|function
text|text only
choice|dropdown menu
list|list box

any field specifier that allows multiple choices takes these choices as a `choices` array

using espanso, I've created an expansion that uses `!!!` to run an arbitrary shell command and insert the results

##### caveats

espanso does not source any of the usual files and so doesn't get any environment variables.
espanso also doesn't seem to set any LANG or LC variables, which may cause some issues.

### jobs

A ⟮job⟯ in computing is ⟮a thing to do⟯, generally ⟮scheduled⟯, and generally ⟮in the background without intervention⟯.
⟮Batch job⟯ is r⟮oughly synonymous⟯ to ⟮job⟯, though it ⟮more strongly implies⟯ ⟮the scheduled⟯ and ⟮in the background without intervention⟯ parts, and also the idea of ⟮there being quite a few things to process⟯.
⟮Batch processing⟯ is ⟮processing (batch) jobs⟯.
A ⟮set of jobs to be run together⟯ in ⟮a certain order⟯ is ⟮a job stream⟯.
A ⟮job⟯ in computing ⟮consists of⟯ ⟮one or more tasks/steps⟯.
A ⟮job scheduler⟯ is an application for ⟮controlling⟯ ⟮the scheduling⟯ of ⟮the execution⟯ of ⟮jobs⟯ (which is ⟮unattended⟯, ⟮in the  background⟯).
The ⟮job queue⟯ is ⟮where tasks are put⟯, and is what ⟮the job scheduler manages⟯.

#### cron ＆ at

⟮cron⟯ and ⟮at⟯ are ⟮job schedulers⟯ for unix-likes.
⟮cron⟯ is for ⟮scheduling repeated tasks⟯, while ⟮at⟯ is for ⟮scheduling one-time tasks⟯.

##### crontab

the ⟮job scheduler cron⟯ is ⟮configured by⟯ ⟮a crontab file⟯.
the ⟮crontab⟯ is interacted with by ⟮the crontab command⟯.


###### syntax

In cron, ⟮each job⟯ is defined by ⟮a line in the crontab⟯, which consists of ⟮times to execute a command⟯, and ⟮a command itself⟯.

```
crontab-line ::= (⟮‹time-specifier› ‹time-specifier› ‹time-specifier› ‹time-specifier› ‹time-specifier›⟯⟮|‹time-keyword›⟯) ⟮‹command›⟯
⟮time-specifier⟯ ::= ⟮* ||⟯ ⟮‹time-list›⟯
⟮time-list⟯ ::= ⟮‹time-item›⟯⟮{,‹time-item›}⟯
⟮time-item⟯ ::= ⟮‹time›-‹time›⟯⟮||(‹time›|*)/‹time›⟯⟮||‹time›⟯
```

###### time specifiers

cron time item|refers to
⟮*⟯|⟮all relevant time units⟯
⟮‹n›-‹m›⟯|⟮specifies a range of times n-m⟯
⟮*/‹n›⟯|⟮every nth unit⟯


*|*|*|*|*|‹command to execute›
⟮c+;s∞;minute (0-59)⟯|⟮c+;s∞;hour (0-23)⟯|⟮c+;s∞;day of month (1-31)⟯|⟮c+;s∞;month (1-12)⟯|⟮c+;s∞;day of week (0-6) (Sunday is 0)⟯


crontab job line example|does
⟮@reboot [command]⟯|⟮every time your computer reboots⟯
⟮30 2 * * * [command]⟯|⟮every day at 2:30 am⟯
⟮15 * * * * [command]⟯|⟮every hour (at :15⟯)
⟮0,10,20 * * * * [command]⟯|⟮every hour at :00, :10, :20⟯
⟮0 5-10 * * * [command]⟯|⟮every day at every hour between 5 and 10⟯
⟮0 0 2 * * [command]⟯|⟮every month on the 2nd at 00:00⟯
⟮0 * * * 1 [command]⟯|⟮every hour, but only on mondays⟯
⟮0 * * * * [command]⟯|⟮every hour (at :00⟯)
⟮*/5 * * * * [command]⟯|⟮12 times an hour (every 5 minutes⟯)
⟮* * * * * [command]⟯|⟮every minute always⟯

###### output

By default, ⟮the output⟯ of ⟮a cron job⟯ gets ⟮sent to your email⟯.
To ⟮change the email⟯ ⟮cron output gets sent to⟯, specify ⟮MAILTO=somemail.⟯
To ⟮change where⟯ cron output ⟮goes⟯, ⟮redirect it as per usual⟯.

## kernelland

## installation

A live OS is a bootable OS on some kind of removable device.
A live OS typically also allows installation of the OS and may be the main means of installing an OS
A live USB is a live OS on an USB stick.
A live CD is a live OS on a CD.
Unetbootin is a cross-platform untility for creating bootable USBs

## virtualization

Virtualization is creating something virtual instead of something real.
For the isolated execution of programs, generally either virtual-machine-based virtualization or os-level virtualiztion is used.
A virtual machine is a form of virtualization where an entire operating system is virtualized.

### OS-level virtualization

OS-level virtualization is where multiple isolated user space instances exist on the same OS.

#### chroot ＆ chroot jail

chroot changes the root directory of a process, preventing it from changing anything outside.
A chroot jail is the environment set up by chroot.
Often, the basis of OS-level virtualization is a chroot jail.

#### containerization

Containerization is (is an implementation) of OS-level virtualization, which generally refers to specifically using OS-level virtualization for running one app, including all its dependencies and its own fs.
Using OS-level virtualization/containerization, interactions with the larger OS is only allowed through limited, specified channels.
An application being contained in a container is said to be containerized.
Containerization improves security and portability.
Containerization is the standard for most mobile operating systems.
Containerization may limit functionality and increase size (since dependencies cannot be shared)
Docker is the most common service for os-level virtualiztion/containerization.

##### docker

In docker, a container is an instance of a container image.
A docker container can be run pretty much anywhere.
A container image contains everything needed to create the container, including the file system, all dependencies, and config.

the command `docker` is used to administer docker.

## communication between OSs

scrcpy is a program that provides display and control of android devices from the computer via USB or the internet(TCP/IP).

# mac

# windows

## misc

Right-clicking the ⟮windows start button⟯ brings up a ⟮context menu⟯ with ⟮a bunch of system tools⟯ 

# *nix

## different *nixes

### POSIX

The Portable Operating System Interface (POSIX) is a family of standards specified by the IEEE Computer Society for maintaining compatibility between operating systems.
POSIX specifies both kernel- and user-level APIs as well as various shells and utilities.

### differences

Different *nixes have different versions of different command-line tools, on account of having descended in different ways from the original unix.
coreutils are the basic GNU file, shell and tex manipulation utilities.
the GNU versions of basic command-line tools is generally more featureful than other versions.
the GNU versions of basic command-line tools is generally the one that is assumed e.g. online.
You can install the GNU coreutils on non-GNU systems via homebrew.
If there is also a preexisting version of the command when the GNU coreutils are installed with homebrew, they are prefixed with g (e.g. gdir instead of dir).
If you need the normal names of the GNU coreutils when installed with homebrew (e.g. because they're being used in a preexisting script etc, add the directory they're in (/opt/homebrew/opt/coreutils/libexec/gnubin) to your $PATH

### what's in a *nix

#### GNU/Linux

GNU is the set of free software that accompanies the linux kernel in GNU/Linux.
GNU = GNU's not unix
The GPL was originally created for GNU
(GNU) GPL = GNU General Public License
Linux technically refers to the Linux kernel.
GNU software set + Linux kernel = GNU/Linux
Often, Linux alone is used (technically incorrectly) to refer to GNU/LInyx

A Linux distribution is GNU/Linux plus a set of other stuff, which depends on the flavor.

Android uses the Linux Kernel but not GNU or any of the other libraries.
From ⟮android⟯ ⟮1.0⟯ until ⟮9⟯, ⟮android⟯ versions had ⟮sweets⟯-based names, with each name ⟮going one further in the alphabet⟯

##### WSL

WSL = Windows Subsystem for Linux
The Windows Subsystem for Linux is a Linux VM/compatibility layer for Windows
The Windows Subsystem for Linux allows you to do things like run a shell environment of linux on windows, and even X11 applications
To install the Windows Subsystem for linux, turn it on in the "Turn windows features on or off" dialog, then download the distro from the windows store
The windows drives with letters C, D, ... are accesible from the WSL as /mnt/c, /mnt/d ...

#### Android

⟮Android features⟯ depend on the relevant ⟮API level⟯, which starts at ⟮1⟯ and is at ⟮30⟯ as of android ⟮11⟯ 

Curreny android has one ⟮API level⟯ per ⟮major version⟯ (e.g. ⟮android 11⟯), but it used to be ⟮multiple ones per version⟯ (bc in the past ⟮minor versions⟯, e.g. ⟮2.2.⟯ Gingerbread and even ⟮patch versions⟯, e.g. ⟮2.2.3⟯ Gingerbread ⟮introduced new features⟯) 

### libraries ＆ systems

#### linux

##### input

On Linux, input devices are often handled on linux by the library libinput, which is also the name of the command used to interface with it. 
libinput is native in wayland, but optional in X, which can also manage input devices directly, whose implementation you can interface with via xinput.

##### grapical display ＆ related systems

pango is a linux library for international text rednering.

###### X

the X window system is the whole thing with X servers, X clients, an X server, X11, ...
The core part of the X window system is the X server.
the Xorg X server is the main implementation of the X Server
by default, the X server handles displays and kb/mouse.
When something of interest happens, the X server sends events to its clients.
The X server handles the actual displaying to the display.
If one wants to display something using X, one sends an request to the X Server.
X11 is the communication protocol of the X window system.
X clients are things such as individual applications.
X clients may be anywhere, including on another computer.

X thingies installed by default live in /usr/share/X11
X local config changes live in /etc/X11
xorg is configured in X11/xorg.conf(.d)

####### window manager

In Unix, a window manager handles window management.
to the X window system, the window manager is just another client.
A window manager does things such as resizing, minimizing, closing
wmctrl   Manage an X window manager
A desktop environment is a window manager plus a set of base applications and some other stuff such as a clipboard manager, toolbar, etc.
Well-known desktop environments are GNOME, KDE, XFCE, Unity...

####### starting X

startx is a wrapper around to xinit.
xinit/startx source .xinitrc when run.
.xprofile and /etc/xprofile is run by X before your window manager is run.
.xsession is (at least in theory) only sourced when logging in from a display manager

####### Login

A X display manager is a graphical login manager which starts a login session on an X server.
the GNOME X display manager is gnome's display manager.
GDM = GNOME display manager
LightDM is the most common alternative to GDM.

####### DE

D-Bus is a protocol/interface/middleware for messaging between processes (IPC).
AccountsService is a D-BUs service for accessing the list of user accounts and information attached to those accounts.

What Desktop Environment you're using   XDG_CURRENT_DESKTOP
What Desktop Environment you selected from the display manager (might be limited to gnome display manager)   GDMSESSION

####### CLI

xdotool allows automation of X windows
xdpyinfo gets info about an x server
xwininfo gets information about open windows
xev shows X events such as keyboard, resizing, clicking etc.

##### systemd

In SystemV style init, the init process was actually called init.
In SystemV style init, the device starts by executing numbered startup scripts one at a time.
Because SystemV executes startup scripts one at a time, it is relatively slow.
SystemV style init has largely been replaced by systemd, though the switch was recieved largely negatively.
In contrast to SystemV init, systemd is not composed of scripts, but of large, precompiled binaries.
In contrast to SystemV init, which was just the init process, systemd is additionally a huge architecture managing may parts of the OS.
systemd targets replaced SystemV runlevels.
When systed has bootstrapped itself, it next looks at default.target

within the relevant systemd folder (/var/systemd, /etc/systemd, /run/systemd), system is the directory that contains the unit files.
There are different systemd folders depending on the persistence that is desired, and the origin of the modification.
/run/systemd|lost at reboot
/lib/systemd|persitent (package-manaed software, the os)
/etc/system|persistent (device admin)

###### units

systemd deals with system units.
A systemd unit represents any kind of system resource.
systemd units contain dependencies to tell us what we need to load first.
Systemd units end .unittype.
an instance of a systemd unit is denoted by ‹instance-name›@‹unitname›.‹unittype›
Systemd units are stored in unit files.

.timer   timed functionality similar to cron
.target   a state to be reached
.socket   sockets
.service   Managing some kind of service
.mount   predefined mount points
.automount   .mounts that will be automatically managed
.path   notifying when a path becomes available

When a .path units path becomes available, ⟮an associated .service⟯ is started.
When a .socket unit has some activity, an associated service is started.
When a .timer units time state is reached, an associated unit is started.

####### targets

reboot.target   The target for rebooting
poweroff.target   The target for turning off the computer
multi-user.target   multiuser (but no GUI)
graphical.target   multiuser ⁑with GUI⁑
default.target   what the machine should try and aim for when booting (another target generally)

####### CLI

Passing systemctl a target (such as reboot) without the .target will execute that target
The main command to administer systemd is systemctl
starting/stopping an unit for systemd does that ⟮right now⟯ but temporarily
enabling/disabling an unit for systemd does that ⟮next reboot/session (by default)⟯ but permanently.
To both start and enable/stop and disable, use enable/disable --now.
syntax: systemctl (start|stop|enable|disable) ‹unit›
To see if a thing is currently enabled or active, use is-enabled/is-active ‹unit›
reload ‹unit› reloads a specific unit.
reset-failed resets all failed units
daemon-reload refreshes changed systemd settings
The systemctl subcommands list-* lists relevant systemd-related things, however there is not a list-unit subcommand for every unit.
list-sockets|list sockets and what happens
list-jobs|list active systemd jobs
list-units|list all units
list-unit-files|list unit files

when using systemctl, if not specifying a suffix, it will assume .service
when using systemctl, for mount/device operations, besides using .mount and .device names,  you can use the respective paths (e.g. /dev/sda2)

loginctl controls the systemd login manager
systemd-analyze allows for systemd debugging

##### various subsystems ＆ specs

###### NetworkManager

NetworkManager aims to provide an 'it just works' type network epxerience for linux
NetworkManager stores its saved connections in /etc/NetworkManager/system-connections/

###### bluetooth

The most common low-level bluetooth stack for linux is bluez
hcitool is a command allowing noninteractive bluetooth config.
bluetoothctl is a command allowing interactive commincation with bluetooth.
As of 2021, bluetooth on linux is still pretty buggy.
Bluetooth high-level-ish management software on linux: blueman, blueberry, bluedevil

###### sound

Linux's reasonably low-level sound interface is ALSA.
ALSA|Adavance Linux Sound Architecture
amixer is a command to control alsa.
PulseAudio is often layered on top of ALSA
pactl is a command to manage pulse audio
in linux soudn jargon, an output is a sink

###### language

ibus and fcitx are linux frameworks for multilingual input
mozc is a plugin for ibus/fcitx/whatever for japanese input.
ibus-daemon is the command for managing ibus
fcitx-configtool allows managing fcitx graphically.

#### state change

`shutdown`|shutting your system down
reboot|restart your computer
shutdown{ ‹option›}[ ‹shudown-time›][ ‹wall-message›]

caffeinate creates assertions to alter system sleep behavior. 
If no assertion flags are specified, caffeinate creates an assertion to prevent idle sleep.  
If a utility is specified with -u, the caffeinate assertions will persist for the duration of the utility's execution. 
if no utility is specified with -u, caffeinate creates the assertions directly, and those assertions will persist until caffeinate exits, or until the timeout specfied w/ -t.

### leaving the shell

termux-open-url   open an url in its default application (termux)
termux-open   open something it its default application
`⟮open⟯` ⟮opens⟯ ⟮files/folders⟯ and ⟮urls⟯ with ⟮the default application (or one you specify⟯) 
⟮xdg-open⟯ is then X equivalent of ⟮macOs `open`⟯ 


`open`
⟮-R⟯|⟮reveals the file in finder⟯
⟮-a someapplication⟯|⟮Specify the application to open with⟯
⟮-e⟯|⟮open the file with textedit⟯
⟮-f⟯|⟮reads from stdin⟯
⟮-t⟯|⟮open the file with your default text editor⟯


### misc

`redshift`|make screen red/yellowish (linux)

set color temperature    `-O temp `
reset color temp   `-P`

`nightlight`|make screen red/yellowish (mac)

`nightlight status`|show `nightlight` status   
`nightlight on`|enable `nightlight`   
`nightlight schedule`|manage `nightlight` schedule   
`nightlight temp`|show current `nightlight` color temperature (with arg: set it)

CLI tool for managing displays|`display_manager.py`
`display_manager.py res`|manage resolutions (display_manager.py)
`display_manager.py res width height`|Set the resolution to width * height (display_manager.py)

date is a tool for showing, formatting or changing date and time
If run without arguments, date gets the current date and time.
date-command ::= date [‹formatting-syntax›|‹setting-syntax›|‹dst-syntax›]
formatting-syntax ::= {‹option›}[ +‹output-format-specifier›]

option|does
⟮-u / --utc / --universal⟯|⟮use UTC⟯
⟮-d date / --date=date⟯|⟮calculate the date for the specific date⟯
⟮-I/--iso-8601⟯|⟮output the date as ISO 8601⟯


Sleep is a command that waits for the specified time.
sleep-command ::= sleep{ ‹number›‹suffix›}
suffix ::= s|m|h|d
for sleep, multiple number-suffix specifier waits for their sum

recode - converts files between character sets
insect - shell scientific calculator

unoconv is a CLI util to convert files using libreoffice in the background.

tee redirects a stream to stdout and to all listed files

## processes

On unix systems, a process is an (instance of a) program that is ⟮running⟯
On unix, a process is the instance that has its own heap.

### process relationshps

IPC|inter-process communication.

PPID|Parent Process ID
PID|Process ID


### process management

ps|list of processes
pstree|processes as a tree

procs is a more fancy version of ps written in rust

### file descriptors

A file descriptor is a positive integer that uniquely identifies a file (or file-like) things.
Each process has its own file descriptors.
The file descriptiors of a single process are stored in their own file descriptor table.
The kernel maps the file descriptors the file descriptor table of a single process to the file table.
The file table is a system-wide table of all open files.
The file table contains reference to the relevant inodes.
Each process has three file descriptors allocated automatically, namely for the standard streams.
the standard streams consist of stdin, stdout and stderr
The standard streams different from other file descriptors is that they are always allocated automatically, and that many mechanisms will use them by default.
stdin   0
stdout   1
stderr   2

using `-` to refer to stdin or stdout is a common convention specified by posiz, but not a feature of the shell or anything else

When you open a file on unixy systems, the kernel creates a file descriptor for the file using (amongst other things) the relevant the inode

### daemons

A daemon is a process running in the background, not under the direct control of a user.
In *nix, a daemon is generally a process which is a child of the init process.
A daemon is usually created either by a process forking a child process and then immediately exiting, thus causing init to adopt the child process, or by the init process directly launching the daemon. 
The names of daemons generally end with d.

### exit codes

true|do nothing, sucessfully (exits 0)
false|do nothing, unsuccessfully (exit non-0)

### process management tools

top is a process viewer.
htop is a more fancy version of top with a better TUI and interactivity.

## terminal system

### job control

job control is mainly performed by signals.
A job is a shell concept, but generally corresponds to a process group.
Jobs mainly exist to be siginalled by signals, all processes in a job are signalled at once.
`^Z` (as keyboard input)   Stop (not kill) the current program
the bg command takes a suspended command (e.g. one that was Ctrl-Z ed) and resumes its execution in the ⁑background⁑
fg  resume stopped task in foreground
bg  resume stopped task in background
⟮c+;＆⟯ at the ⟮end of an command⟯ ⟮puts it in the backround⟯ (but it ⟮still continues running⟯)
jobs|show processes running in the background

### terminal

A terminal may be a physical/hardware terminal, a virtual terminal/console, or a terminal window.
/dev/tty represents the current terminal, regardless of what kind of terminal it is (hardware, virtual, etc.)
the tty command tells us which device file is implementing the current terminal

#### terminal architecture


flex-container:✫file://~/Downloads/terminalsys.svg✫

A physical terminal is connected via cables to an UART driver.
screen, keyboard etc. are connected via drivers to a virtual terminal (not a window).
The UART driver or virtual terminal are connected to the line discipline.
The line discipline may be disabled, in which case the characters are sent directly and instantly to the process, the so called raw mode.
cooked/canonical mode is when the line discipline is enabled, which means that text is only sent to the application after a newline is sent.
cooked = canonical mode
The line discipline is typically disabled for TUI applications or similar and for the shell, which implements its own line discipline.
the line discipline is connected to the tty driver.
The tty driver is passive, while it has fields and methods, they need to be called from outside, e.g. via signals.
the tty driver seems to be the parent process of the session leader.
stty administers the options for the tty driver.
The tty driver is the thing that has all all the processes living in a terminal as descendants (?)

##### physical terminals and terminal emulators

Terminal emulator is properly a synonym for virtual terminal/console, though sometimes terminal emulator is used in the wider sense of 'any thing that emulates a hardware terminal', though I would consider this incorrect usage. Nevertheless, I wil use virtual terminal for this to avoid ambiguity. 
virtual terminal = virtual console.
vt/vc is short for virtual terminal/console.
Virtual terminals are realized by a /dev/tty‹n› file.
/dev/tty‹n› files are provided by the kernel.
Hardware terminals are realized by /dev/ttyS‹n› files (I think)
tty may be a synonym for virtual terminal (since all virtual terminals are realized via /dev/tty‹n›), or as a synonym for any non-pseudo-terminal terminal.
Each physical terminal would have been its own separate thing, and so each virtual terminal is also its completely separate thing.
Virtual terminals occupy the whole screen, they decidedly don't live within a GUI.
/dev/tty0 represents the current controlling virtual terminal.
When in a GUI, /dev/tty0 may be the virtual terminal the window server is running in.
On linux, pressing ctrl + alt + f‹number› switches to tty‹number›
In linux, the window manager lives within a virtual terminal.
Linux typically starts with 6 virtual ternubaks, and then one additional one (tty7) to run the window manager in.
ttys (physical terminals and virtual terminals) are initialized by `getty`, which mainly calls `login`.

each /dev/tty‹n› has a corresponding /dev/vcs‹n› (including /dev/tty0, which means that /dev/vcs0 corresponds to the memory of the current virtual terminal)
the /dev/vcs‹n› contains what is visible on the screen of a /dev/tty‹n›

##### pseudo terminals

A pseudo-terminal consists of two device files, a master file and a slave file.
In a pseudo-terminal, a terminal window such as xterm (or sth like ssh) replaces the virtual terminal. 
In a pseudo-terminal, instead of being connected directly to the line discipline, the thing replacing the virtual terminal is connected to the pseudo-terminal master device file. 
The kernel links the pseudo-terminal master device file (ggf. filtering through the line discipline) to the pseudo-terminal slave device.
The link between pseudo-terminal master and pseudo-terminal slave is full duplex.
The pseudo-terminal slave fulfilles the role that the tty driver would normally, e.g. holding on to processes.
If you input something e.g. to a terminal window, it is written to the pseudo-terminal master device, which is transferred to the pseuod-terminal slave, which redirects it to the relevant process. 
the file /dev/ptmx is the pseudo terminal master multiplexer, which spawns new pseudo terminals.
Opening /dev/ptmx gives you a file descriptor for the master device and spawns a slave device in /dev/pts.
/dev/pts/‹n› represents a pseudo terminal slave.
When sshing, the pseudo terminal master device is connected to your terminal/terminal window/virtual terminal, but the pseudo terminal slave is instead on the remote machine.
The thing that creates the pseudo terminal slave on the remote machine is sshd.

##### system console

In the past, many hardware/physical terminals might have been connected to one computer.
In the past, the system console would have been its own hardware/physical terminal connected directly to the computer.
Today, the system console is merely the device file /dev/console.
In most modern systems /dev/console is merely a symlink to /dev/tty (however it may also point at something else)
In any case /dev/console and /dev/tty have different major numbers.

#### terminal window

A terminal window must be one level of emulation deeper than a virtual terminal, since it lives in a GUI which in linux at least itself lives within a virtual terminal.
A terminal emulated within a GUI is known as a terminal window
Alternative terminal window (mac)|iTerm2
xterm is the classic terminal window for the X window system.
most terminal windows are based of xterm
the default terminal window for gnome is gnome-terminal.
all the various terminal windows generally have a command of the same name to launch them/specify options
most terminal windows take the -e argument to execute the command in the newly opened terminal window.
Termux is a terminal window for android.

#### process interaction with terminals

PGID|Process group ID
SID|Session ID
pgrp|process group

On unix, every process has a parent.
A process group is a collection of one or more processes.
A session is a collection of one or more process groups.
Processes may not migrate between sessions.

To the terminal, the shell is just one more process running within it.

ctty = controlling terminal (doesn't have to be a tty)
A session has one controling terminal.
all processes within a session inherit the controlling terminal via fork()
Signals can only be sent by/via the controlling terminal and only to its forground process group.
The relevant foreground process will have its in/output connected to the tty driver of the controlling terminal.
Any session has exactly one foreground process groups, all other process groups are in the background.
Each session is managed by a session leader.
the shell is the session leader, and is always the process group leader of its process group
The session leader updates the tty driver and does some other admin stuff, e.g. creating new porcess groups for pipelines.
for the process group leader, PGID == PID
for the session leader, SID == PGID == PID


#### signals

signals allow the kernel to communicate asynchronously with a process (group).
The thing that is signalled when being singalled from a terminal is always an entire process group.
In the context of terminals, signals may be sent by/via TTY driver or some other part of the terminal subsystem.
signal names are all-caps and start SIG.
In a terminal, any input, including stuff such as ^Z gets sent to the tty driver (or maybe the line discipline - I'm not quite sure, and people seem to be disagreeing). 
For some key combinations, such as ^Z, the tty driver will not transmit the input, but instead turn this into a signal and send this to the foreground process group.
For some key combinations, such as ^D, the tty driver will not transmit the input, but instead turn this into a different character and transmit this instead.
Other key combinations, including some ^‹char› combinations may merely be passed on to the process.
Ergo some ^‹char› combinations may always send the same signal (but leave it up to the process how to respond to the signal), some ^‹char› combinations may send a different character (which will be treated by that process as that characer), and some ^‹char› combinations will just send ^‹char›, which the process may handle if it so chooses.
You can change which ^‹char› the terminal driver handles how via stty.
^C|SIGINT|tty  driver
^\|SIGQUIT|tty driver
^Z|SIGTSTP|tty driver
^D|EOT/EOF|tty driver
^L|FF|processs|often interpreted as 'clear the screen' (shells) or 'redraw the screen' (curses)

kill sends a signal to a process, given its PID
killall sends a signal to a n processes, given a string that their name contains
by defaut, kill and killall send SIGTERM

#### appearance

Things such as color and cursor movement in the terminal are implemented via control characters.

#### shell commands for terminal management

There are a number of shell commands that nevertheless still are concerned with terminals, and not with shells

##### virtual terminal

fgconsole   get the number of the current tty
fgconsole --next-avaliable   get next unallocated vt
openvt|run a program on the next free vt.
deallocvt   remove unused virtual terminals
chvt N   change to ttyN
Couldn't get a file descriptor referring to the console is an error you encounter using commands meant for virtual terminals somewhere else

##### any terminal 

the who utility displays all active terminal sessions and for each the users logged into them, datetime of login, and hostname if not local.
    sam$ who
    sam      console  Dec  4 01:44 
    sam      ttys002  Jan  9 12:34 
    sam      ttys007  Jan 24 23:26 
uptime -  prints general system stats: time of day, uptime, amount of users logged in, and and the average number of jobs in the run queue over the last 1, 5 and 15 minutes.
w is an extended version of who, which shows everthing who does, plus what is currently running in the terminal and the time since the user last typed anything. w also the stats that `uptime` shows.
    sam$ w
    9:10  up 52 days,  7:26, 3 users, load averages: 2.10 2.05 2.01
    USER     TTY      FROM              LOGIN@  IDLE WHAT
    sam      console  -                04Dec21 52days -
    sam      s002     -                09Jan22  3:34 -bas
    sam      s007     -                Mon23    9:41 -bas

### shell

the shell is typically the foreground process in a given terminal, but may be the background process e.g. if we're using a TUI.
The shell runs in the foreground of a terminal if its being used interactively.
The shell is a special kind of program.
The shell is the interpreter that executes the commands.
For bash, there are two commands that allow changing settings of the shell, set and shopt.
The difference between set and shopt is that set is a POSIX-compliant command originally from the original bourne shell, while shopt is bash-only.
SHELLOPTS|options set via set
BASHOPTS|options set via shopt

#### variants

The first shell, introduced in 1971, was called the thompson shell with the executable sh.
the pwb/masey shell was introduced in 1977 and built on top of the thompson shell, keeping the executable sh.
The bourne shell was introduced in 1979 and also had/has the executable sh.
Today, the executable sh most often is a sym- or hardlink to a different shell, e.g. bash or csh.
csh is a more c-like shell developed from the thompson shell.
tcsh itself is a more advanced version csh.
Today, csh is most often a sym- or hardlink to tcsh.
ash, bash, ksh, and zsh are descendants of the bourne shell.
bash is the shell of GNU, and perhaps the most common shell as of 2020.
bash = bourne again shell

#### history

history can be en/disabled via the history parameter of set.
The history list is a list of commands that the shell internally stores.
the HISTSIZE environment variable determines how much of a the history list will be saved on exit.
the histfile stores the command history as a file. 
The path of the histfile is determined by the HISTFILE environment variable.
For bash, the default history path is ~/.pash_history.
the HISTFILESIZE environment variable detrmines the maximum length of the histfile.
When the shell starts up, the HISTFILE is truncated to HISTFILESIZE and then loaded into the bash history list.
When the shell exits, it saves the last HISTSIZE lines of the history list to HISTFILE, either overwriting the contents, or appeding if the histappend option is set. afterwards, the HISTFILE is truncated to HISTFILESIZE.
If the HISTTIMEFORMAT is set, the time stamp information associated with each history entry is written to the history file, marked with the history comment character. 

The HISTCONTROL and HISTIGNORE variables may be set to cause the shell to save only a subset of the commands entered.

The builtin command fc may be used to list or edit and re-execute a portion of the history list. 
The history builtin may be used to display or modify the history list and manipulate the history file.
With no options, history displays the history list with line numbers.

#### various features

##### The directory stack

in nix, there is a stack of directories called the directory stack.
in nix, you can push/pop from the directory stack with the commands pushd/popd.
pushd not only pushes the specified directory to the stack, but also cds there.
The dirs command shows the contents of the directory stack.
dirs, pushd and popd all take a positional argument +/-‹n›, which do something with the nth directory counting from zero and from the start/end respecitvely
dirs +/-‹n›|display the nth directory counting from the start/end
pushd +/-‹n›|bring the nth directory counting from the start/end to the top of the stack by rotating the stack
popd +/-‹n›|remove the nth directory counting from the start/end from the directory stack (without cding)

#### Prepopulated environment variables

PWD|current directory
OLDPWD|directory before last pwd
DIRSTACK|everything on the directory stack
PAGER|set the pager
HOME|user home directory
BROWSER|web browser

EDITOR and VISUAL are shell environement variables ⟮setting the default editors⟯


command prompt is often just shortened to prompt.
The command prompt is one or more characters indicating the command-line is ready to accept input.
The PS‹n› environment variables set the command promt in different circumstances.
PS‹n› exist from 1-4.
PS1|default command prompt
PS2|prompt for following lines for multiline commands
PS3|options for `select`
PS4|execution of shell script debugging trace (whatever that is)
Bash additionally executes the content of the PROMPT_COMMAND just before displaying the PS1 variable.
for PS‹n›, ash supports a set of \ initiated special escape sequences for things such as the time, hostname, number of current jobs etc.

#### login shell

A login shell is is the first shell that executes after you `login`.
login indicates to the shell that the shell should be a login shell by prepending the name of the shell with a -, so that $0 will e.g. be -bash, not bash.
-l/--login forces bash to be a login shell (in this case), $0 will not be prefixed with -)
In bash, you can also use shopt login_shell to see if bash is a login shell.
On mac, all interactive shells become login shells, meaning that .bashrc is not ever automatically read.
linux can rely on the login shell startup files being executed since the login shell is started before the OS has become interactive
mac cannot rely on the login shell startup files being executed before the first shell has been opened.

#### startup files

pretty much all shells have a set of startup files that they run as normal shell code when starting a new shell.
when bash starts non-interactively, it looks for startup files in the paths listed in BASH_ENV.
when bash starts interactively, which files it reads from depends on if it thinks its a login shell.
if bash is not a login shell, it reads from ~/.bashrc and on some versions of bash also from /etc/bash.bashrc
if bash is a login shell, it reads from /etc/profile, and then exactly one of ~/.bash_profile › ~/.bash_login › ~/.profile
It may be advisable to have one of the files loaded when something is a login shell load .bashrc, to ensure consistent behavior.
When an interactive login shell exits, or a non-interactive login shell executes the exit builtin command, Bash reads and executes commands from the file ~/.bash_logout, if it exists.

There are other files for environment variables that may be read at different times unrelated to the shell: .pam_environment, /etc/environment

#### Shell lifecycle

0. The shell may get its input from a file, a string, or the terminal, and splits it into lines.
1. The shell performs history expansion
2. the shell tokenizes the input
3. the shell parses the input into commands
4. The shell performs expansions
5. the shell performs redirections
6. the commands are executed
7. the shell waits for the commands to complete and collects its exit status

since shell syntax (such as filename expansion) are performed far before something like sudo is executed, if you lack permission to see things those things will not work.
To use shell syntax/features with sudo permissions, the easiest way is to create a sudoed subshell (sudo bash -c "command")

##### whence commands?

###### interactive shell

Bash uses a simple heuristic to determine if the shell is interactive: (if neither an non-option argument nor -c or -s is specified and error/iput are connected to terminals) OR (-i is specified), it is interactive.
While an interactive shell is meant to read/write to a terminal, there is no guarantee it is in a terminal if you force it with -i.
if a shell is interactive, $- will contain i, and $PS1 will be set (otherwise unset).
Interactive shells have a bunch of unique rules and semantics.

####### readline

An interactive shell will typically use the GNU readline library to allow line-editing of entered commands.
While GNU readline is most commonly used in interactive shells, it may be used in may different places.
GNU readline has both emacs and vi editing modes, with emacs editing mode enabled by default.
The emacs and vi arguments for set allow switching between those two modes.

####### tab completion

compgen generates potential autocompletes for a certain string based on its option

###### noninteractive shell

bash -s|read commands from standard input
bash -c|read commands from following string
shell scripts execute in their own shell by default
Unless you force it, the shell a script will execute in is a noninteractive shell.

##### history expansion

history expansion allows us to splice parts of the history list into the current input stream
In history expansion, the line from the history list that is used is called the event.
In history expansion, the parts of the event that are included are the words (broken into words with normal bash tokenization ＆ parsing).
In history expasnion, various modifiers are available to modify words.
history-expansion ::= !‹event-designator›[‹word-designator›]{:‹modifier›}
If the histverify shell option is enabled, and Readline is being used, history substitutions are not immediately passed to the shell parser. Instead, the expanded line is reloaded into the Readline editing buffer for further modification. If Readline is being used, and the histreedit shell option is enabled, a failed history expansion will be reloaded into the Readline editing buffer for correction.
only ‘\’ and ‘'’ may be used to escape the history expansion character, but the history expansion character is also treated as quoted if it immediately precedes the closing double quote in a double-quoted string.
Event designators allow the selection of the event for history expansion.
‹n›|nth command in history list
-‹n›|nth last command from current command
!|last command (synonym for -1)
‹string›|most recent command preceding the current position in the history list starting with string.
?‹string›|most recent command with string before a newline
?‹string›?|most recent command containing string
#|the entirety of the command line as typed so far
word-designator ::= ‹positional-selector›|*|‹integer›*
positional-selector ::= ‹position›[-‹position›]
position ::= ‹integer›|$|^|%
‹integer› corresponds to an index of a word starting at zero
^ and $ corresponding to the first and last argument (not words!)
% corresponds to  first word matched by the most recent ‘?string?’ search

the special word designator * corresponds to 1-$
the special word designator ‹integer›* corresponds to ‹integer›-$

modifiers for history expansion

h ＆ t remove everything from a pathname but the head/tail
r / e remove a suffix .suffix / remove everything but the suffix
p prints the new command but does not execute it
s/old/new/ regex like substitution
(more exist)

indexes for ! for repeating start at 1 for the first command and go from there

##### tokenization

to the shell, a word is a sequence of characters treated as a unit by the shell. words are separated by whitespace or the characters ‘|’, ‘＆’, ‘;’, ‘(’, ‘)’, ‘‹’, or ‘›’. (this has nothing to do with IFS)

##### parsing (quoting)

since bash allows strings without quotes, double quotes actually perform a function somewhat similar to raw strings/escaping, except that the constructions starting with the metacharacters $, `, and ! still work.
In bash, $'...' treats the contents as raw strings, but allows for C-style escape seuqences.
In bash, $"..." translates the string according to the current locale settings

##### Expansion

Expansion is replacing a thing with another thing or things.

Expansions are performed in the order: brace › tilde › parameter › command substitution › arithmetic › process substitution › word splitting › filename expansion › quote removal 

Only brace expansion, word splitting, and filename expansion can increase the number of words of the expansion; other expansions expand a single word to a single word. The only exceptions to this are the expansions of "$@" and $* (see Special Parameters), and "${name[@]}" and ${name[*]} (see Arrays).

###### Brace expansion

Brace expansion is similar to filename expansion, but things expanded to need not exist as files.
Brace expansion is a mechanism for generating strings.
Brace expansion syntax: [‹preamble›]\{(‹comma-separated-strings›|‹sequence-expression›\}[‹postscript›]
comma-separated-strings: ‹string›{,‹string›} 
sequence-expression: ‹start›..‹stop›[..‹step›]
Bash calls its range syntax a »sequence expression«.
a{d,c,b}e results in ade ace abe
For brace expansion, bash generates all string alternatives, separated by spaces.
Since bash does brace expansion before anything else, it can contain other metacharacters, e.g. * or _, but they will be interpeted at the appropriate step later.

###### Tilde expansion

tilde expansion is performed if a word begins with a tilde.
tilde expansion takes an argument that is specified between the tilde and the next /
With tilde expansion, if no argument is given, the tilde will merely evaluate to $HOME
~foo|the home directory of the user with the name foo
~+/foo|$PWD/foo
~-/foo|$OLDPWD/foo
~‹n› as well as ~+‹n›|what would be displayed by dirs +‹n› (ie the nth directory on the directory stack)
~-‹n›|what would be displayed by dirs -‹n› (ie the nth directory on the directory stack counting from the back)

The ‘$’ character introduces parameter expansion, command substitution, or arithmetic expansion. 

###### Shell parameter expansion

While parameter expansion is disabled within '', it works in "", but also in unquoted strings.
In shell parameter expansion, the thing being expanded may be enclosed in curly braces, which is optional in some circumstances, and mandatory in others.
Assinging to a variable does not require the $ character, but referring to a variable is a form of parameter expansion and therefore does.
Bash supports a bunch of fancy parameter expansion features, which all require there to be {} surrounding them.

Within parametere expansion, prefixing a parameter with ! indicates indirection.
Indirection in parameter expansion means that if your parameter expands to another parameter name, it will then recursively expand this (to one level of depth)

Within parameter expansion, * and @ are nearly equivalent.
Within parameter expansion, to refer to an entire array, use arrayname[@/*]
Within parameter expansion, to refer to the special parameters $* or $@, use just * or @.

Bash allows specifying defaults for parameters within parameter expansion.
Bash's three operators for specifying defaults within parameter expasion are :-, :+ and :=.
Bash default for parameter syntax: parameter(:-|:+|:=)default
:- and := within parameter expansion evaluate to the parameter if not unset or null, or to the alternative otherwise.
The difference between :- and := is that :- will leave parameter unchanged, while := will substitute the value of parameter with the default.
:+ is the exact inverse of :-, it will only evaluate to the default if it is not null or unset.

Bash's slicing feature is performed within parameter expansion:
Bash slice syntax: ${parameter:start:length}

Many parameter expansions allow a pattern which is evaluated according to the usual pattern matching rules.

Bash's replacing within string is performed within parameter expansion:
general pattern (replace first instance) ${parameter/find/replace}
//pattern/replace|replace all instance
/#pattern/replace|replace if at beginning of string
/%pattern/replace|replace if at end of string

parameter#pattern get the shortest substring that matches pattern at the beginning
parameter##pattern get the longest substring that matches pattern at the beginning
parameter%pattern get the shortest substring that matches pattern at the end
parameter%%pattern get the longest substring that matches pattern at the end
parameter^pattern test each single character against the pattern, and uppercase the first one that matches
parameter^^pattern test each single character against the pattern, and uppercase all that match
parameter,pattern test each single character against the pattern, and lowercase the first one that matches
parameter,,pattern test each single character against the pattern, and lowercase all that match

parameter@operator do different things with the string depending on the operator
parameter@U|uppercase the string
parameter@u|uppercase the first character
parameter@L|lowercase all characters
parameter@Q|quote the parameter

Getting the length of something is done within parameter expansion: #parameter

###### Command substitution

Command substitution takes a command and replaces it (and the syntax) with its output.
Command substitution is performed in the modern syntax with $(command).
Command substitution is performed in the older, deprected syntax with `command`.
Command substitution may be nested.

###### Arithmetic expansion

Arithmetic expansion evaluates arithmetic and replaces it (and the syntax) with the result.
Arithmetic expansion is performed by $(())

###### Process substitution

Process substitution allws referring to the in or output of another process as a file.
To implement process substitution, bash creates an anonymous pipe with two file descriptors.
anonymous pipes file descriptors start at /dev/fd/63 and count downards
Process substitution runs asynchronously.
‹(command) provides the output of command as a file for further use.
\›(command) provides a 'file' for a command to write to that will be used as stdin for the provided command. 
command1 ›(command2) is equivalent to command1 | command2 if command1 supoorts outputting to sdout
e.g. a command doesn't output to stdout, but just a file
‹() is used more commonly than ›() because it is more common that a program expects multiple inputs as files than that it outputs multiple outputs as files.

###### Word splitting

Word Splitting	  	How the results of expansion are split into separate arguments.
the shell scans the results of parameter expansion, command substitution, and arithmetic expansion, if they did not occur within double quotes, for word splitting.
Word splitting means splitting the things mentioned above into words using $IFS
IFS is a prepopulated environment variable specifying what counts as a word separator.
IFS is used by a number of commands and control structures (e.g. looping) by default.
IFS is short for internal field separator.
The default value of IFS is whatespace.


###### File name expansion

filename expansion expands strings containing wildcards to pathnames.
filename expansion is perfomed using an utility/syntax known as glob.
The process of filename expansion is also known as globbing.
globbing recognizes wildcards.
a wildcard is a character(s) that expand to something else but their literal value.
a word containing a wildcard is known as a pattern

In the file name expansion stage, bash scans each word for a pattern and replaces it with an alphabetically sorted list of filenames matching the pattern.
In the file name expansion stage, bash retains patterns that didn't match anything as-is by default.
nullglob makes patterns disappear if they don't match anything
failglob makes patterns fail if they don't match anything.
When a pattern is used for filename expansion, the character ‘.’ at the start of a filename or immediately following a slash must be matched explicitly, unless the shell option dotglob is set. The filenames ‘.’ and ‘..’ must always be matched explicitly, even if dotglob is set. 
To see what a command will actually get from a file name expansion, you can prefix it with `echo`

wildcard|matches
*|matches 0-n arbitrary characters, excluding directory separators
**|0 - infinity characters, including directory separators
?|matches 1 arbitrary character
@(foo|bar|baz)|one of the options foo, bar, baz
?(foo|bar|baz)|zero or one of the options foo, bar, baz
+(foo|bar|baz)|one ⁑or more⁑ of the options foo, bar, baz
!(foo|bar|baz)|none of the options foo, bar, baz
*(foo|bar|baz)|zero or more of the options foo, bar, baz
[^‹characters›]   one character that is none of ‹characters›
[!‹characters›]   one character that is none of ‹characters›
[aml]   one of the characters a, m, l
[a-m]   one character in range of characters a-m

to activate bash wildcards using (), you have to enable extglob with shopt

.gitignore uses a similar syntax to globbing

###### Quote removal

After the preceding expansions, all unquoted occurrences of the characters ‘\’, ‘'’, and ‘"’ that did not result from one of the above expansions are removed. 

##### Redirection

Before a command is executed, its input and output may be redirected using a special notation interpreted by the shell. 

redirecting input [‹n›]‹[＆](‹path›|‹n›)
redirecting output [‹n›]›[›|\|][＆](‹path›|‹n›)

redirecting input opens the file for reading at file descriptor ‹n› (most commonly standard input)
redirecting output opens the file for writing at file descriptor ‹n› (most commonly standard input)
clobbering a file is to overwrite its contents.
redirecting ouptut will clobber by default, unless noclobber is enabled, in which case › must be followed by | to force clobbering
redirecting output will append instead of clobber if › is used instead of ››
if one wants to redirect standard output and error at the same time, there is the short form ＆›‹path› or ›＆‹path›, of which the first is preferred. adding another › appends instead, as per usual.
‹n›‹＆‹n› ‹n››＆‹n› make the first file descriptor ‹n› refer to the same file as the second file descriptor ‹n› is pointing to.
e.g. 1›out.txt 2›＆1  make the file descriptor 1 refer to the same file as the file descriptor 2
‹n››＆- or ‹n›‹＆- close the file descriptor ‹n›.
‹n››＆‹n›- or ‹n›‹＆‹n›- make the first file descriptor ‹n› refer to the same file as the second file descriptor ‹n› is pointing to, and then close the second file descriptor ‹n› (basically a move)
using ‹› instead of ‹ or › opens the file in read＆write mode
using ‹› and ＆ allows one to read from and write to the same file

for redirecting, the ‹n› before the ‹ or › may be the number of any file descriptor, though the standard streams are most common.

1› may be abbreviated › 
0‹ may be abbreviated ‹

if a file is to be used as input to a command, there is often no reason to do cat file | command, since one could also do command ‹ file

##### command execution

###### aliases

alias-command ::= alias{ name=vale}
the alias command with no arguments lists available aliases
aliases are only replaced if they are the first word of a simple command.
Aliases have very error-prone semantics, so using shell functions is almost always preferred.
sometimes an extra file bash_aliases is created for storing aliases, however bash does not itself read from bash_aliases so it needs to be sourced from other files.

###### pipelines

the character indicating an anonymous pipe is |
In a general sense, a ⟮filter⟯ ⟮takes some input⟯, ⟮transforms it⟯, and ⟮produces some output⟯.
In shell contexts, filters are combined with anonymous pipes.
Multiple filters combinded by anonymous pipes are a pipeline.
In shell contexts, filters normally recieve their input from STDIN and output it to STDOUT.
Well-behaved programs should operate as filters inf possible.
|＆ is the same as |, but it also outputs its standard error thrugh the pipe.
While they are often called merely pipes, the pipes in pipelines are actually anonymous pipes.
anonymous pipes ↔ named pipes.

Pipes, whether anonymous or named, basically consist of two file descriptors (one read, one write) and a buffer.
pipes are simplex in direction.
The default behavior in a pipe is for the writing and reading ends of a pipe is to exhibit blocking behavior. 
When in a pipeline, the write file descriptor is connected to the stdout of the first process and the read file descriptor is connected to the stdin of the second process.

When the second process reads from the buffer created by a pipe, this is called draining the pipe.

theoretically, any program that reads from stdin should read from terminal input if given no standard input (as cat does), however some programs don't.

####### liquid (semantically appropriate)

Liquid also features filters prominently to transform values, and also uses the pipe | as a separator.
filter name (liquid)|filter action|constraints
⟮date: "formatstring"⟯|⟮date formatting⟯
⟮markdownify⟯|⟮transform from markdown⟯|⟮jekyll only⟯
⟮append: foo⟯|⟮append foo to the string⟯
⟮prepend: foo⟯|⟮prepend foo to the string⟯

###### command search

When the shell encounters something it thinks it is a command, if it does not contain slashes, it first searches shell functions, then builtins, then $PATH, if it does contain slashes, it executes the path as a command. If the execution fails but the file is not a directory, it assumes the file is a shell script and tries to execute it thus.
The environment variable PATH provides a set of locations of where to search for commands.
PATH contains, well, paths, separated by colons.
For anything in PATH we can execute it by just using its name, to execute anything else we would have to use its path.
`⟮which⟯` takes ⟮a string⟯ and ⟮searches⟯ ⟮the PATH⟯ to see ⟮what the path of the binary of this command is.⟯
npx ‹name› allows execuution of a binary ‹name› within an npm project without having to specify a path (e.g. a local version of a build tool or sth.)
npx can also be used to run a specific version of a npm binary.

###### exit status

exit allows you to exit the current (sub)shell, optionally specifying an exit code.
success|0 
some kind of failure|not 0
miscellaneous error|1
(bash builtins) incorrect usage (invalid/missing arguments)|2

#### concepts

##### Parameters

In bash, a parameter is an entity that stores a value.
In bash (as in other languages), a positional parameter one passed by position (indicated by $1 ... $9)
In bash, there is a special set of parameters that is auto-set.
In bash, a variable is a type of parameter, specifically one denoted by a name.
In bash, a parameter may be indicated by a name (names are the usual type of [a-zA-Z0-9_]), by a number, or by a special character.
In bash assignment statements, only some forms of expansion are performed, specificaly tilde, parameter, command and arithmetic (ergo not brace and filename)
Bash assignmet statements may appear as arguments to the declaration commands
In the context where an assignment statement is assigning a value to a shell variable or array index (see Arrays), the ‘+=’ operator can be used to append to or add to the variable’s previous value.
+= in bash may add, append to array or append to string depending on the context.

Besides the positional parameters, shell has a set of special parameters which are auto-populated, but to which cannot be assigned.
*/@|expands to all positional parameters. They are the same when unquoted, when quoted $* expands to a single word separated by IFS, and $@ expands to separate words "$1" "$2"...
#|amount of positional parameters
?|exit status of most recent command/pipeline (foreground)
$|PID of shell, except in (), where it still has the PID of the shell and not the subshell
!|PID of job in background
0|name of shell or shell script
-|options the shell was launched with

NOT CONTENT JUST STOPPING THE PARSER FROM FREAKING OUT $

##### declaration commands

declaration commands = {alias, declare, typeset, export, readonly, local}

declare-command ::= declare {‹option›} {‹name›[=value]}

-f|functions with definitions
-F|functions without definitions
-r|readonly

in bash, declare prints the variables to which a given option applies if no names are given, or applies the option to the given names if some are given.
Thus the declare builtin can be used for a light form of typing.
for declare options, using + instead of - turns off the attribute instead (yes, really)
The typeset command is supplied for compatibility with the Korn shell. It is a synonym for the declare builtin command.
the type command indicates what it would be interpeted as if used as a command name (e.g. is a shell builtin, is a function, etc.).

### conventions

#### commands

most configurable commands are done so by a config file, either at ~/.commandname or XDG_CONFIG_HOME/commandname if following the XDG base directory specification, some also read from a global config file generally in /etc. Some commands also have a file ending in rc for config in those locations, though rc files generally specify commands to run beforehand more than settings.

The unix philosophy says each program should do one thing well and be designed to work together with other programs, most commonly by accepting text as IO.

##### common syntax considerations

-o PATH|generally short for/equiv to --out or --output
-O|output to current directory with same name. (curl, wget)
-(-)out, --output PATH|Write the output to a path (presumably, instead of STDOUT). Mac accept some sort of string interpolation, e.g. via C format string|curl, say, youtube-dl
--progress|show an indicator of progress|say
-f THINGY|generally short for/equiv to --file, sometimes also --from or --format
--file FILE|Use the file as input|say
-t SECONDS|Specify a length of caffeination in seconds|caffeinate (macOs only)
-t THINGY|Generally short for --to
-r|generally short for/equiv to --recursive
-R|generally short for/equiv to --recursive|chown
--recursive
-v|generally short for/equiv to --verbose or --version more rarely for --voice
--voice VOICE|speak whaterver with the relevant voice (generally only for things on mac that can use `say` in the background)
--verbose|verbose output
--version|show the version
-h|generally short for/equiv to --human-readable or --help
--human-readable|human readable output
--help|show a short set of info/options, generally shorter than man
-i|generally short for/equiv to --interactive, may also be short for --in-place, --include, --ignore-case/--case-insensitve
--include|
--interactive|prompt before doing something
--in-place|edit in-place, i.e. don't emit an extra file
-n NUMBER|amount of something
-n|generally short for --number
-d|prevent display from sleeping|caffeinate (macOs only)
-s|generally short for/equiv to --set
-u|generally short for/equiv to --unset
--dry-run|show what would happen withou changing anything
-a|show dotfiles or archive mode = preserve various attributes ＆ structures
-E|use ERE instead of BRE (Only where applicable, obv)
--lines|count/specify the number of lines

Options ≈ switches ≈ flags are indicated by hyphen(s) followed by characters
By convention, an option started by a single hyphen is one character long.
By convention, an option started by two hyphens is multiple characters long.
Generally, multiple single character flags can be joined into one: -h -a = -ha
In general, mac only features short flags, while linux also has long ones (this presumably has a deeper reason that I currently don't know)
In general commands that do something from a source to a target (e.g. cp, mv) have the default syntax SOURCE TARGET
⟮c1;⟯
-- normally ends the list of flag arguments and allows you to pass plain arguments


#### man

Most CLI commands have a manual page, which can be diplayd with man.
When we want a man entry for a composite command (e.g. git log, jekyll serve), the man entry headword (by convention) is the same, but hyphenated (git-log, jekyll-serve)
The numbers in parenthesis after the names of things (xterm(1), efence(3)) come from sections of the manual
The standard sections of the manual include:
1      User Commands
2      System Calls
3      C Library Functions
4      Devices and Special Files
5      File Formats and Conventions
6      Games et. Al.
7      Miscellanea
8      System Administration tools and Deamons

#### pagers

a ⟮pager⟯ is ⟮a terminal program⟯ that ⟮paginates⟯ its input. 
the ⟮default pager⟯ for the terminal is set in the env variable ⟮PAGER⟯. 
`⟮less⟯` is the most common ⟮pager⟯. 

## users and groups

GID|group id
UID|user id
groups/users on nix are uniquely identified by their user or group ID.
groupadd is the command for creating new groups.
gpasswd is the command for managing /etc/group and /etc/gshadow.
id is the command for printing things like UID, GID, etc.
the groups command lists the groups a user is in.
/etc/groups defines the groups on the system:
etc-groups ::= {‹group-name›:‹password-encrypted›:‹GID›:‹member_list›‹newline›}
passwd – modify a user's password

### commands

whoami|show current username
login|login as user
logout|logout of shell

### superuser

superuser = root = admin(istrator)
OS-independently, the superuser/root/administrator is a user with large to unlimited power over the system.
In unix, the superuser is the user with the UID 0.
In unix, the three groups that hasve superuser/sudo-related priviledges are wheel, sudo and admin.
sudo allows executing a single command with superuser priviledges.
To use sudo you need to enter your own password, to use su you need the password of the relevant user, in this case the superuser password.
Who can use sudo is managed in /etc/sudoers
visudo edits the sudoers file in a safe fashion with your configured VISUAL/EDITOR.
getpass is the C function that makes sure that password input is hidden (nothing is displayed) on the comamnd line
sudo usually caches the entered credentials for a short while.
The su utility requests appropriate user credentials and switches to that user ID (the default user is the superuser).  A shell is then executed.
su = substitute (in the past super) user
sudo = substitute (in the past super) user do

-E = --preserve-env

#### polkit

polkit is a toolkit to allow finer-grained control than just running sudo.
Polkit defines ⟮actions⟯, ⟮who can use them (group/user)⟯, and ⟮under which circumstances⟯.
pkexec works like sudo, but instead opens a window for password entry (it also depends on polkit policies)

## projects

freedesktop.org was formerly called X Desktop Group (XDG)
freedesktop.org governs projects such as the X Window System, wayland or systemd

# communication

### ASN.1

ASN.1 is an IDL for data structures that can be serialized and deserialized, mainly used in networking.

#### X.690

X.690 is a standard that specifies the BER, CER and DER encoding formats for ASN.1
Basic/Canonical/Distinguished Encoding Rules =short=> BER/CER/DER
CER and DER are subsets of BER.

### APIs for certain purposes

Data|Name|Interface
⟮DWD open weather data⟯|⟮Bright Sky⟯|⟮JSON⟯


# protocols

## hardware / low-level

### NFC

NFC = Near field communication
NFC works via induction.
NFC works at a distance of up to ~4 cm

### PCI

PCI   Peripheral Component Interconnect
PCIe  Peripheral Component Interconnect Express
PCI is a parallel bus, PCIe is a serial bus
PCI, AGP (older), PCIe (today) are the protocols/connectors that were/are used to connect things on the motherbord, especially PC expansion cards but also some of the things soldered on.

### thunderbolt

Thunderbolt 1 and 2 are transmitted via the MiniDisplayPort connector.
Thunderbolt 3 and 4 are transmitted via the USB C connector.
Apple and Intel co-developed Thunderbolt around 2011.
Thunderbolt was designed to run over optic fiber cables, but actually generally runs over copper.
1|10 Gbit/s
2|20 Gbit/s
3|40 Gbit/s
4|40 Gbit/s

### DP

https://upload.wikimedia.org/wikipedia/commons/f/f1/DisplayPort_Connector.svg|DisplayPort Connector
flex-container:✫sm_300px-Mini_DisplayPort_on_Apple_MacBook.jpg✫|Mini DisplayPort Connector
Mini and nonmini ⟮DisplayPort⟯ is mainly for ⟮video / audio⟯, but can also carry ⟮USB⟯ and ⟮other data (e.g. thunderbolt)⟯

### ATA

ATA is short for Advanced Technology Attachment, though due to IBM trademarks its officially short for nothing.
ATA was renamed PATA after SATA was introduced.
ATA/PATA|parallel
SATA|serial
PATA ＆ SATA are interfaces for secondary storage
SATA is the successor to PATA
SATA
I|1.5Gb/s
II|3Gb/s
III|6Gb/s
III Rev 3.2|16 Gb/s

### usb

USB   Universal serial bus
USB can transmit both data of various kinds as well as power.
The speed of USB depends on the version of USB, indicated with a number.
The role in the master/slave architecture of USB is indicated by a letter.
The connector type of USB depends on the letter indicating its role within the master/slave system, as well as the size specifier.

A|Master
B|Slave
AB|complicated
C|Either Master or Slave dynamically

Size specifiers: ø, mini, micro.

USB C only exists as a single size.

USB versions: 1.0, 1.1, 2.0, 2.0 revised, 3.0, 3.1, 3.2, 4.0

Within USB 3, usb 3.1 and 3.2 were renamed

table:class=yesno;Standard |USB 1.0 |USB 1.1 |USB 2.0 |USB 2.0 Revised |USB 3.0 |USB 3.1 |USB 3.2 |USB4
type=th;Maximum transfer rate |span=2;12 Mbps |span=2;480 Mbps |5 Gbps |10 Gbps |20 Gbps |40 Gbps
type=th;Type A |span=4;<img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/USB_Type-A_receptacle.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/f/f4/USB_3.0_Type-A_receptacle_blue.svg" width="75" height="67"> |span=2;class=no;Deprecated
type=th;Type B |span=4;<img src="https://upload.wikimedia.org/wikipedia/commons/2/28/USB_Type-B_receptacle.svg" width="50" height="60"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/USB_3.0_Type-B_receptacle_blue.svg" width="59" height="75"> |span=2;class=no;Deprecated
type=th;USB-C|span=3;class=no;N/A|span=5;<img src="https://upload.wikimedia.org/wikipedia/commons/0/07/USB_Type-C_Receptacle_Pinout.svg" height="80">
type=th;Mini-A|class=no;N/A|span=3;<img src="https://upload.wikimedia.org/wikipedia/commons/e/eb/USB_Mini-A_receptacle.svg" width="75" height="50"> |span=5;class=no;Deprecated
type=th;Mini-B|class=no;N/A|span=3;<img src="https://upload.wikimedia.org/wikipedia/commons/e/ec/USB_Mini-B_receptacle.svg" width="67" height="50"> |span=5;class=no;Deprecated
type=th;Mini-AB|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/USB_Mini-AB_receptacle.svg" width="60" height="40"> |span=5;class=no;Deprecated
type=th;Micro-A|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/8/86/USB_Micro-A.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/4/42/USB_3.0_Micro-A.svg" width="117" height="50"> |span=2;class=no;Deprecated
type=th;Micro-B|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/1/1b/USB_Micro-B_receptacle.svg" width="75" height="42"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/a/a8/USB_3.0_Micro-B_receptacle.svg" width="117" height="50"> |span=2;class=no;Deprecated
type=th;Micro-AB|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/6/6c/USB_Micro-AB_receptacle.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/7/7a/USB_micro_AB_SuperSpeed.png/117px-USB_micro_AB_SuperSpeed.png" width="117" height="69"> |span=2;class=no;Deprecated

USB has a tree (bus + star) topology 


#### usb 4

USB 4 was released in 2019.
As of USB 4, the only connector type is USB C.

## Internet Protocols


### layers


#### between application and transport









## protocols higher than the OSI/TCP/IP

For HTTP APIs, the endpoint is most commonly an URL + request verb.

### REST

⟮REST⟯ is short for ⟮Representational State Transfer⟯
⟮REST⟯ is a set of ⟮constraints⟯/⟮design principles⟯ for ⟮APIs⟯
⟮REST⟯ as an idea was created in ⟮2000⟯ by ⟮Roy Fielding⟯ in his ⟮doctoral dissertation⟯
On a theoretical level, ⟮REST⟯ consists of ⟮6⟯ ⟮constraints/criteria⟯.
While REST is theoretically implementation-independent, REST APIs generally transmit their data over HTTP as JSON
sometimes, HTTP APIs are called REST APIs even if they don't follow all constraints
an API following REST is often called RESTful
for the client-server constraint of REST to be met, client and server should be independent of each other, as long as the interface is not altered
Code on demand as a REST API constraint means that a REST endpoint may return code to execcute
RESTful APIs must be stateless, that is, the server does not have state, but rather any state information is transmitted by the client
The thing a RESTful API returns is called aaresource

#### six principles (alphabetical)

Cacheability
Client-server achitecture/decoupling
Code on demand
Layered system architecture
Statelessness
Uniform interface

#### HATEOAS

HATEOAS = Hypermedia as the Engine of Application State
HATEOAS(Hypermedia as the Engine of Application State) is part of the uniform interface constraint of REST
HATEOAS requires the responses of an API to contain all the relevant hyperlinks for further requests/action
in a RESTful API following HATEOAS, the API may change its URLs without creating incompatibilites
in a RESTful API following HATEOAS, one hits an initial API URL and navigates via hyperlinks from there.
Access in a RESTful API following HATEOAS is similar to a web-browsing user hitting a home page and finding their way from there

### OAuth

OAuth is short for Open Authorization
The current version of OAuth  is OAuth 2
Most APIs use OAuth for granting access to them, e.g. to monitor access and enforce API limits.
OAuth is also commonly used to grant access to information of other accounts without giving up your password.
OAuth is often used for logging in with Facebook, GitHub, Google, etc.
In OAuth there are 4 roles/actors, the resource owner (= User), the client (= Application), Resource Server (= Where the accounts are located), and Authorization Server
in OAuth, any client (= application) needs to register themselves with a resource server.
When registering an application with a resource server, one needs to provide a callback URL, which is where the resource server will redirect users after registering. 
After registering an applicationwith the resource server, it will issue a client ID and secret.
the client ID is public, the secret must be kept private.
client ID and secret are functionally the username and password of the application
The permissions to be granted or not in OAuth are known as scopes.
While the flow of OAuth using redirection etc. is the most common flow, there are others

OAuth 2.0 (grant type: Authorization code)

flex-container:✫tmp7t5et6aw.png✫

TODO transorm flow into ascii art maybe

In general, when users want to sign in using OAuth:
1. the application makes a request using its client id
2. The user sees a screen asking them to grant access
3. The user clicks ok (or not) and is redirected
4. We get an authorization code
5. We exchange the authorization code for an access token
6. We can now make API requests

## misc

MTP|Media transfer protocol
PTP|Picture transfer protocol

# networks

A network is a group of connected nodes that communicate via a medium, and almost always via a protocol.

## concepts

### routing

Routing is the process of selecting a path for traffic in a network or between or across multiple networks. 

#### addresses

An address is the identifier of an entity(ies) in a network, often relevant to a specific protocol.
A broadcast address is an address that identifies a subgroup of entities to target with a broacast transmission.
Loopback is the routing of signals/streams back to their source without intentional processing/modification.

#### routing schemes/architectures

Routing architecture visualization|name
⟮✫sm_unicast.svg✫⟯|⟮Unicast⟯
⟮✫sm_multicast.svg✫⟯|⟮multicast⟯
⟮✫sm_broadcast.svg✫⟯|⟮broadcast⟯
⟮✫sm_anycast.svg✫⟯|⟮anycast⟯



### topologies

The topology of a network is how its vertices are arranged.
A tree network may consist of star networks connected ⟮via a bus network⟯, or may be a tree just as a network.
In a bus, everyone attached recieves the transmission.
In a bus, only one entity can send at a time.
Sometimes, bus is used to refer any connection between two points, even if it isn't a bus (this definition is nonsense)
A daisy chain is a topology where devices are linked in a line or ring.

topology name|how it looks
⟮star⟯|⟮✫StarNetwork.svg✫⟯
⟮ring⟯|⟮✫RingNetwork.svg✫⟯
⟮fully connected mesh⟯|⟮✫FullyConnectedMeshNetwork.svg✫⟯
⟮partially connected mesh⟯|⟮✫PartiallyConnectedMeshNetwork.svg✫⟯
⟮bus⟯|⟮✫BusNetwork.svg✫⟯
⟮line⟯|⟮✫BusNetwork.svg✫⟯
⟮tree⟯|⟮✫TreeNetwork.svg✫⟯


## types

### telegraphs

The first type of telegraph was the optical telegraph.
The electrical telegraph began to overtake optical telegraphs middle of the 19th century.
electrical telegraph is often just shortened to telegraph.
The electrical telegraph uses electrical pulses as a medium.
Telegraph stations were connected by wires.
The first telegraph was the needle telegraph, later replaced by the telegraph with key and sounder.
flex-container:✫morse-vail-telegraph-key-1844-science-source.jpg✫
A ⟮telegraph key⟯ was/is a electrical switch where ⟮pressing it⟯ would ⟮produce a signal⟯ (and ⟮holding it⟯ would ⟮produce a longer one⟯).
The telegraph sounder would have produced clicks from the electrical impulses.
Telegraphs were operated by telegraph operators until the advent of teh writing  pelegraphs.

### telex

flex-container:✫sm_dbb1bf63cbbb7831ac766c93ee6e10d8.jpg✫✫sm_220px-Fernscheiber_01.jpg✫✫sm_s-l1600.jpg✫

Telex was the network of teleprinters common in a large part of the 20th century.
Rough synonyms (not abbreviations): Teleprinter, Teletypewriter, Telex
Abbreviations: teletypewriter → teletype → tty
Teletypewriters/teleprinters/telex/ttys have keyboard for input and a printer for output.
Video terminals then came to replace teletypewriters especially for computer IO
Teletypewriters + video terminals = physical/hardware terminals.

### the internet

On a basic level, the internet is a system of globally interconnected ⟮computer⟯ ⟮networks⟯.
The internet runs on the internet protocol suite.

An intranet is a computner network for an organization, but which uses most of the the Internet protocol suite. 
An intranet that can be acessed from approved 3rd parties too is sometimes called  an extranet

#### standards

IANA  Internet Assigned Numbers Authority
IETF  Internet Engineering Task Force
BCP   Best current practice
RFC   Request For Comment

RFCs are generally published by the IETFs.
RFCs may document internet standards, but RFCs may also be informational or experimental and non-normative. 
BCPs are a subset of RFCs.

⟮W3Schools⟯ weirdly is ⟮unaffiliated with the W3C⟯ 
⟮W3Schools⟯ is a website for ⟮documentation/information⟯ for ⟮web technologies/languages⟯ as well as ⟮other languages⟯. 
In ⟮the early 2010s⟯ ⟮W3Schools⟯ was known to have ⟮much low-quality information and errors⟯, leading to ⟮the website w3fools pointing it out⟯. However, ⟮today, most of it has been fixed⟯. 

#### the web

WWW = World Wide Web
The WWW runs on the internet, using the protocol HTTP(S).
The WWW is only one of many technologies running on the internet.
A web browser is a program to access the WWW.
The WWW was developed in CERN in 1989 by Timothy Berners-Lee.
The first web browser was written in 1990, the WWW was released in 1991.
The main organization working on web standards is the W3C.
World Wide Web Consortium = W3C
A web site is a collection of web pages, generally one that share a domain name/FQDN

##### user agents

User agent may mean any device that accesses web services for an user, or autohyponymously to a web browser specifically, or to the HTTP header User-Agent.

lynx, w3m|text-based browser

Qutebrowser is a vim-like browser written in python.
In qutebrowser, quickmarks are bookmarks that have a short name
For qutebrowser, you do ⟮advanced config⟯ in ⟮the config.py⟯ 
In the config.py of qutebrowser, you ⟮can change most settings⟯ ⟮on the `c` object⟯ 
In qutebrowser, greasemonkey scripts become active merely by placing them in $XDG_CONFIG_HOME/qutebrowser/greasemonkey

##### file-sharing

ephemeral file-sharing sites allow you to upload files which expire after a while

##### performance

https://developer.mozilla.org/en-US/docs/Web/Performance/Critical_rendering_path
https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading
TODO: More structure. How do these relate? WHat aspect of performance are they optimizing? Perhaps use PRPL as a structure, or something else, or a combination.

###### speculative parsing

Speculative parsing is that the browser will not block when hitting a script tag, but instead just continue parsing while fetching the script, and using the parsed DOM if the script hasn't modified it (which only really happens via document.write()).
Speculative parsing does not apply to images/css/videos, which will not block even if speculative parsing is disabled (the fact that it doesn't is a common myth)

###### lazy loading

lazy loading is loading things only when needed.
In general, one lazy-loads the things that are not critical to performance.
To enable lazy loading for images and iframes, set loading="lazy", these images will only load once they are a specific distance away from the viewport.
TODO relationship with code splitting (I think code splitting allows for lazy loading)

###### server push

Server push allows the server to send along resources it knows the browser will need directly on the first HTTP request (without the browser having requested them)
Server push is a feature of HTTP/2, used by specifying it in the HTTP header

###### minifcation

⟮Minifying⟯ is ⟮removing unnecessary characteristics⟯ (e.g. ⟮longer names, whitespace⟯) from ⟮source code⟯ to ⟮reduce size⟯
⟮minified files⟯ are commmonly indicated by ⟮.min(.whatever)⟯

###### media compression

Images used ⟮on the web⟯ are typically ⟮specifically compressed⟯ beforehand, e.g. ⟮by using programs such as imageoptim⟯

Image compression tools
|GUI|CLI|API|other
imageoptim|y|y|y
squoosh|web|y|n
sharp|n|n|n|npm module

###### PRPL

Push/Preload the most important resources
Render the initial route ASAP
Pre-cache remaining assets
Lazy-load other routes and non-critical assets

the "render the initial route ASAP" of PRPL is basically "reduce time to first (contentful) paint"
"render the initial route ASAP" can be achieved server-side by SSR/Static Generation, and client-side by stuff like async or defer (and maybe others)

####### P

⟮c+;‹link rel="preload"⟯ specifies that you ⟮will need the resource very soon⟯, and that it should be downloaded ⟮asyncly⟯ with ⟮high priority⟯
⟮c+;‹link rel="preload"⟯ needs an ⟮as=⟯⟮"kind(e.g. style, script, image)"⟯
If you've specified a resource with ‹link rel="preload", you still need to actually include it later

###### defer ＆ async

defer ＆ async are two attriubtes for ‹script› that influence how it is loaded.
Ignoring speculative parsing, when the browser hits a ‹script› tag, it blocks until it's loaded, which is not ideal since scripts are quite large, and the browser could be loading things in parallel.
Instead of the default behavior, the `defer` and `async` attribute of scripts tells the browser to load the script in the background.
Between  the `defer` and `async` attributes, defer executes scripts loaded in the background ⟮when the dom is fully built⟯, in the order they were in the document
Between  the `defer` and `async` attributes, async executes scripts loaded in the background ⟮as soon as possible⟯, in the order in which they load, no matter source order.

###### RAIL

RAIL is a performance model that centers on the user.
RAIL is short for Response, Animation, Idle, Load.
RAIL's perfomance model consists of goals for the four things of which it consists.
Response|respond to user input within 100ms. To account for other background tasks, budget 50ms.
Animation|provide an animation frame every 16ms (= 60FPS). Since browsers take about ~6ms to render a frame, budget max 10ms to calculate the frame. 
Idle|Use idle time so that other goals are met. Perform work in idle time in bursts of 50ms or less so that the Response goal is met.
Load|(subject to change with new technology) Load within 5s on first load and in 2s on subsequent loads on mobile.

###### minification

Webpack minifies your JS by default, using `terser`.
Source maps allow mapping minfied/compressed/otherwise transformed code back to the original source
to indicate a source map, at the bottom of the optimized file, add a magic comment or use the http header
source map magic comment: //# sourceMappingURL=foo/bar.js.map 
Most dev tools have source map support built in.

###### Google speed

PageSpeed Insights|Lab data ＆ realworld data|Web Vitals|only website by default
Lighthouse|only lab data|Web Vitals ＆ other data|GUI (devtools ＆ website), CLI, CI pipeline

####### Lighthouse

Lighthouse's Performance audits provides a grade consisting of (the scores of individual) metrics, but also offers opportunities and diagnostics::d... as ways to improve the metrics
Lighthouse consists of 5 categories, Performance, PWA, Best Practices, Accessibility, and SEO.

⟮Web Vitals⟯ are the stats that ⟮google⟯ measures to judge ⟮the user experience of your websites⟯
⟮Core Web Vitals⟯ are the subset of ⟮Web Vitals⟯ that ⟮apply to all web pages (and are thus considered very important)⟯
as of 2020, there are 3 core web vitals

Largest Contentful Paint, Cumulative Layout Shift|Core Web Vitals ＆ Lighthouse Metrics
First Input Delay|Core Web Vitals 
First Contentful Paint, Speed Index, Time to Interactive, Total Blocking Time|Lighthouse Metrics

A ⟮layout shift⟯ is when a ⟮visible element⟯ ⟮shifts position⟯ between ⟮render frames⟯ (in bad cases causing users to e.g. ⟮click the wrong button⟯)
⟮Cumulative Layout Shift (CLS)⟯ is how google measures the ⟮badness⟯ of the ⟮layout shifts⟯ you've going on
The ⟮largest contentful paint⟯ is when the ⟮largest media/text block⟯ (which elements are exactly considered is more complicated) loaded, relative to ⟮when the page first started loading⟯


a ⟮long task⟯ is when ⟮the main JS thread⟯ is ⟮blocked⟯ for more than ⟮50ms⟯
⟮Total Blocking Time⟯ as a Lighthouse metric measures ⟮cumulative length⟯ of ⟮long tasks⟯ between ⟮First Contentful Paint⟯ and ⟮Time To Interactive⟯
the ⟮Lighthouse Speed Index⟯ is how quickly ⟮the viewport is visually populated with content⟯
⟮Time to Interactive⟯ as a ⟮lighthouse⟯ metric is the time it takes for a page to ⟮become fully interactive⟯

CLS  Cumulative Layout Shift 
FCP  First Contentful Paint
FID  First Input Delay
LCP  Largest contentful paint

##### web analytics

In web analytics, a bounce is a person who only views one page of a site and then leave.
The bounce rate is the percentage of total site visitors who bounce.

#### infrastructure

##### clients

A thin client is a low-performance computer that mainly exists to connect with a server, which handles most of the computing ＆ storage.
A zero client is a thin client driven to extremes, so that it has no local storage and barely any computing ability of its own.
Hardware terminals are basically zero clients.
a rich/fat/heavy/thick client is a client that contrasts with a thin client in that it can do more stuff itself.

# platforms running on the internet

## search engines

### google

WIthin google search, ⟮tbm⟯ is the key of the query parameter that ⟮specifies the type of search (Image, News, Shopping etc.⟯) 
For example, ⟮Specifying the search mode in google search as images⟯ is done by ⟮`tbm=ish`⟯ 
Force google to ⟮only finde pages from a certain domain⟯ is done by ⟮site:foo.com⟯ 

## fora

### text ＆ imageboards

A ⟮textboard⟯ is a ⟮simple⟯ kind of Internet ⟮forum⟯; most require neither ⟮registration⟯ nor ⟮entry of a screen name⟯. 
An ⟮imageboard⟯ is like a ⟮textboard⟯, just with ⟮images⟯. 
⟮Textboards⟯ as well as ⟮imageboards⟯ were invented in ⟮Japan⟯. 
⟮Textboards⟯ such as ⟮2channel⟯ are generally popular in ⟮Japan only⟯, while ⟮imageboards⟯ (e.g. in the form of ⟮4chan⟯) are popular in ⟮english-speaking countries too⟯ 

# in programming

To share data between entities, one can use message passing or shared memory.
Shared memory is having a fixed storage location which both entities can access to read/write the data.

## messages

Message passing is communicating between two things by sending messages.
A message consists of the source thing, the target thing, the message, and potentially the  arguments passed.
IPC is just message passing between two processes.

# applications

⟮Photoscape X⟯ is notable for being a ⟮GUI⟯ program that has ⟮batch editing of photos⟯

# vimlike

## modes

vim basic modes: ⟮normal⟯, ⟮insert⟯, ⟮visual⟯, ⟮select⟯, ⟮command⟯, ⟮ex⟯, ⟮terminal⟯ (there are more, but they are all derivative of these)

insert mode|similar to how a normal text editor works
normal mode|commands on the text
command mode|allow entering of vimscript/ex commands
visual mode|select text

Moving in visual mode selects the thing you traverse
visual mode|select text you go over (as in normal word processors)
visual line mode|select whole lines you go over
visual block mode|select rectangular areas you go over

⟮Select mode⟯ is like ⟮visual mode⟯, but ⟮starts insert mode for the selection⟯.
Ex-mode is a mode for vim similar to command mode (which itself also supports ex commands), which is mainly used for batch processing.

I (shift i)|visual mode → insert mode
v|normal mode → visual mode
shift+v|normal mode → visual line mode
ctrl+v|normal mode → visual block mode
:|normal mode → command mode
esc|most modes → normal mode
enter|search mode → normal mode at place where searched
visual|ex mode → normal mode

## vimscript/commands

vimscript is the scripting language built into vim.
vimscript is used for command mode commands, macros and in .vimrc

Action|Command|Available in...|Differences between
⟮evaluate a js string⟯|⟮:jseval⟯|⟮qutebrowser⟯
⟮bind a key⟯|⟮:bind⟯|⟮qutebrowser⟯
⟮restart qutebrowser⟯|⟮:restart⟯|⟮qutebrowser⟯
⟮save⟯|⟮:w(rite⟯)|⟮qutebrowser, vim⟯|⟮saves the file in vim and the session in qutebrowser⟯
⟮quit⟯|⟮:q(uit⟯)|⟮qutebrowser, vim⟯
⟮save and quit⟯|⟮wq⟯|⟮qutebrowser, vim⟯|⟮saves the file in vim and the session in qutebrowser⟯
⟮reload config file⟯|⟮config-source⟯|⟮qutebrowser, vim⟯
⟮:Explore⟯|⟮open vim file explorer⟯|⟮vim⟯
⟮:saveas⟯|⟮save file with name and continue editing this⟯|⟮vim⟯
⟮:so(urce) file⟯|⟮source the specified file as vim code⟯|⟮vim⟯
⟮:number⟯|⟮show number of current line⟯|⟮vim⟯

pwd   current directory|vim only
h(elp)   show help|vim, qute
s(ubstitute)   replace text|vim only

set|change/set an option
%s|replace on all lines (slash-based)

clearjumps   clear the jumplist
jumps   list all items in the jump list

sp filename   open file in horizontal split
vsp filename   open file in vertical split

the various map commands is for mapping actions to keyboard shortcuts
map-command:  ‹mode-char›[un|nore]map
in the map commands, nore means no recursion, i.e. don't trigger further keybindings/maps after performing the map
In general, it is wise to use the nonrecursive mappings
in the map commands, un is for unmapping a certain combination

## concepts

### lists

all past jumps are stored in the jump list
In vim, only a specific subset of things that move the cursor counts as a jump
In addition to the jump list, there is the similar  change list

## shortcuts

### normal mode

#### common/vim only

##### multiple modes/mode-agnostic

###### search

/|start forward search
?|start backwards search
n|next regex match|qutebrowser, zathura, vim, less
N|previous regex match|qutebrowser, zathura, vim, less


###### window

ctrl+w   prefix for window management
ctrl+w ›   grow window width of window rightwards
ctrl+w ‹   grow window width of window leftwards
ctrl+w hjkl   move between windows according to hjkl
ctrl+w +   grow window height
ctrl+w -   shrink window height
ctrl+w H/J/K/L   move window to the far left/bottom/top/right
ctrl+w ctrl+w   cycle through windows
ctrl+w c   close current window
ctrl+w o   maximize current window (and thus get rid of all splits)
ctrl+w s   split window horizontally
ctrl+w v   split window vertically

###### buffer

ctrl+^    doing buffer related stuff (switching buffer when no leading number arg)
‹n›ctrl+^    switch to buffer n

##### grammar-defined (may be insert-only or multi-mode)

action ::= ‹command-component›||‹motion-component›
command-component ::= [‹count›]‹command›[‹command›]
motion-component ::= [‹count›]‹motion›
text-object ::= ‹modifier›‹object›
modifier ::= i|a
count ::= ‹digit›{‹digit›}

double operator does the action to the whole line, or ‹count› whole lines.
Only a small subset of vim commands take a motion argument.
A motion without a command component simply moves the cursor
e.g. ›› shift whole line right
modifiers:
a   around our object (including whitespace/surrounding symbols) 
i   inside our object (excluding whitespace/surrounding symbols)

###### countable commands

ctrl+i   jump to next (newer) location in jump list
ctrl+o   jump to previous (older) location in jump list

Change to insert mode

a|insert text after cursor
i|insert text before cursor
A   append text at end of line(enters insert mode)
I (shift i)   insert text before first non-blank in line(enters insert mode)
O   begin line above cursor and insert text(enters insert mode)
o   begin line below cursor and insert text(enters insert mode)
s   erase letter under cursor and set insert mode(enters insert mode)
S   erase whole line and enter insert mode (enters insert mode)

C   change to end of line
D   delete until end of line

p   paste after the cursor
P   paste before the cursor

x/X   delete forwards/backwards (not an operator, therefore does it immediately, in contrast to d

J   join next line with this one

####### page navigation

ctrl y|half page right|zathura only
ctrl d|half page down|qutebrowser, zathura, vim
ctrl f|page down|qutebrowser, zathura, vim|
ctrl b|page up|qutebrowser, zathura, vim|
ctrl t|half page left
ctrl u|half page up

In vim, adding a ‹count› before the half page... makes this scroll ‹count› lines instead of a half page, in qutebrowser it instead scrolls ‹count› half-pages. They both behave the same for whole file commands


###### motions

k|move cursor up|qutebrowser, zathura, vim, less
j|move cursor down|qutebrowser, zathura, vim, less
l|move cursor right|qutebrowser, zathura, vim, less
G|go to last line|qutebrowser, zathura, vim, less
g|go to first line|less only
‹n›G   jump to line n
H/L|top/bottom of viewport
‹quantifier›H/L|n lines before top/bottom of page
M   go to middl eof screen
%   matching delimiter (e.g. other ")")
(/)   beginning/end of sentence
[[/]]   previous/next { (with edits suggested in :help)
[{/]}   ⟮beginning/end of block (enclosed in {})⟯
{   prev blank line
⟮c1;⟯}   next blank line
b/B   start of previous word 
e/E   end of word 
w/W   start of next word 
^   start of line (excl whitespace)
$   emd of line
'‹letter›|mark ‹letter›
+/-   beginning of line below/above
0   move to first character in line (even if indented)
##   search backwards for word under cursonr
*   search forwards for word under cursor
f‹character›   go to next ‹character› on current line
F‹character›   go to previous ‹character› on current line
t‹character›   go to up to (one before) character
T‹character›   go to up to (one before) character backwards

The capital versions of the motions w e and b are different from the non-capital versions in that the capital versions only consider space as a separator, while the non-capital versions also consider puctuation as a separator

######  objects

p   paragraph
s   sentence
"   something wrapped  in "
( or )   something wrapped  in ()
[ or ]   something wrapped  in []

###### motionable commands

›   shift right
‹   shift left
gU   convert to uppercase
gu   convert to lowercase
y   yank
c   change (delete and enter insert mode)
d   delete (more precisely: cut (you can paste it again))

###### g

g|first character of a whole set of additional shortcuts|qutebrowser, vim
gd|download page|qutebrowser
gg|go to first line|

###### related

m‹letter›|set a ‹letter› as a mark

##### visual mode exclusive

o|go to other end of selection

#### qutebrowser

yt|yank title to clipboard
yT|yank title to selection (primary selection has something to do with terminal clipboards etc.)
yy|yank URL to clipboard
yY|yank URL to selection (primary selection has something to do with terminal clipboards etc.)

f|hint for opening in this tab
F|hint for opening in new tab
;‹some char›|hint ‹different things›
;p|hint images for yanking
;y|hint links for yanking
;i|hint images (for opening in new tab)
;b|hint for opening in background tab
;d|hint for downloading
;h|hint for hovering

{{ / }}|click previous/next link on page (new tab)
[[ / ]]|click previous/next link on page (same tab)
r|reload
R|hard reload

ctrl a|increment number in url
ctrl x|decrement number in url

w...|do dev/web inspector related stuff
wi|toggle devtools

(t/w)h|back (in new tab/window)
(t/w)l|forward (in new tab/window)

H/L|history forward/back   
J/K|next/prev tab   

p/P‹some_char›|do paste stuff (first char)
pp|open URL from clipboard
pP|open URL from selection
Pp/PP |what pp/pP do (open URL from clipboard/selection), but in a new tab
            
b/B|open quickmark in this tab/new tab
‹n›|open tab n
T|open tab chooser (accepts number, name, or url)

go/gO|edit current URL (and open in this tab/new tab)
o|open website (in current tab)
O|open website (in new tab)
d|cloze current tab
‹n›d|cloze nth tab

mode-switching:

enter passthrough mode   ctrl v
exit passthrough mode   shift - esc
Passthrough mode is like insert mode, but won't auto-exit

#### less

q|quit|less
h|show help|less and similar

#### zathura

best-fit mode of display   a
follow links/ display link target   f/F ‹number-index›
rotate   r
toggle 2 pages side by side view   d
width mode of display   s
collapse entry/all entries   h/H
expand entry/all entries   l (small l)/L
next page/prev page   space/shift-space
show index and switch to index mode   tab
switch to presentation mode (and back)   f5
Snap to current page   P




u|undo action
y|yank selection

y|yank the thing you've searched for, if you've searched for something



.|repeat past action

## vimlike apps

name|function
⟮lf⟯|⟮vimlike curses file manager⟯
⟮qutebrowser⟯|⟮vimlike web browser⟯
⟮vifm⟯|⟮vimlike curses file manager⟯
⟮vimiv⟯|⟮very vimlike image viewer⟯
⟮visidata⟯|⟮vimlike data visualizer⟯
⟮zathura⟯|⟮vimlike document viewer⟯


## patterns

### do an edit a bunch

1. search for the place you want to make an edit with /pattern
2. make your repeatable edit
3. use n to go to the next place to edit
4. use . to repeat the edit
5. repeat the last two steps: You're the king of the world (or at least of edits

## misc

In vim, copying is known as yanking.

# misc

### various programs

#### subscriptions

podboat   podcast management for newsboat
newsboat|good rss reader
newsboat is the maintained fork of newsbeuter
newsboat stores the things its subscribed to in an urls file.
newsboat-subscription-file ::= {newsboat-subscription-line}
newsboat-subscription-line ::= ‹url›{ ‹newsboat-tag›}
newsboat-tag ::= ‹newsboat-tag-no-spaces›|‹newsboat-tag-spaces›
newsboat-tag-no-spaces ::= ‹operator-prefix›‹string›
newsboat-tag-spaces ::= "‹operator-prefix›‹string›"
operator-prefix ::= ~|!

~|make this the name of the feed
!|hide the feed


-x string, --execute=string   execute a command
commands e.g. reload

#### mail

mail or the older mailx are *nix builtins to manage mail.

#### backup

borg, restic

#### termdown

termdown is a terminal timer utility.
termdown [OPTIONS] [TIME]
You can specify the time for termdown in a variety of formats.
SPACE|Pause
R|Reset
Q|Quit
L|Lap
-|subtract 10s
+|add 10s

--critical SECONDS|Draw final N seconds in red and announce them individually with --voice

#### pass

`pass` terminal-based password manager
`pass` edit plaintext version of file  `pass edit somepassword`
`pass` delete a password  `pass rm somepassword`
`pass` command for listing the passwords  pass ls (or just pass)
`pass` command for adding passwords  `pass insert/add`

#### misc

cal/ncal display a mini ascii calendar

### online data fetching

`urban`|Terminal urban dictionary browser
`trans`|Use google translate to translate text
`deepl`|Use deepl to translate text

lang-specifier (trans, deepl) ::= [‹lang›]:‹lang›{+‹lang›} # leave out first arg for detection


### sysadmin

powertop - cli program to analzye power consumption
mac: system_profiler|report system hardware and software configuration (mac)

#### hardware info

lspci   list pci devices
lshw   list hardware config
lsblk   list block devices
-f/--fs|list some extra info, esp. UUID
lsusb   list USB devices


# standards

unofficial extensions are generally indicated x-whatever

# licenses

A rights managed license allows only specific uses.
A royalty-free item is one with a license which allows unlimited uses without paying any more money.

## CC

The three attributes that a CC license can require (or not) are Attribution, Share Alike, No Derivates.
As of 2013, the newest version of CC is 4.0
CC0 releases the work into the public domain.

# identifiers


## language

The locale of a user is a set of values for a set of parameters related to language and region.
The locale is generally specified as an identifier.
On POSIX platforms, locales are specified as environment variables with a certain syntax.
posix-locale-identifier ::= language[_location][.charset][@modifier]
the environment variables for locales are LANG as well as various LC_*.
All LC_* locale variables are overwritten with LC_ALL.

the locale command shows the currently specfied locales.
/etc/locale.gen and the command locale-gen associated with it is used for generating locales

### BCP47

A ⟮IETF language tag⟯ indicates exactly ⟮in which language a thing is⟯. 
Currently, the standard for ⟮IETF language tags⟯ on the internet is ⟮BCP47⟯. 
BCP 47: ⟮‹primary-language›⟯⟮[-‹extended-language›]⟯⟮[-‹script›]⟯⟮[-‹region›]⟯⟮[-‹variant›]⟯⟮[-‹extension›]⟯⟮[-‹privateuse›]⟯ 
BCP 47 language tags should be kept ⟮as short as possible⟯. 

#### subtags

##### primary language

The ⟮primary language⟯ subtag of ⟮BCP 47⟯ is specified as ⟮a language code⟯. 
A ⟮language code⟯ consists of ⟮2 or 3 letters⟯. 
⟮Language codes⟯ are standartized in ⟮ISO 639.⟯ 
⟮3-letter language codes⟯ are standartized ⟮in ISO 639-2 and -3⟯. 
⟮2-letter language codes⟯ are standartized ⟮in ISO 639-1⟯. 

##### other

⟮extlang (extended language⟯) subtags are for ⟮sublanguages of a given language (e.g. hakka chinese, the variants of arabic⟯) 
⟮script⟯ subtags are for ⟮writing systems⟯, and always ⟮4 characters long⟯ 
⟮region⟯ subtags are for ⟮locations (countries, other geo regions⟯) 
⟮variant⟯ subtags are for ⟮dialects or other variations (however, use other tags if possible⟯) 

##### extension

bcp-extension = (ALPHA/DIGIT) 1*( "-" 2*8(ALPHA/DIGIT) )

currently, for the initial char/digit of a BCP extension, only two are defined (or maybe that's only for `Intl`?): u and t

u alllows additional customization, specified as ‹key›-‹value›
t indicates that it was transformed from the following locale

##### private use

bcp-private-use = x 1*( "-" 1*8(ALPHA/DIGIT) )

#### examples

BCP 47 language tag|meaning
⟮en⟯|⟮english (no further info⟯)
⟮zh-hak⟯|⟮hakka chinese⟯
⟮zh-Hans⟯|⟮Chinese written in hanzi (simplified⟯)
⟮en-GB⟯|⟮english as spoken in great britain⟯
⟮az-Latn⟯|⟮azerbaijani, written in latin script⟯
⟮ast⟯|⟮asturian (no further info⟯)


tag|problem
⟮it-IT⟯|⟮unneccesary specification of IT (italian as spoken where else?⟯)
⟮es-Latn⟯|⟮Unneccesary Latn (As opposed to spanish written in kanji? :P⟯)

### in HTML

In HTML, the ⟮language of the document⟯ should be indicated with ⟮a lang attribute⟯ ⟮on ‹html›⟯o 
In HTML, ⟮anything that is not in the language indicated on ‹html›⟯ should be ⟮indicated by an element with a lang attribute.⟯ 
In HTML, the ⟮lang attribute⟯ takes ⟮BCP 47 language tags⟯. 


## media

### DOI

DOI = Digital Object Identifer
A DOI is a eternally persistant identifier of exactly one work.
DOIs are standartized by the ISO.
DOIs are mainly popular in academia.
https://doi.org/ is the DOI resolver.
DOI resolver + DOI resolves to an online representation/page of the resource
One can identify DOIs by prefixing the DOI resolver or the URN namespace `doi:`
doi-syntax ::= ‹registrant-identifer›/‹object-identifier›

### ISBN

ISBN   International Standard Book Number
There is one ISBN per version of a book, such that different editions, hardcovers/paperbacks, etc. each have unique ISBNs
ISBN-10 and ISBN-13 are the two types of ISBNs there are, with 10 and 13 characters each.
the original standard was ISBN-10, but since that was filling up, it was switched to an ISBN-13.
Serial publications don't get ISBNs, but instead ISSNs.

## licenses

Copyleft is type of restriction that does not allow creators of thing B including thing A to restrict the access to thing B more than thing A.
GPL is a type of copyleft license.
Share-alike is a type of copyleft license.

SPDX is a format for software licneses

spdx-license-expression ::= ‹spdx-simple-expression›|(‹spdx-license-expression› ‹operator› ‹spdx-license-expression›)|\(‹spdx-license-expression›\) # slightly simplified
spdx-simple-expression ::= (‹license-name›-‹license-version›)[+]
Each SPDX license has a short and a long name.
The + at the end of a SPDX license indicates this version or later.

## versions

semver = semantic versioning
semver is the most common way to specify version identifiers
semantic-versioning-version ::= ‹semantic-versioning-version-specifier› {‹connective› ‹semantic-versioning-version-specifier›}
semantic-versioning-version-specifier ::= [‹operator›]‹major›.‹minor›.‹patch›
operator ::= ~ | ^ | ‹relational-operator›
connective ::= \|\| | ＆＆ | - 

patch|backwards-compatible bugfixes
minor|new functionality in a backwards-incompatible manner
major|incompatible changes to existing API

~A.P.X|of the same A.P, but higher levels of the same patch are acceptable, i.e A.P.Y...
^A.P.X|any that do not modify leftmost nonzero digit


Using semver, for each of major, minor or patch you can instead specify a * to indicate that any are acceptable.

## date ＆ time

### Unix time

Unix time measures seconds passed since the unix epoch.
The unix epoch is the datetime at which unix time starts.
The unix epoch is 1970-01-01T00:00:00 UTC. 
Unix time is also called various other things including unix, posix, epoch, and time, none of them correct.

### datetimes

Most common format is RFC 3339 / ISO 8601
RFC 3339 is almost the same as ISO 8601

### time zones

The primary standard for time is UTC.
The primary standard for time used to be GMT.
UTC's standard specifies that time is divided into days, hours, minutes, and seconds, how much of each each contains, leap seconds, etc, and what time it is according to that system.
Ergo, UTC is a time system and the current time in that system, while UTC offsets are ways to define time in relation to UTC, but are not UTC themselves (!)
Timezones are defined in reference to UTC via UTC offsets.
UTC-offset ::= UTC(+|-)‹time›
UTC may be specified using an UTC offset as UTC+0
Nevertheless, what people often are referring to when they say UTC is the system of UTC offsets
Today, GMT is an alias for UTC+0

## currencies

Currencies are identified by a currency code.
ISO 4217 standartizes currency codes for national currencies as well as some other currencies.
In the case of national currencies, the first two letters of a currency code are the 2-letter country code, and the third is usually the initial of the currency.
The third letter of a national currency currency code may sometimes be chosen for mnemonic purposes instead of the initial of the currency (EUR)
When a devaluation happens, a new currency code must be chosen, thus the third letter will no longer be the inital of the currency.

currency codes for special types of currencies start with an X.

X+element symbol = currency code for special metals 
for special metals, the currency code indicates one troy ounce instead of one of the currency.
XTS|testing only
XXX|no currency

## emoji shortcodes

The ⟮common syntax for emoji⟯ is sometimes called '⟮emoji shortcodes⟯'
⟮emoji shortcodes⟯ are delimited by ⟮colons⟯, and have names in ⟮lowercase⟯ connected by ⟮underscores⟯.
The ⟮emoji shortcode⟯ for ⟮💙⟯ might be ⟮:blue_heart:⟯
The ⟮emoji shorcodes⟯ don't have ⟮a spec⟯, but you ⟮can use them in many places⟯, including sites such as ⟮Discord, GithHub, and Slack and a whole lot more⟯
In ⟮some places⟯ (e.g. ⟮discord⟯), you can ⟮prefix⟯ ⟮emoji shortcodes⟯ with ⟮+⟯ to ⟮add a reaction⟯.
I can ⟮type emoji using emoji shortcodes⟯ but ⟮using spaces instead of underscores⟯ anywhere using ⟮espanso⟯. 

## dice notation

⟮Dice notation⟯: `⟮‹amount›⟯⟮d⟯⟮‹sides›⟯⟮+⟯⟮‹add-to-end-result›⟯` 
In ⟮dice notation⟯, you can leave out ⟮the amount of dice to roll⟯, if ⟮its one⟯. 
⟮4d10+3⟯ is an example of ⟮Dice notation⟯, it means ⟮roll 4 10-sided dice and add 3 to the overall result⟯ 
the shell command ⟮`roll`⟯ ⟮rolls dice⟯, specified in ⟮dice notation⟯ 

## citation

### content

Reference and citation are most often synonyms.
Citation is indicating a source of information.
A »full citation« fully identifies a source, and where in the source the information can be found, if applicable.
A »short citation« identifies a source in a short way and where in the source the information can be found, if applicable. to resolve a short citation to the actual work, finding the corresponding full citation is normally needed.
Philosophical works sometimes get an abbreviation such as KrV for use in short citations
A »complete citation« is the pair of a short citation and a full citation.
Author-date is a type of short citation where one includes the author and date.
Author-date citation is also called harvard style.

some citation styles allow using ibid. instead of the page information if the page information is repeated.

### placement

onion-box:
citations 
  in-body citation 
    note citation
    in-text citation
  works cited/references entry


Note citations are citations in endnotes/footnotes.
In-text citations are citations within the flow of text.
Typically, short citations are also in-body citations, and full citations are reference entries.

### → in-text short citations

Parenthetical citation is a type of in-text short citation format where the citation is surrounded in parentheses.
Narrative citation is a type of in-text short citation format where the citation is mentioned in the prose of the text.
Author-date/harvard style is often realized as narrative or parenthetical citations.
author-date-narrative-format ::= ‹author› \(‹date›\)
author-date-parenthetical-format ::= \(‹author› ‹date›[, ‹page-specifier›]\)

when adding page specifiers to author-date narrative citations, the page specifier goes in its own set of parentheses, at the end of the clause.

#### specifying pages

page-specifier ::= p. ‹integer›[f.|ff.|-‹integer›]

f.|this page or the next
ff.|this page or any following.

### sections

＿Works Cited＿ and ＿References＿ are synonyms.
Sometimes the ＿References＿ section is also called 「reference list」
»Works Cited«/»References« are sections at the end of the work containing ＿full citations＿.
Properly, a »bibliography« should contain all works consulted, not those merely cited.
Often, 「bibliography」 is also just used as a synonym for ＿Works Cited＿/＿References＿.
A bibliography may also be a separate work listing works on a particular topic.
An annotated bibliography is a bibliography with author's comments on each work.
「Literaturverzeichnis」 is the german name for ＿Works Cited＿/＿References＿.
Quellenverzeichnis may be used as a synonym for Literaturverzeichnis, but is more properly a section used in historical science for identifying primary sources.

### citation style

A citation style is a set of rules of how to structure your citations.
the APA is the american psychological association.
the APA publishes a style guide, which is often autohyponymously also called APA.
Of the APA style guide, the thing that is most well known is its citation style.
The current APA edition is the 7th, released 2019.

table:citation style|in-body
APA|author-date

### multiple authors

et al. is used to abbreviate many authors in an academic setting


# databases

## geonames

Geonames is the worlds largest databae of geographical features, their locations, type, names, and names in alternative languages.
Geonames is updated via crowsourcing.
Geonames is licensed under CC BA.

# documentation

## RFC 2119 (this is basically done)

＞ The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED" "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119. 


⟮RFC 2119⟯ = ⟮BCP 14⟯
»⟮RFC 2119 / BCP 14⟯« ⟮defines⟯ ⟮a set of⟯ ⟮＿requirement level terms＿⟯.
»⟮A requirement level term⟯« is ⟮a term⟯ that ⟮indicates a requirement level⟯.
⟮＿The requirment level terms＿⟯ that ⟮＿RFC 2119 / BCP 14＿⟯ defines: ⟮required⟯, ⟮must (not)⟯, ⟮should (not)⟯, ⟮(not) recommeded⟯, ⟮may⟯, ⟮optional⟯.
Requirement level terms are only relevant if the spec is being followed.

⟮＿The requirement level terms＿⟯ that ⟮＿RFC 2119 / BCP 14＿⟯ defines are typically rendered in ⟮allcaps⟯.

### requirement level terms

⟮MUST⟯ = ⟮REQUIRED⟯ = ⟮SHALL⟯
⟮MUST NOT⟯ = ⟮SHALL NOT⟯
⟮MUST/REQUIRED/SHALL⟯ ↔ ⟮c_;MUST NOT/SHALL NOT⟯ = absolute requirement ↔ prohibition
⟮SHOULD⟯ = ⟮RECOMMENDED⟯
⟮SHOULD NOT⟯ = ⟮NOT RECOMMENDED⟯
⟮SHOULD/RECOMMENDED⟯ ↔ ⟮c_;SHOULD NOT/NOT RECOMMENDED⟯ = ⟮may exist valid reasons⟯ to ⟮not do⟯ ↔ ⟮c-;do⟯ the thing, but ⟮full implications should be considered and carefully weighed beforehand⟯
⟮MAY⟯ = ⟮OPTIONAL⟯
⟮MAY/OPTIONAL⟯ = ⟮truly optional⟯
for something foo marked with the requirement level term ⟮OPTIONAL⟯, ⟮any implementation not implementing foo⟯ ⟮MUST be able to interoperate⟯ ⟮c-;with an implementation implementing foo⟯ (and v.v.)

# programming (mostly)

# Expressions

An expression evaluates to = returns a value.
e.g. `6`, `6 * 2`, `true ? "foo" : "bar"`

# Statements

Statements are the fundamental unit of programming in imperative programming languages (used in some restricted sense).
Ergo, imperative programming languages (in some restricted sense) are those that use statements as their fundamental unit, in this sense a program consits of n statements.
Statements do not return a value.
Since statements do not return a value, they either do nothing or cause side effects.
var test = 2 + 6; → side effect of initializing a variable test
An expression statement is a statement that consists of a single expression.

## imperativeness

Imperative vs. declarative may be understood as a spectrum.
If imperative/declarative is understood as a spectrum, the more imperative something is, the more you're specifying the actual steps necessary for something to happen.
If imperative/declarative is understood as a spectrum, the more declarative something is, the more you're merely specifying what you want to happen, unconcerned about the steps.
On the imperative/declarative spectrum, functional languages are quite far on the declarative side.
Markup languages such as HTML are quite far on the declarative side of the imperative/declarative spectrum.

## statement separators and terminators

A statement separator is used to demarcate boundaries between two separate statements. A statement terminator is used to demarcate the end of an individual statement.
Semicolons are used in programming languages for two things: statement separators and statement terminators. When a language uses semicolons as statement separators, this allows you to write more than one statement on the same line.
Semicolons as statement terminators aren’t optional and are used to definitively mark the end of a statement.

Typically, even if programming languages have semicolons as statement terminators, they don't go after block statements. JS is the exception to this, where you can but don't have to do this.

semicolons as statement separators and statement terminators|C#|Java|Perl|Rust
semicolons as statement separators, newlines as statement terminators|Lua|Python|Ruby|sh
semicolons as statement separators and statement terminators, complex exceptions apply|JS

In languages which have newlines as statement terminators, typically the statement-terminating newlines can be escaped (generally by \ ) 
e.g. print("foo" + \
"bar")

## Blocks

In ⟮most programming languages⟯, a ⟮block⟯ is a ⟮statement⟯.  
However, in ⟮Rust⟯ (and in ruby to, though its weird, as blocks have the same syntax/are merely anon functions w/o arguments), ⟮blocks⟯ are ⟮expressions⟯. 

⟮Blocks⟯ ⟮contain/consist of⟯ ⟮one or more⟯ ⟮statements⟯. 
⟮In/with⟯ ⟮constructs⟯ or ⟮languages⟯ that are ⟮block-scoped⟯, ⟮a block defines a scope⟯. 
⟮Curly-brace/bracket languages⟯ are defined as languages that ⟮use curly-braces⟯ ⟮to define blocks⟯. 
Many programming languages have been influenced by C, sometimes called C-family languages.
C was a curly-brace language, and so many C-family language are curly-brace languages.

Examples of ⟮curly-brace/bracket languages⟯ I can write are ⟮C#⟯, ⟮ECMAScript⟯ → {⟮Javascript⟯, ⟮TypeScript⟯}, ⟮Java⟯, ⟮Perl⟯, ⟮Rust⟯, SCSS (but not Sass). 
Most ⟮curly-brace/bracket languages⟯ ⟮are thus because they are strongly influenced by⟯ ⟮C⟯. 
In some programming languages (JS, Lua, ...?) blocks can stand alone, merely creating a scope. In other programming languages, blocks must follow a certain statement.
In lua, blocks end with `end` (outside of repeat...until). They are begun by `do` when standing alone, or when after a loop, by `then` after an if condition, and by nothing after a function signature
In bash, blocks for if are delimited by then ... (possible else etc.) fi, for for and while by do ... done, for case by in ... esac
In ruby, blocks end with `end`. begin begins a dedicated block statement (and is the keyword for the error handling statement), but no other blocks
In python, pretty much anything (control structure, function, etc) that precedes a block ends with `:`. In Ruby by contrast (which otherwise may look pretty similar), nothing ends with `:`
In some languages, notably Ruby and Rust, block expression return the value of the last statement

liquid|{% keyword %} ... {% endkeyword %}
python|Sass|indentation

### bash

In bash, compound commands includes all control structures and block statements (which bash calls command grouping).
(ba)sh is not generally a curly-brace language, but it still allows creating block statements via {} (but also via `()`)
bash calls its block statements command grouping.
bash block statements/command grouping is what is used by bash functions.
The difference between bash block statements using () and using {} is that () spawns a subshell and thus a new scope, while {} executes the commands in the current shell.

## control structures

The default control flow is linear from top to bottom, this is called sequencing.
A thing that modifies control flow is a control structure. 

A control structure takes the normally linear flow of code and makes it somehow nonlinear.

Programming languages that use control structures outside of GOTO are structured programming languages.
Programming languages that do not use control structures or only use GOTO are non-structured programming languages, which are today quite rare.

Control structures are typically statements, however in Ruby and Rust, they are expressions.
In javascript or JS, most control structures take one statement after it, which can either be a normal statement or a block statement. A statement that does nothing is an empty statement
If control structures have conditions, they are delimited by...

()|C|JS|Java|C#|Perl
nothing|Python|Ruby|Rust|Lua
is complicated|shell

Conditions for control structures in ba(sh) are actually (a) command(s)
If the command(s) that make up the condition for a control structure return a zero exit code, they will be treated as true, and false otherwise.
Ergo, one can use the `test` command in the condition of a (ba)sh control structure, but one can also use any other command and rely on its exit status.
test is also available under the name `[` but requires a closing `]` in this case.
(ba)sh requires all operators and the [] themselves to be separated by spaces, since [ is actually just a symlink for test, and thus all of these are actually arguments for a command.

### choice/selection control structures

choice/selection control structures allows choosing between several alternatives based one or more conditons.
choice/selection control structures constructs are also just called conditionals.
In conditionals, any of the possible paths is called a branch.

#### if

The most common conditional is if/then/else. 
  
the if/then/(else) conditional is typically a statement (in rust, it's an expression).
An if/then(else) conditional is started by `if` in nearly all programming languages
the else arm of an if/then(else) conditional is started by `else` in nearly all programming languages

else if|C#|Java|JS|SCSS/Sass
elseif|lua
elsif|liquid|perl|ruby
elif|Python|(ba)sh
  
Anki has a if-like conditional to show something only if a field has content, indicated like: 
```
lang=text;
⟮{​{⟯⟮#FieldName⟯⟮}​⟯}
	Lorem Ipsum
⟮{​{⟯⟮/FieldName⟯⟮}​⟯}
```

#### conditional operator

The ternary operator is a conditional which is typically an expression. 
The ternary operator is more properly called conditional operator. 
The conditional operator typically has the syntax ‹condition› ? ‹iftrue› : ‹iffalse›. 
The conditional operator comes from C (more properly an early ancestor of C), thus most programming languages that are inspired by C have it. 
Example in JS:
`let attack = enemy.isFireType() ? this.attacks.thundershock : this.attacks.inferno;`
Languages that I can write that ⁑don't⁑ have a ternary/conditional operator with the typical syntax are Bash (more precisely, only exists for arithmetic expressions), Lua, Python, and Rust.

#### others

An if statement/expression, but reversed in its truth value, is an unless statement/expression.
unless statements/expressions use the keyword unless.
unless statements exist in liquid, perl, ruby


Some languages (Perl, Ruby), allow a one-line conditional, where the syntax is ‹expression› ‹conditional› (we might term this a postfix notation)
for the postfix conditionals in perl, ruby


in rust, `if let` instead of `if` allows for an if with pattern matching

#### switch

switch is a type of conditional.
the switch conditional is generally a statement.
the switch conditional generally has one condition, and then n branches for possible values.
Besides the branches for possible values of the conditional, the switch conditional generally also allows for a default case.
The default for switch statements is optional in JS
In many languages switch conditionals feature fallthrough, which is where it will continue even after the case ends, until it hits a break/return statement.
switch conditioals are generally started by the `case` keyword.
Different cases for a switch conditional are started by `switch` in Java, JS and by `when` in liquid, ruby.
In liquid, ruby, multiple cases are separated by commas.
The default case for a switch conditional is `default`  in Java, JS, and `else` in liquid, ruby.
Bash has a fucked-up syntax: case ‹expression› in {‹case›) ‹command› ;;} esac
In C-family languages, switch cases are generally syntactically equivalent to labels, and thus don't themselves create a new scope by default.

JS Syntax examples:

```
switch (expression) {
  ⟮case⟯ ⟮c2;⟯value1⟮c2;⟯⟮:⟯
   //Statements;
   ⟮default:⟯
}
```

#### guards

guardss are additional boolean expressions specified on branches of conditionals that must also evaluate to true if the program is to continue.
Of the languages I know, Rust has guards, introduced by `if`.

### Iteration/Loop control structure 

Control flow that repeats the code a number of times is called iteration/looping


#### Count-controlled loops

Count-controlled loops are loops that repeat a piece of code a certain number of times.
Count-controlled loops are often started with the keyword for.
Count-controlled loops are often called for-loops.
The typical syntax for count-controlled loops inheriting from C (e.g. C#, Java, JS, Perl) is 
for ‹delimiter›[‹counter-initialization›];[‹counter-end-condition›];[‹counter-change-per-loop›]‹delimiter›‹block›
for (;;) ends up just being an infinite loop
SCSS/Sass instead has the syntax @for ‹variable› from ‹lowerbound› to (excl)/through (incl) ‹upperbound›


#### Condition-controlled loops


A condition-controlled loop is aloop that repeats until a condition changes.
condition-controlled loops can begin or end with their condtion, in which case they will run at least 0 or at least 1 time.
condition-controlled loops that test at the beginning of the loop are often started with the keyword `while` and are often called while-loops. 
condition-controlled loops that test at the end of the loop are often started with the keyword do, then a block, then end with the keyword while followed by the condition and are often called do-while-loops.
Most programming languages I know have while and do-while loops, in fact I don't think I know a programming language that doesn't have a while loop.
Perl and bash have an until loop: a while loop with an inverted condition (analogous to unless).
Lua also has a while loop with an inverted condition that tests at the end of the loop with the syntax repeat ... until
in rust, `while let` instead of `while` allows for a while with pattern matching


#### Collection-controlled loops 


A collection-controlled loop is a loop that loops over all elements of a thing.
Collection-controlled loops are commonly called foreach loops.
Collection-controlled loops most commonly start with the keyword `for`, but then feature a different syntax than count-controlled loops. In perl, they instead start `foreach`.
Collection-controlled loops generally work on iterators, or by transforming the thing into an iterator implicitly.
Lua: for ‹expression› do
bash, Liquid, Python, Ruby, Rust: for ‹expression› in ‹iterable› ...
Java: for (‹type› ‹element› : ‹iterable›) ...
JS: for (‹variable› in ‹object›) ... (only used to iterate over all key-value pairs of an assoc array)
In a JS forin loop, the thing assigned to the variable is the key, not the value.
for (‹variable› of ‹iterable›) ...
SCSS: @each ‹variable› in  ‹iterable›
Some languages have collection-controlled loops that are called as methods on a collection or iterable (these are higher-order fucntions)
iterable/enumerable.each(block)|Ruby
somearr.forEach(anonFunc)|JS

When iterating through something that returns multiple values, the expression may need to destructure the values out, or may just list n variables with commas, depending on the language

bash for in is actually the only loop using for that it has. It's also weird in that what it loops through is an $IFS separated list

Infinite loop

loop|Ruby|Rust

takes a block in ruby




Many languages provide a statement which allows skipping the current (continuing with the next) iteration of a loop.
Most languages use the continue statement to continue with the next loop, Perl and Ruby use the next statement.
Many languages provide a statement which allows ending/exiting the loop.
Most languages use the break statement to end/exit the loop, Perl uses the last statement.
In Rust, you can pass an argument to the break thing (break ‹something›) to have that be the return value of the block expression


Sometimes, loops have an else clause. In python, this runs at the end if we never break out of the loop. In liquid, this runs if the loop is empty

(loops with reversed condition do not count as separate kinds of loops)
lang|count-cont|cond-cont|col-cont|infinite
lua|1|2|1|0
liquid|0|0|1|0
Python|0|1|1|0
JS|1|1|2|0
SCSS|1|1|1|0
Rust|0|1|1|1

## Labels

A label in a programming language is a sequence of characters that identifies a location within source code. In most languages labels take the form of an identifier, often followed by a punctuation character (e.g., a colon). 
JS and C have labels.
JS label syntax: ‹name›:
Labels can be used to break out of a loop that is not the enclosing one.

## other statements

### empty statements

Empty statements are useful if a statement is required syntactically, but there is nothing to do, e.g. when writing outlines

;|JS|C#
pass|Python
:|(ba)sh

: is actually more complicated. It is kinda similar to true, and is therefore used as a condition for an infinite while loop.

# Identifiers

In a wide sense, "name" is synonymous to identifier, in a narrow sense it is an identifier
An identifier is a thing that refers to/labels an object or class/set/collection of objects.
a unique identifier is an identifier that labels a thing uniquely in a given context.
UID   unique identifier
An identifier is opaque if it provides no information about the thing it identifies
A transparent identifier provides information about the thing it identifies.

Aliasing is referring to the same location in memory by multiple different identifiers.

UUIDs/GUIDs are formats for unique identifiers that make it very likely for them to be unique.
UUID|Universally Unique Identifier
GUID|Globally Unique Identifier
UUID=GUID
UUIDs/GUIDs are 128 bit long, which makes it very likely for them to be unique.

## name resolution

name resolution is the associating of identifiers with the correct things (e.g. variables)

### Name binding

Name binding is the association of entities with identifiers.
For an identifier to reference something is to the identifier bound to that thing.
Binding is intimately connected with scoping, as scope determines which names bind to which objects.
static = early binding is name binding during compile-time
dynamic = late binding is name binding during runtime
dynamic/late binding enables duck typing
duck typing is calling a method without caring about its type, and seeing if it works.

### namespaces

a namespace is a context in which names are unique.
Names within a namespace are sometimes called local names.
a namespace itself generally has a name.
Within a namespace, only the local name is needed to refer to a thing.
Outside of the namespace, the namespace and the local name are needed to refer to the thing.
In hierarchical namespaces, namespaces are nested.

## Scope

the scope of a name binding is the part of a program where the name binding is valid.
for something to have x-scope is to only have the name binding be valid within x.
a variable with foo-scope is often called an foo-variable

### Lexical ＆ dynamic

Static scope is another name for lexical scope.
Lexical scope is where scope is determined by where in the source code (a reference to) a name binding is.
Lexical/static scope is contrasted with dynamic scope
Dynamic scope is where scope is determined by where on the stack something is.
Pretty much all programming languages today use lexcial scope. Bash is the example, using dynamic scope.

### global/local scope

The scope that is the entire program is global scope.
A variable that does not have global scope has local scope.

Local scope is often either block or function scope.

In some languages, things that live within global scope are properties of an object called a global object.
In JS in browsers, generally, the global object is Window.
within ⟮workers⟯, the ⟮global scope⟯ is `⟮WorkerGlobalScope⟯`
within ⟮service workers⟯, the ⟮global scope⟯ is `⟮ServiceWorkerGlobalScope⟯`
The mixin `⟮WindowOrWorkerGlobalScope⟯` describes ⟮the common features⟯ of `⟮Window⟯` and `⟮WorkerGlobalScope⟯`
The `self` property of a WorkerGlobalScope returns a reference to the WorkerGlobalScope itself.

Without ⟮crates/unsafe code/etc.⟯, ⟮globals⟯ in Rust can only be ⟮constants⟯.

#### Variable scope

In general, if you declare block- or function-scoped variables on the top level, these will be global or at the least, global to the module.

Block-scoped variables
my|perl
local|lua
let|JS
ø|Ruby
ones defined within a block|C#|Java|Python

Function-scoped variables
var|JS

Global variables
ø|lua|perl
$|Ruby

Variable scope in python is not determined by keyword but by context.
In JS, variables declared without a keyword become properties of the global object

### shell scope

In (ba)sh, the thing that determines scope is the shell.

running a script spawns a new subshell, unless you source it.
Sourcing a thing is done by `source` or by `.`
environment variables have a scope that allows access in current shells and subshells.
shell variables have a scope of the current shell only.
Variables are shell variables by default.
Exporting a variable turns it from a shell variable to a environment variables.

env|show all environment variables

export|export a variable
export -n|unexport a variable

### Shadowing

Masking = shadowing
Name masking/shadowing is when a name in a inner scope overrides that same name in an outer scope
Variable masking/shadowing is name shadowing involving variables
In rust, shadowing allows for 'changing' tye type of the variable (really merely declaring a new variable)


### Hoisting

Hoisting moves declarations but not initializations to the top of the scope.
Hoisting is mainly a JS concept.
in JS, var variables and function declarations (but not function expressions) and hoisted.

## Case

snake_case|variables, methods (, symbols)|ruby|python (use underscores sparingly)
UpperCamelCase|classes|C#|Javaruby
SCREAMING_SNAKE_CASE|constants|ruby
camelCase
snake_case|shell variables|(ba)sh
SCREAMING_SNAKE_CASE|environment variables|(ba)sh
_leading_underscore_snake_case|fake private variables|(ba)sh

most programming languages are case-sensitive as regards identifiers.

## Naming

While there is variety in what is allowed in a identifier name, most commonly it is [a-zA-Z0-9_]
JS also allow $ in a non-sigil way in identifier names.
JS identifiers may not start with a number, but with any other allowed character.
In general, identifiers may not be keywords.

# values, variables, types

# Values

A literal is a value which is written into the source code as-is and therefore is fixed.

## Memory-management

### Ownership

In rust, eveary value has exactly one owner.
Owners are variables(/constants).
Moving happens when we assign a value to a different owner and thus the first owner is invalidated.
Assigning a value to a second owner produces a move unless the type implements Copy, in which case it instead calls copy.
Rust says values that are moved when reassigned (= which don't implement Copy) have move semantics, values that are copied (= which implement Copy) implement copy semantics.
A type can implement Copy if all of its components (parts) implement Copy.
In rust, all primitves implement Copy
Assigning as an operation that forces moving includes passing to a function and returning from a function.
When a owner goes out of scope, a value is dropped.

to allow cloning(), implement the Trait `Clone`. This does not change the semantics, since clone() must be called manually

# Variables

A variable is an identifier which is associated with a storage location which contains a value.

## Declaration and initialization

Declaring something is saying what an identifier means.
In most languages, but not in JS and Python, declaration at the very least fixes the kind of entity the identifier refers to. 
In statically typed languages, declaration generally fixes the data type of an identifier.
To initialize something is to assign a value for the first time.

declaring: var bla;
initializing: bla = 5;
declaring and initializing: var bla = 5;

Trying to read from something undeclared in general produces an error in most programming languages, in sh however it merely produces an empty string.
In JS, a declared but unitialized variable has the value undefined. In most other languages, reading from an unitialized variable produces an error.
In python there is no such thing as variable declaration (however, using a name you haven't used before still creates an error)
Redeclaration may or may not produce an error. In JS, it does not produce an error for var, but does for const and let.

## assignment

Setting a variable/constant to a value is known as assignment.
= is used as the assignment operator in most programming languages
sh is special in its assignment operator, since it does not allows spaces on either side
SCSS/Sass uses : as the assignment operator.
In most languages, assignment expressions evaluate to the value assigned.
Many languages have combinations of their math/string concat and assignment operators to combine these two operations (e.g. +=)

### Destructuring

Destructuring is binding variables to values in a way that does not correspond to the 1 variable - 1 value pattern

In many languages, the comma can be used for multiple assignment, most commonly like so:
a, b = 1, 2|Python|Ruby
This is often a form of destructuring under the hood.

[var1, var2] = [value1, value2] or preexisting array|JS|Python|Rust
var1, var2 = [value1, value2] or preexisting array |Python|Ruby
(var1, var2) = (value1, value2) or preexisting tuple|Rust

In general, you can destructure that language's linear collections (esp. if primitive) and iterables.
In JS you can also destructure the assoc array structure.

Destructuring an array(like) requires array delimiters ([]) in JS, python doesn't want any delimiters, and python wants a tuple, which may mean no delimiters or () if needed for nesting etc.
use normal default value syntax to assign default values in array destructuring|JS only
combine spread syntax/splat operator w/ destructuring|JS|Ruby|Python
var1, *var2 = [1,2,3]
[var1, ...var2] = [1, 2, 3];
=› var2 = [2, 3]
Ignore a single value in destructuring
, (e.g. var1,,var2)|JS
_, (e.g. var1,_,var2)|Python|Ruby|Rust

Ignore multiple values in destructuring
*_, (e.g. var1,_*,var2 )|Python|ruby
.. (e.g. var1, .., var2)|Rust
Not possible|JS

nested destructuring
((target, _), _) = [["foo", "bar"], "baz"]|Python
[[target]] = [["foo", "bar"], "baz"] |JS
not possible|ruby

Destructuring can be a cheeky way to swap variables

When destructuring out of assoc arrays in js, this looks like

{nameofkey: nameofvariableyouwantthevaluetoendupin} = {nameofkey: value}
If the nameofkey and the nameovariableyouwantthevariabletoendupin are the same, you can do:
{nameofkey} = {nameofkey:value}

In rust, there is a set of destructuring/pattern matching constructs that can only be used in enums or if let statements.

putting an enum or struct with variable names inside in a match or on the left of an if-let will assign the variables to the values contained within.
e.g. `match { Some(foo) =› ... }` will match Some() containing some value and assign that to foo
e.g. `match { Run{ distance: dist, direction: dir } =› ... }` will match a `Run` and assign its distance field to dist and its direction field to dir.

pattern matching checks if a thing matches a pattern.
In rust, the destructuring syntax is part of the larger idea of pattern matching. (and the syntax that we use for destructuring is a subset of the syntax of patterns)
Many pattern matching things can be used for destructuring (and are the equivalents of the destructuring constructs of other languages).
Beyond or at the same time as destructuring, pattern matching is used for match and if let conditions. 
In rust, patterns can either be
refutable|pattern can fail to match|Some(x) (does not match if value is not Some)
irrefutable|pattern cannot fail to match

match is a conditional that uses pattern matching for its conditions, and forces checking to be exhaustive.
Rust of the languages that I know has a match conditional (using the keyword match). Of the languages I don't know, the ML family and functional languages have match conditionals.
in rusts's match, condition and expression are separated =›

pattern1 bar pattern2|pattern 1 or pattern 2

Within rust pattern matching/destructuring, we even can destructure a thing out of a reference: let ＆foo = somereference

## Sigils

In programming, a sigil is a symbol(s) affixed to a variable name.
Sigils are generally used to show that something is a variable, show its type, or ts scope.
In perl
\$|Scalars
@|Arrays
%|Associative Arrays (Perl calls them Hash)

In ruby
\$|global variables
@|instance variables
@@|class variables

In sh, $ is a sigil-like used for various kinds of expansion
In SCSS/Sass, any variable requires teh $ sigil
 

## Declaring multiple variables

a, b = 1, 2 (or e.g. returnTwoValues()) (lua, python)

## Constants (and not)

Mutability is whether something can be changed after inital creation. Something is mutable if it can be changed, and immutable if it can't.
Different things can have mutability: Objects, variables, (though generally not primitves).
Some languages make a difference in which keywords are used to declare constants and variables.
Constants are immutable, while variables are mutable.
In most languages, constants are written in all upper case.

Keyword for constants:
const|JS|Rust
final|Java

Keyword for variables:
let|Rust

In rust, even variables are immutable by default, and the keyword mut makes them mutable, the difference to consts being that consts cannot be declared mutable.
Rust requires its consts to always be type annotated.
In JS, consts are always block-scoped.
In some languages (JS), consts must be initialized in the same statement as they are declared.

The term magic number or magic constant refers to the anti-pattern of using numbers directly in source code. 
Instead of magic numbers (the antipattern), one should instead use constants.

## Default variables

In Perl there is a special variable $_. There are many places in programming language Perl where if you do not explicitly specify a variable, the variable will be used $_. There are key words that read the values from this variable, and there are those which set of values in this variable. (also sometimes exists as @_ and %_)

# (Data) types

An abstract data type is defined in terms of its behavior or more specifically its semantics, instead of in terms of its syntax.
If an abstract data type is a description of what something does, a data structure is how something does it.

A null pointer/reference/type/value indicates that we're not referring to a valid thing
Datatypes implemented in a programming language can either be scalar or compound/composite
Bash is fun in that it does not have data types at all, in truth all values are strings

To clamp a value is to specify an upper and a lower bound, and keep the number within those values.

## primitives and composites

Primitive may refer to a data type that is provided in a programming language as a basic building block.
Composite data types are built from primitive data types. 
Primitive may also refer to a type that has built-in language support.

#### primitive types in different languages

C#: int, float, bool, string, char, double
Java: byte, short, int, long, float, double, char, String, boolean
JS: Number, boolean, null, undefined, string, object, array
Rust: 
  scalar: integer, floating-point numbers, booleans, chars
  nonscalar: tuple, array
Python: integers, floats, complex numbers



## Type Systems

A (data) type consists of a set of values that something with that type can assume.
In implementation, each value of a type has a unique (within the type) binary representation.
Typing can also be understood as how to interpret a series of bits.
A datatype T1 whose set of values is a subset of a datatype T2 is a subtype of T2.
A datatype T1 whose set of values is a superset of a datatype T2 is a supertype of T2.
A language may also be untyped: neither variables nor values have type.
An example of an untyped language is bourne shell, which is completely untyped.
Bash supports a very mediocre type of typing via builtins such as declare.

### Dynamic vs Static typing

Dynamic typigng: type checking at runtime ≈ values have type
Static typing: type checking at compile time ≈ variables have type

Dynamically typed languages I know: JavaScript, Lua, Python, Ruby
Statically typed languages I know: C#, Java, Perl (with regards to the scalar, array, hash distinction), Rust, TS
TS makes the normally dynamically typed JS statically typed

### Type inference/manifest

Explicit/manifest typing is a feature of a type system where the type has to be explicitly declared.
Implicit/latent typing is a feature of a type system where the type is not explicitly declared.
Implicit/latent typing  ↔ Explicit/manifest typing 
Type inference is a rough synonym for implict/latent typing, but is often used in contexts where the language is otherwise generally explicitly/manifestly typed.
Only statically typed languages can usefully be explicitly/manifestly typed
Type inference in C#: var 
in TS and Rust, often type inference is possible automatically 
Type inference in TS/Rust is more likely to work for anonymous functions
In languages with manifest typing, variable declarations require typea annotation.

On the negative side, manifestly and statically typed languages can be more effort to write. 
On the positive side, manifestly and statically typed languages 1) dramatically lower the chance of bugs, especially type errors (logic type), 2) provide better linting 3) provide better IDE code completion and similar.

(literal) type widening is the fact that TS will infer a primitive type and not a literal type for literal values.

Often, when rust can't infer the type, we need to use turbofish notation ( :​:‹type›)

#### const assertions

In TS, const assertions are a special case of type assertions that influence type inference rather than specifying a specific type to cast to.
const-assertion ::= ‹type› as const;
Const assertions make TS infer the narrowest possible type. 
Specifically, const assertions make three things happen:
1. type widening.
2. object literals get readonly properties.
3. arrays become readonly tuples.

#### type narrowing

Type narrowing is a form of implicity type change where the type of a thing is made more precise based on which types could possibly exist in that context.
In TS, pretty much anything that could be reasonably assumed to narrow does.
Assigning to a variable with something of a more loose type undoes the narrowing performed that is narrower than that loose type.
Narrowing can produce the never type if the thing was narrowed to impossibility
A type guard is any check that narrows the type of a thing.
In TS, type guards for basic types uses typeof.
in TS, a type predicate is a function that returns a boolean value. The boolean value determines if the thing is the specified type.
A type predicate is specified by adding ` is ‹type›` to the end of the return type.
In effect, using a type predicate acts as a custom type guard.

#### Type annotation

Specifying the type of a thing (esp. a variable/constant) by writing the type into the code is known as type annotation.
Languages with manifest typing generally require type annotation for variable/constant declarations, parameters as well as return types.
In most (esp. C-family) languages, type annotation goes before the variable/constant.
In Python, Rust and TS, type annotation looks like so `: type`
Python supports type annotation since Python 3.5

##### Type aliasees

Type aliases are names for types thsat abbreviate longer type descriptions.
Where type aliases exist, they generally use the type keyword.
Type aliases exist in TS, Rust
`type ‹name› = ‹type-expression›`

##### Interesting keywords

### Type errors

Type safety is the dgree to which a programming language prevents logic-type type errors in favor of static-semantic type errors.
A logic-type type error is caused by treating a value as the wrong type.
A type-safe language is a language that throws more static semantic type type errors instead of logic errors.

### Conversion, coercion, casting and context (plus truthy/falsiness)

Context is a term usely used in programming, and with much variation.
We can think of context related to types as creating a situation in which things will be coerced to certain types automatically.
In python, bool() is said to create a boolean context = convert a value to true or false depending on their truthy/falsiness.
Something is falsy if it evaluates to false in a boolean context, and truthy if it evaluates to true in a boolean context.
Most langauges treat at least their null type(s) and their false type as falsy.
JS additionally treats empty strings, 0 and NaN as falsy.
Languages like JS or Python establish a boolean context (coerce to boolean) within their conditions for loops, conditionals, etc. Other languages (C#, Java, Rust) treat using non-booleans in these situations as an error, i.e. not create a boolean context.
In perl, context is most often used with the scalar/list distinction.
scalar() generates a scalar context
Since (ba)sh doesn't have any types but strings, it needs specific contexts to do certain tings
math context is required to do math
math context|$(()), (()) and the command let

##### Type annotation keywords

In general, certain types are generally indicated similarly across programming languages (though there is variation)
Integers|int|not Rust
Floating-point numbers|float|not Rust
Booleans|bool|C#, Rust
Booleans|boolean|Java
Characters|char|C#, Java, Rust
Double-precision floating-point numbers|double|C#, Java

#### Conversion

Type conversion is explicitly using a function or the like to change the datatype of something.
All pythons types, called as a function, convert to that type (e.g. list(), bool(), int())
Ruby has a set of methods that have the syntax foo.to_‹char› that convert to that type (e.g. to_i, to_f, to_s, to_sym)

#### Coercion

Type coercion is implicitly forcing a value to be treated as of a different datatype.
JS will coerce extensively in the case of operations w/ mismatched types.
Concatenation of non-string w/ string|coerces non-string to string
use of booleans w/ math operators|coerce to 0/1
In contrast, pythons operators rarely coerce.

#### Casting

Type casting is asking the programming language implementation to treat a value as a certain datatype temporarily.
Casting will go wrong if the vlaue cannot be treated as teh casted type.

!!type value|YAML
(type) value|C#|Java

Type assertions in TS are the equivalent of type casting in other languages.
In TS, if ⟮you know something about a type that TS doesn't⟯, you can use ⟮type assertions⟯
TS type assertion syntax: prepending ⟮‹some_type›⟯ or appending ⟮as some_type⟯


### Firstclassness

An entity is said to be first-class in programming if you can ⟮Do most other things you can do with objects/values⟯
typical features of entities that are first-class in a certain language are e.g. ⟮Can be stored in variables/data structures, can be passed as a parameter to callable units, can be returned, tec.⟯
An entity that is first-class is called a first-class citizen.
Lua: all values

## bottom type

A bottom type is the subtype of every other type.
A variable with bottom type can take no value. (there is no value that can be assigned to a variable with the bottom type.)
A thing with bottom type can be assigned to anything at all.

A bottom type is used to indicate noncomputability.

no bottom type|most languages
! (called the never type)|Rust
never|TS

## unit type

A unit type is a type that only allows a single value.
A variable with unit type only ever takes things of the unit type or the bottom type.
A thing with unit type is only assignable to other things with unit type or the top type.

()|Rust

Rust's () for the unit type is abstracted from the idea of a tuple with no elements.
In Rust, things without a return value implicitly return ()
In rust, a struct without fields is also an unit type, called the unit-like strct.

in TS, there are three unit-like types: `null`, `undefined` and `void`
in TS, `null` is the only proper unit type: only things of type `null` plus `never` and `any` (of course) are assignable assignable to `null`, and `null` can only be assinged to `null` plus `unknown` and `any`.
in TS, `undefined` is only unit-like, since besides the proper relationships one may also assing things of type `undefined` to variables of type `void`.
in TS `void` is only unit-like, since besides the proper relationships things of type `undefined` are assignable to variables of type `void`.
in TS, if `strictNullChecks` is enabled (which is not the default behavior, but my default assumption otherwise the type system becomes a mess) `null`, `undefined` and `void` act like unit types, such that nullable types need to be literally declared as option types.
in TS, if `strictNullChecks` are disabled, all types are nullable.

### Literal types

A literal type is unit type whose value is specified via the literal of another type (e.g. 4 or true or "ara ara")
in TS, the types of constants are a literal type of thier value.

## combination of other types

### intersection types

An intersection type specifies a type which must satisfy all constraints that individual types satisfy.
While it would be technically possible to create intersection types of primitive types, it is pointless: There is no value that could possibly satisfy the constraints e.g. 'is a string' and 'is a number' at the same time, since they are disjoint.
intersection-type ::= ‹type› ＆ ‹type›

### Union type

#### definition

A union type specifies a number of types that anything with the union type as type may take.
A union type can hold a value that could take on several different but fixed types.
A union type can be thought of as a type that has several "cases", each of which should be handled correctly when that type is manipulated.
In type theory, a union type is a sum type.

#### use

with ⟮union⟯ types, you can only use things that ⟮all of the relevent types can do⟯, unless you ⟮narrow them down⟯

#### in various languages

Common syntax: type1 | type2 ...
Syntax for creating arbitrary union types exist in Python, TS and graphQL

#### Tagged unions

A tagged union type is a union type where each of the types has a tag, which is used to determine which type is currently in used.
What rust calls enums is more properly a tagged union.
in TS, a thing similar to tagged unions is called a discriminated union.
in TS, discriminated unions are implemented by a union type of other types with a shared field.
In a discriminated union, TS can narrow based on checking a shared field.

##### Rust

in rust, tagged unions implements the tag by means of the name of the enum.
in rust, tagged union variants may be tuples, structs, or unit-like

###### strum

strum|enum ‹-› string manipulation

to make enums ready for use with strum, one needs to derive the relevant trait onto it, and also use attributes on the enum or the variants.
Strum attributes use strum()

Enum → str|derive strum_macros::ToString
Enum → str message|derive strum::EnumMessage|Enum.get_message() ＆ Enum.get_detailed_message() (return options)
str → Enum|derive strum::EnumString|Enum::from_str()

##### Types with two possible states

###### Option type

An option type is a type that represents an optional value.
An option type can generally take on a state representing it is empty, or a state representing it is full, and wrapping around another value.
In rust, the option type is its alternative for null, which it does not have.
In rust, the option type is implemented as an enum.
In rust, the option type is 
pub enum Option‹T› {
  None,
  Some(T),
}

In general, either option types or nullable types will be used to represent the absence of a value in a given language, but no both.

###### Result type 

A result type is a type which can be either of two variants/states, a success type holding the result, or an error type holding the error message.
in rust, the result type is `Result`, looking like enum Result‹T, E› { Ok(T), Err(E)}

###### Commonalities

####### logic with methods

|if None|if Some
‹OptionOrResult›.and(‹AnotherOptionOrResult›)|None/Err|‹AnotherOptionOrResult›
‹OptionOrResult›.and_then(‹callback›)|None/Err|‹callback›(‹OptionOrResult›)
‹OptionOrResult›.or(‹AnotherOptionOrResult›)|‹AnotherOptionOrResult›|None/Err
‹OptionOrResult›.or_else(‹callback›)|‹callback›|None/Err
‹OptionOrResult›.map(‹callback›)|None|call callback with contained value and return option with returned value
‹OptionOrResult›.map_or(‹default›, ‹callback›)|‹default›|call callback with contained value and return option with returned value

####### cloning and copying

the cloned/copied methods of Options/Results takes an Option‹＆T› or ‹＆mut T› or a Result‹＆T, E› or ‹＆mut T, E› and returns an Option‹T› or Result‹T, E› by cloning/copying

####### conversion

Result‹T, E›.ok() → Option‹T›

####### ? operator

In rust, the ? operator takes a `Result` or `Option`
In rust, the ? makes a `Result` evaluate to the value inside the `Ok` if `Ok` or exit out of the nearest function, returning an `Err`.
In rust, the ? makes a `Option` evaluate to the value inside the `Some` if `Some` or exit out of the nearest function, returning a `None`.
The ? is implemented via the trait std::ops::Try

####### unwrap ＆ expect

unwrap and expect can be called on options and results.
unwrap and expect are similar that they return the value if the type is Ok/Some, and panic otherwise.
the difference between unwrap and expect is that expect allows us to choose our error message.

#### Nullable types

##### definitions

Null is not typically its own type (since it would be a useless unit type), instead other types are generally nullable.
A type being nullable means it can take a special value null/nil/undefined instead of the usual possible values.
We can understand nullable types as an union type between usual type | null type

##### keywords for the special value null

nil|lua|liquid|ruby
null|C#|Java|JS (secondary)
undefined|JS (primary)
None|Python
there isn't one|Rust

##### language peculiarties

###### liquid

Liquid has a special null-like type that is returned when accessing a deleted object called EmptyDrop

###### JS

In JS a type is nullish if it is null or undefined.

###### graphql

In GraphQL, an exclamation mark `!` afte a type indicates that the field is non-nullable.

### type manipulation

in most languages, types are limited in how they can be used:
contain predefined primitive types|all statically typed languages
new data structures create corresponding types|all statically typed languages (I know)
new records create new corresponding types|all statically typed languages (I know)
can create type aliases|Python, Rust, TS
can create types that are combinations of other types|TS
can create new types by reasoning about other types|TS

type manipulation is a not-so-common cover term for creating new types by reasoning about other types

the `keyof` operator takes an object type and returns a union type of its keys.
the TS-specific `typeof` operator returns the type of a non-type thing.
the TS type `ReturnType‹T›` corresponnds to the return type of T (T must be a function ＊type＊)
An indexed access type, given a key of a field, allows us to get the type of the value of a field of another type, much as indexing an assoc array with a key returns its value.
Indexed access types use the same [] syntax as normal accessing.
Conditional types evaluate to different types depending on an expression.
conditonal-type-specifier ::= ‹generic› extends ‹type› ? ‹type› : ‹type›;
the generic which is the first thing conditional type can be used in the true branch for further manipulation/selection.
in the ‹generic› extends ‹type› of a conditional type, within the ‹type› one may declare an additional generic via `infer ‹generic›`, which we than can use in the true branch
A mapped type maps all keys of another type to a certain type.
mapped-type-specifier ::= \[‹type› in keyof ‹type›\]: ‹type›;
more on mapped types: https://www.typescriptlang.org/docs/handbook/2/mapped-types.html
Template literal types use JS template literal syntax to expand to all possible string literal types that this could assume.

mapped types

### TS Utility types

TypeScript provides several utility types to facilitate common type transformations.

## top type

A top type is the supertype of every other type.
A variable with top type can take any possible value. (any possible thing can be assigned to a variable with top type)
A thing with top type can only be assigned to another variable with top type (in languages that have static typing).

A top type is often also the type that is at the top of the class hierarchy, in languages where such a thing exists

object|Python
unknown|TS
UNIVERSAL|Perl
java.lang.Object|Java
System.Object|C#
BasicObject|Ruby

In ruby Object inherits from BasicObject and generally acts as the top type for most purposes.

In TS, `any` is like a top type in that any value can be assigned to variables of type `any`.
in TS, `any` is like a bottom type in that things of type `any` can be assigned to anything.
Most languages with dynamic typing act as if everything had type `any`.
in TS, unless `noImplicitAny` is enabled, TS will often fall back to `any`, acting like default JS in these cases.
in TS, `{}`, `Object` are the same type.
in TS, `{}`/`Object` are nearly top types, you can assign everything but `null`, `undefined`, or of course `unknown` to `{}`/`Object`.
by contrast, `object` (notice the case) is any non-primitive type, and thus not even nearly a top type.

## object types, interfaces and classes in TS

object type = objects literals as types, generally declared with the type keyword if not inline.
in TS, object types, interfaces and to a certain extent classes share a lot of syntactic similarities.
object types, interfaces (and to a certain extent classes) both fundamentally a similar syntax to js objects.

type|keyword
object type|type
interface|interface
class|class

basic field|‹fieldname›: ‹value›,|object type, interface, class
optional field|‹fieldname›?: ‹value›,|object type, interface, class
methods|‹fieldname›: (‹ts-param-list›) =› ‹return-type›, (syntax 1/2)|object type, inteface
methods|‹fieldname›(‹ts-param-list›): ‹return-type›, (syntax 2/2)|object type, inteface
make thing itself callable (i.e. a function)|(‹ts-param-list›): ‹return-type›,|object type, interface
make thing itsef newable|new(‹ts-param-list›): ‹return-type›,|object type, interface

TS object types, interfaces and classes can all be defined over n generics.
prefixing a field of a object type or interface with `readonly` makes it a constant field.
in TS, object types, interfaces and classes all can have getters ＆ setters.

in TS, multiple interfaces with the same name will be merged into one, multiple object types or classees with the same name will throw an error
in TS, while interfaces can do many more things, interfaces can be implemented by classes just as in languages such as Java.
in TS, interfaces can be `extend`ed with other interfaces.
(TS) The main difference of using interfaces and extends vs intersections is that interfaces w/ extends will overwrite if there are properties with the same names but different signatures, while intersections will merge them.

(TS) An index signature specifies that for all keys of a specific type (in theory, but in fact I think they can only be string or int in ts anyway), the value will be of the specified type
Syntax of an index signature: [foo: sometype]: sometype2
The ⟮name⟯ of an index signature ⟮does not matter⟯.
^source: https://basarat.gitbook.io/typescript/type-system/index-signatures

Partial‹T›|Returns T where all keys have been set to optional
Required‹T›|Returns T where all keys have been set to required.
Readonly‹T›|Retunrs T where all keys have been set to readonly

## boolean

A boolean data type is a type that has one of two possible values, indicating
truth values.

true/false|C#|Java|JavaScript|Lua|Ruby|Rust|TOML|YAML
True/False|Python|(YAML)
yes/no|YAML
no boolean type, only truthy/falsiness|Python

YAML is not boolean keyword case sensitive

## Symbols

Symbols as a datatype are guaranteed to be unique, and generally have a human-readable representation.
The fact that symbols are guaranteed to be uniqe mean that they are equal only to themselves.
In some languages, two symbol literals with the same name are equal to each other, for example in Ruby (:foo == :foo # true)
In some languages, two symbol literals with the same name are not equal to each other, for example in JS (Symbol("foo") === Symbol("foo") // false). Even in those languages, the same instance of a symbol is always equal to itself
Often, the main use of symbols is as object keys to avoid key collisons, or to act as alternatives to enums
Internally, symbols are often represented by a number.

:name|Ruby
Symbol("name")|JS

## references

A reference is a value that allows indirect access to another value.
A pointer is a type of reference that allows indirect access to a thing by storing its memory address.
Handle is an ambiguous concept, but is most commonly seem as a synonym to reference.
dangling reference/pointer = wild reference/pointer
A dangling/wild reference/pointer is a reference that doesn't reference/point to something valid
Link rot is the process of links becoming dangling/wild references.
Multiple indirection is having references to references (and so on).

A smart pointer is a pointer with some other features (e.g. automatic memory management or bounds checking).
A fat pointer is a pointer that stores some extra data besides the address.

What Rust and C++ call references are probably more like pointers.
In Rust and C++ the ＆ operator takes a reference of something.
In Rust, any references of a type have the type ＆‹type›, while in C++ they have the type ‹type›＆.
In Rust, to take a reference, one must prefix the thing one is taking a reference of with ＆, while in C++ reference-taking is implied if one assigns to a reference-type variable.
In Rust, a reference to an element in a data structure counts as a reference to the whole data structure for the purposes of borrow semantics.
In Rust, references are immutable by default, and must explicitly be declared mutable with ＆mut.
In Rust, the act of taking a reference is known as borrowing, since implements specific semantics/rules.
In Rust, correct use of borrow semantics are checked at compile time by the borrow checker.
Borrow rules:
1) borrows cannot last for a larger scope than the owner
2) you may only have n references to a resource or exactly one mutable reference to a resource, but not both at the same time.
Only having either n references or exactly mutable reference to a resource implies that you cannot assign to a variable borrowed elsewhere, since assigning requires an implicit mutable borrow (!).
x = 22 is equivalent to *(＆mut x) = 22
Dereferencing takes a thing that is a reference and returns the referenced thing, allowing you access to the value behind the reference.
you can also dereference on the left-hand side of an assignment to assign to the referenced piece of memory.
In most C-family languages (of the ones I can write, C# and Rust) to dereference you use the dereference operator *.
In Rust, the Trait that controls the behavior of the dereference operator is Deref, which has a method deref implementing dereferencing.

In Rust, a slice is a view into a block of memory by means of a pointer that also stores a length.
In Rust, any linear collection type can be sliced.
In Rust, slices are considered a reference and have the same semantics as references do.
Rust slices can bu used for the same reasons one would use slices in e.g. Python (though without the ability to step or reverse), but they are not copies, but fundamentally just views.
getting a slice: ＆[mut] ‹thing-being-sliced›\[‹n›(..|..=)‹m›\]
slices can be indexed just like anything else.
Slices' length may not be known at compile time, and so rust can't guarantee that indexing into a slice will not produce an error.

when cloning a reference ＆T, rust will return T.
to_owned() is part of the Trait ToOwned.
there is a blanket implementation for ToOwned for anything that implements Clone.
the reason to use to_owned() is for types where returning T of ＆T is not desirable, namely ＆str, hence to_owned() returns a String for str.

In rust, string literals are slices, specifically they are slices into the rodata section of the object file.
this means that instead of being ＆str, string literals are in fact ＆'static str
In rust, `String` and `str` are both UTF-8 byte sequences.
Since `String`/`str` are UTF-8 byte sequences, they cannot be indexed, as they could be indexed on a non character boundary (does allow slicing however, slices always have this problem potentially).
To get an iterator of the UTF-8 bytes of a String, use bytes().
In rust `String` represents string data allocated on the heap, while `str` represents string data somewhere in memory.
since rust's `String` is stored on the heap, it can be grown and shrunk.
Since we don't know where the string data of `str` will be and what size it can or cannot have, `str` itself cannot be owned, but instead can only be referred to as a reference.
A 'reference' ＆str is actually a slice, not just a mere reference. I presume that's because we need the feature of slices indicating the length, sice we need some way to know where the str stops (since `str`s can have any length, in contrast to other things like an array which we don't need to slice to reference it since we know where it ends at compile time)
Rusts treats references to strings ＆String and ＆str as the same in most cases, since there is not much difference between a reference to a string stored on the heap whose length we know, and a slice to a string stored somewhere whose length we know by virtue of it being a slice.
string.as_str returns a string slice ＆str of a string.
String slices ＆str and ＆String are type-compatible with ＆'static str, but of course work differently: they can't last longer than the original value.

String.from() gets a String from an ＆str.
String.new() creates a new empty string.
the + operator for strings requres a `String` on the left and a `＆str` on the right

## Numeric types

Languages generally have at least a type for Integers and a type for numbers with fractional parts, most commonly floats. JS combines these into a single type Number.
C#, Java, Perl, Python, Ruby, Rust, TOML allow inserting underscores in numeric literals for readability.
In some languages, multiples subsequent underscores within a numeric literals, or underscores at the beginning or end of literals are not allowed]
Some languages have specific keywords for Infinity (JS, Ruby) or NaN (JS). More commonly, values such as these exist as constants on the Number/relevant numberic type class/object/whatever.
In some languages (JS, Ruby), you can recieve values such as Infinity or NaN via certain operations, e.g. dividing by zero. Other languages will throw errors in this case.
In JS, you can generate NaN by trying to do math with a non-number and non-boolean (unless using +, which will concatenate), multiplying Infinity * 0 or * Infinity, using unary plus on a non-number and non-boolean.
In JS, you can generate Infinity by dividing by zero
checking for NaN
Number.isNaN(num)|JS (true only for NaN)
checking for finity
Number.isFinite(num)|JS (false for all non-numbers and NaN/Infinity)
In CSS, the general numeric type is ‹number›, which supports decimal numbers also. ‹integer› is a speialization for integers.
In CSS, percentages are a special type, ‹percentage›. 
In CSS, ‹percentage› consists of a ‹number› followed by a %

### Overflow

If a numeric type has arbitrary precision, it can store (nearly) infinitely large numbers (it will in practice be limited by the memory the application can get from the OS)
overflow/underflow occurs when a numeric value is to large/small for its container.
Numeric types either have arbitrary precsion, are subject to overflow/underflow, or need to throw an error if a calculation exeeds the size limit of a numeric type.
Rust throws an error in overflow/underflow scenarios when debugging, and wrap otherwise.

### size (not arbitrary precision)

In rust:
Numeric types: ‹type›‹size›
signed integer|i|i16, i128, isize,...
unsigned integer|u|u32, u64, usize,...
floating-point|f|f32, f64
size as part of the type annotation (usize, isize) indicates the system word size 

⟮ES2020⟯ introduces the ⟮BigInt⟯ datatype for numbers ⟮larger than the previous maximum size⟯
BigInt literal is indicated by ends in n

### Integers

Integer literals generally not overtly marked

### float and double

In Java and C#, to indicate a float literal you must add f as a suffix. any number containing a decimal point not explicitly indicated as a float will be a double
Most other languages don't distinguish between floats and doubles on a keyword level, merely by size (rust) or automatically

#### single and double precision

single-precision floating point numbers are floating point numbers stored in 32 bit of storage.
double-precision floating point numbers are floating point numbers stored in 64 bit of storage.
A single-precision floating point number typically has 1 bit sign bit, 8 bits for the exponent, and 23 (stored) bits for the significand
A double-precision floating point number typically has 1 bit sign bit, 11 bits for the exponent, and 52 (stored) bits for the significand
In JS, all Numbers are double-precision floating points.

### methods

Object/Struct/whatever for standard math operations
Math|JS
math|Python

get a random number
‹mathobj›.random()|JS

floor/ceiling function
‹mathobj›.floor()/.ceil()|Python|JS
‹thingItself›.floor()/.ceil()|Ruby

Is a thing an integer?
Number.isInteger(foo)|JS

Truncate decimal places (not rounding)
‹mathobj›.trunc(num)|JS

Round to fixed amount of decimal places
somenumber.toFixed(num)|JS

Round a number
‹mathobj›.round()|JS|Python

Get absolute value of something
‹mathobj›.abs()|JS
abs()|Python (y, it's not on the math obj)

Square root
‹mathobj›.sqrt()|JS|Python

Is the thing an Integer?
Number.isInteger(foo)|JS

## enums

Enum is short for enumeration or enumerated datatype.
An enum is a datatype that can take on one of a finite set of values.
In stats terms, an enum is a categorical variable.
We may want to consider the boolean type an enum of {true, false}
Of the languages I know, C#, Java and TS allow creation of enums via the enum keyword.
Rust also uses the enum keyword, but for things more like tagged unions.
Python allows using enums via an external module
C#, Java enum syntax: enum ‹name› {
  ‹variant›,
  ‹variant2›,
  ...
}
In C# the syntax ‹variant› = ‹value› exists to apply values to enum variants
We may want to consider enums a special case of tagged unions, where enums can only stand for simple values.


## Collections

Collections are an abstract data type that hold a number of data items.
Python calls its data structures that represent collection ADTs, well, collections.
Associative collections map keys to values. 
Js sets and maps use .size instead of .length
Java has the Collections Framework for collections 
Collections may be implemented in the language as primitives, but many are either transparently records or some syntactic sugar made up of literals over records; in some language everything is an object anyway and thus this distinction doesn't apply.

Rust only calls its non-primitive collections collections, which are stored in std::collections.
Rust collections (as in non-primitve collections) are stored on the heap and are variable size, primitive data structures are stored on the stack and are fixed-size.

### access

#### random and sequential

##### definitions

Random access might be clearer if it was called direct access.
Random access allows access to arbitrary elements at will.
Sequential access only allows access in a certain sort of order.

##### examples

flex-container:✫sm_rand_seq_acc.svg✫
book|random access (to pages)
scroll|sequential access

#### notation



### Collection methods

#### Clear a mutable collection

foo.clear()|not JS|Python|Ruby

#### Flatten a nested thing ([[1]].flat() =› [1])

foo.flat(depth)|JS
foo.flatten(dept)|Ruby
nothing in py

### Non-linear collections

Python: dictionary, set (and frozenset)

#### Sets

ADT similar to sets in math = unique members, don't have order.
Python data structure: set (mutable), indicated by {}, frozenset (immutable).
JS: class Set, create via new Set(), add(), has()

##### Set operations

Many languages/libraries have generalized set operations to something you can do to most/all collection types.
Python has set methods, but only allows them on sets.
JS has a Set class, which does not support set method

xor/union/intersection/difference(things...)|lodash/underscore(JS)

#### Associative collections

##### Associative array

###### definitions

An associative array is an abstract datatype composed of a collection of (key, value) pairs so that each possible key appears only once (as a key) = keys are unique.
A mapping is the term for a single key-value set (ordered pair).

###### keys

Different programming language's implementations limit keys to only strings, strings or integers, all values, or something inbetween.
In programming languages, string assoc arr keys are generally quoted. In TOML they may be unquoted for simple alphabetic keys.

####### computed property names

Computed property names allows you to put any expression on the left-hand side of a property within an object literal, if you wrap that thing in []
AFAIK only JS has computed property names

###### implementation

####### primitve vs records

Associative arrays are implemented as primitives in some languages, as records in others, or sometimes as both.
Languages with no associative array primitives: C#, Java, Rust
If languages implement assoc arr via records, you then interact with them as you would with records.
If languages implement assoc arr as primitives, these then often have their own syntax for interaction.

####### literals

######## delimiters

no literals at all|C#|TOML
{}|JS (objects)|Lua|Perl (1 of 2)|Python|Ruby|YAML
()|Perl (1 of 2)|SCSS/Sass (same as arrays)
newlines ＆ indentation|YAML

######## mapping separators

In associative array literals, the separator between 2 mappings is generally ,

######## key-value separators

=|lua|TOML
:|python|Ruby (symbols)|YAML
=›|Perl (1 of 2)|Ruby (non-symbols)
, (yes, really)|Perl (1 of 2)

######## assoc array names (if primitve)

table|lua|TOML
hash|perl
dictionary|python
hash table|Ruby
map|SCSS/Sass

In most languages with primitive associative arrays, accessing and assigning are handled by the usual indexing syntax also used for their primitive array type etc.

####### Objects

Dictionary‹K, V›|C#
HashMap‹K, V›|Rust
BTreeMap‹K, V›|Rust
Map‹K, V› interface, e.g. HashMap‹K, V›|Java

####### JS

JS implements associative arrays via the `Map` and `WeakMap` classes. 
In JS objects (esp. object literals) also perform many of the operations we would expect of associative arrays. 
Specifically, Maps maintain insertion order, and support any key type, while Object coerces any key to a string (except Symbols). 
Objects are primitives, Maps need to be created with the new Map() constructor. 

###### properties

####### Insertion order

There are both languages that do and do not guarantee insertion order to be maintained for their associative arrays.
In Rust, you need to use the `indexmap` crate to get an associative array that keeps insertion order.

###### operations

####### assigning

adding a key, value pair
.Add(‹key›, ‹value›)|C#
.set(‹key›, ‹value›)|JS (map only)
.put(‹key›, ‹value›)|Java
.insert(‹key›, ‹value›)|Rust

####### retrieval

get(‹key›)|Java|JS(map only)|Rust
[] indexing notation despite not being a primitive|C#

####### deletion

set it to null type|lua

####### checking for existence

######## Has key? 

key?|Ruby

######## Has value?

value?|Ruby

####### iterators/arrays of

######## key, value tuple/array/whatever

pairs()|lua
items()|Python
entries()|JS (map only)

########  keys

keys()|JS(only Map)|perl|Ruby|Rust|Python (returns a dict_keys object)
Object.keys(someobj)|JS

######## values

values()|JS(only Map)|perl|Ruby|Rust|Python (returns a dict_values object)
Object.values(someObj)|JS

######## JS

Amusingly, JS doesn't have the keys(), values(), entries()... functions for its assoc array type (objects), but does have them for arrays

####### merging

map-merge(foo, bar)|SCSS/Sass

###### derived structures

####### entries

An entry is a view into one item in a assoc array.
In rust, an `Entry` is an Enum with possible variants `Occupied`, `Bacant`
in rust `Entry.or_insert` insets the key into the map if map is empty.
Rust: Has the entry() function go get a Entry

###### assoc-array files

typically, most languages have modules/libraries called json/yaml for json/yaml processing.
JS and thus node calles its json/yaml libraries JSON/YAML.
‹j-or-y-library-object-name›.load()|parse as JSON/YAML into assoc array structure|Python
‹j-or-y-library-object-name›.parse()|parse as JSON/YAML into assoc array structure|JS (incl node)
‹j-or-y-library-object-name›.dump(‹assoc-arr›, ‹file›)|write assoc array as JSON/YAML|Python

to make sure that Python's JSON/YAML libraries insert newlines and indentation, pass the load method the named parameter indent with the relevant indent.

####### Rust serde

serde is a rust crate for serializing/deserializing data structures from/to common formats.
serde uses additional crates to add support for formats, e.g. serde_json for json and serde_yaml for yaml.
trying to use serde-related features with indexmap will fail if you haven't specified the feature "serde"
you can make `ureq` support conversion to json via serde directly via the `json` feature.
serde represents anything with the `Value` enum
the `Value` enum has variants for each type supported by the file format. 
serde_yaml represents mappings as `Value::Mapping‹Value, Value›`
serde_json represents Objects as `Value::Map‹String, Value›`

`Value.as_‹type›` returns Option‹‹type››
`Value.is_‹type›` returns bool representing whether is ‹type›

using serde to parse, we may parse arbitrary data into a serde representation using from_str and then index into it as you would in JS with square bracket notation (but you may recieve `Value::Null`), or we may parse data into a predefined rust representation
to make serde support the derive macro, set the "derive" feature

###### peculiarities

####### lua

tables are actually the only data structure in lua

### Linear collections/ADTs

Linear collections/ADTs are a sequence of items.
Python calls its data structres that are linear collections sequences.
Linear collections are the equivalents of sequences in math.
Python sequences: list, tuple, str

It seems to me that all non-array linear collections only allow sequential access.

#### Linear collection methods

##### reverse the thing

reverse()|JS(in-place)|Perl|Python (in-place!)|Ruby

##### Append a linear collection to a different linear collection

col1 + col2|Python (also works for strings)
col1 ‹‹ col2|Ruby (also works for strings)
col1.extend(col2)|Python

##### Repeat the contents of a linear collection n times

col1 * n|Python

##### append one element to end of dynamic linear collection

push()|JS|Rust
append()|Python

##### remove an element from a lin coll by name

somelincoll.remove(elem)|Python

##### insert an element at a specific position

somelincoll.insert(elem, index)|JS

##### Fill the thing with the specified element

somelincol.fill(element[, start[, range]])|JS|Ruby
In Ruby, fill also may take a block to calculate the element to fill it.
[element; length]|Rust (Arrays)
vec![element; length]|Rust (Vectors)

JS
Array() and Array.of() will create an array of a list of arguments.
The difference between Array.of() and Array() is in the handling of integer arguments: Array.of(7) creates an array with a single element, 7, whereas Array(7) creates an empty array with a length property of 7 (Note: this implies an array of 7 empty slots, not slots with actual undefined values).

The push() and pop() methods were borrowed from the Stack ADT to describe inserting/taking from the end of the linear collection in some languages, e.g. JS. 
Most commonly, pop/shift returns the element removed, while push/unshift returns the new length.
Shift and unshift are methods in JS, Ruby, Perl, Java that do the same as pop/push but for the beginning of the array.
Python extends the pop method to all collections, but it generally works weirdly, compared to other programming languages:
someset.pop()|a random element
someassocarray.pop(somekey)|the relevant value
somearr.pop(index)

somearray.splice(⟮start⟯, numberOfElementsToDelete, element1toInsert, ...); (odd, js only, returns array of removed elements which may be empty)

##### Rust

In Rust, vectors can be indexed via the [] syntax, which will panic if the element doesn't exist, or via get(), which returns an Option‹＆T›

#### Strings as linear collections

TODO string as iterable
Strings are often implemented as linear collections (esp. arrays) of chars, or at least their semantics are similar enough that they work the same way.
Since strings are semantically and often also by implementation similar to linear collections, their methods often are the same.

##### methods

get (first) index of element/substring in string or linear collection
foo.index(bar, optionalStartIndex)|Python
foo.indexOf(bar, optionalStartIndex)|JS (returns -1 if ti could not be found)

get (last) index of element/substring in string or linear collection
foo.lastIndexOf(bar, optionalStartIndex)|JS

Concatenate multiple strings/ arrays at the end of an existing string/array
stringOrArray.concat(stringsOrArrays)|JS|Ruby

#### Array

An array (type) is a abstract datatype of an ordered linear collection of elemennts, selected by indices.


##### depth

no indices (one value only)|zero-dimensional array (uncommon)|scalar
one index|(one-dimensional) array|vector
two indices|two-dimensional array|matrix
n indices|multidimensional array|tensor

##### types, names, literals

###### primitiveness

Arrays are generally primitives in different programming languages, though they differ on syntax and what they call them.
In C# and Java, the builtin static arrays are objects, and thus must be created using the new operator. 

###### possibilities

Arrays may be dynamic = have variable size, or static = have fixed size.
Some languages have mutable static arrays, some languages have immutable static arrays, and some languages have both.
Some languages allow only one type in an array, and some languages allow multiple types in an array.
In static arrays, the compiler therefore knows the type of each index
Dynamic arrays are sometimes called arraylists.

###### names

####### dynamic arrays (one type only*)

Vec‹T›|rust
ArrayList‹T›|Java
List(yes, really)‹T›|C#

Rust Vectors, Java ArrayLists and C# Lists are Objects/Structs and defined over a generic
Different types in the dynamic arrays defined over a generic may be possible via parametric polymorphism.

####### dynamic arrays (of whatever types)

list|GraphQL|python
array|perl|JS|ruby
table|lua (though this is more properly the assoc array type, it just happens that an assoc array w/o keys will have numeric keys set up for it by lua, making it also the array type)

####### static arrays (one type only)

array|C#|Java|Rust

####### static arrays (of different types)

tuple|rust|TS

####### immutable static array (of whatever types)

sequence|yaml
array|liquid|TOML
tuple|Python
list|SASS/SCSS 

###### Array literals

####### delimiter

dynamic (of whatever types)
()|Perl (same as assoc. arr)|Shell
[]|JS|GraphQL|Python|Ruby

static, one type only
{}|C#|Java

static arrays (of diffent types), the compiler therefore knows the type of each index
()|rust
[]|TS

dynamic (of a single type)
vec![]|Rust (creation only)

immutable static array (of whatever types)

()|SASS/Scss|Python (Though in python in reality it is the comma that creates a tuple. the parentheses are just often needed for grouping)
[]|TOML|YAML (if inline)

####### separator

In array literals, the invidual elements are generally separated by ',', except sh, which separates them by space

####### oddities

YAML also has indentation delimited, newline separated, individual items marked by `- ` version

####### nested

Most languages use the same syntax for one-dimensional, two-dimensional, or multidimensionall arrays, merely nesting the literals.

####### type annotation

In principle, type annotation for array types usually uses the same delimiter as the literal for that array type.

######## specific variants

static immutable arrays|‹delimiter›‹type›{, ‹type›}‹delimiter›
static mutable single-type arrays|‹delimiter›‹type›, ‹length›‹delimiter›
dynamic arryas|‹type›‹delimiter›‹delimiter›|TS
dynamic arrays|‹delimiter›‹type›‹delimiter›|GraphQL

######## language peculiarities

In C# the type for multidimensional arrays (e.g. for a three-dimensional array) is type‹delimiter›,,‹delimiter› (and for the constructor type‹delimiter›length,length,length‹delimiter›). These are different from merely arrays of arrays, as these have a uniform size (while arrays of arrays do not) 

in TS, ‹type›[] is syntactic sugar for Array\‹‹type›\›
in TS, readonly ‹type›[] is syntactic sugar for ReadonlyArray\‹‹type›\›

##### operations

In sh, referring to the whole array requires a special syntax my_array[@] which can only be used within ${}

###### fixed length

When creating static arrays, the size must be given. In C# and Java, this is done in the [] of the array type in the constructor, e.g. new type[10];
In JS, one can create an array with a specfic size (and thus ergo empty slots) by using Array(n) or new Array(n)

#### Lists

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are finite.
Lists are always dynamically sized
C#: List, defined over one generic. must be created via constructor. Add to end of list .Add()

##### linked list

flex-container:✫sm_408px-Singly-linked-list.svg.png✫
A linked list is a data structure (implementing the ADT list) in which each node/vertex holds a reference to the next element.
To access a linked list, we merely need a reference to the first element.
A linked list in which the only node/vertex is a reference to the next element is a singly-linked list

flex-container:✫sm_doubly_linked_list.svg✫
A linked list with a backward reference too is a doubly-linked list.
access|O(n)

###### cons

cons is short for construct function, and comes from lisp. 
To ⟮cons something onto something⟯ is to take a ⟮container⟯, add ⟮an element in front of it⟯, and ⟮put this in another container⟯.
A singly linked list is functionally eqivalent to / can be modelled by a set of nested ordered pairs (foo, (bar, (quuz, nil))).
A cons list is a singly linked list constructed via nested ordered pairs.

###### blockchain

flex-container:✫blockchain.svg✫


A ⟮blockchain⟯ is a growing ⟮(linked) list⟯ of records called ⟮blocks⟯.
In a blockchain, each block contains ⟮a hash⟯ of ⟮the previous block⟯, a ⟮timestamp⟯, a ⟮nonce⟯, and ⟮transaction data⟯ represented as ⟮a merkle tree⟯.
Since ⟮blocks contain hashes of previous blocks⟯, ⟮changing a block⟯ would ⟮also require changing subsequent blocks.⟯

##### vs arrays

slower access O(n) vs O(1)
more space consumption if no empty spaces in array due to pointers.
Re: modern processors, linked lists have the problem that they are stored non-contiguously and thus can't take advantage of processor cache as well (priniple of spatial locality)

#### Streams

Streams are an abstract data type (specifically a linear collection), in which each element has a position (a first element, a second element), and that are infinite (or at least potentially so).

#### Stack

The anaogy of a stack historically comes from spring-loaded plate dispensers (e.g. in a mensa)
In a stack, the element you remove will be ⟮the one you added most recently⟯
LIFO = last in first out
A stack is a linear collection ADT with LIFO order, and the operations:
push: add to the top of the stack
pop: remove from top of the stack
peek: loop at top of stack

flex-container:✫sm_Data_stack.svg✫

#### Queue

FIFO = first in first out
A stack is a linear collection ADT with FIFO order, and the operations:
enqueue: add to the end of the queue
dequeue: remove from the front of the queue
peek: look a the next element that would be dequeued

flex-container:✫sm_450px-Data_Queue.svg.png✫

## intersection of iterators, strings, linear collections

### slicing and ranges

Slice and range syntax is often similar.
For slicing, the slice syntax must generally be surrounded by the same brackets used for array indexing.
For ranges, different programming languages need them to be surrounded by () at different times.
start..end_incl|Ruby|Perl|Liquid (range only)
start..end_excl|Rust
start...end_excl|Ruby
start..=end_incl|Rust

#### Slicing

Slicing is extracting a subset of elements from a data structure.
Slicing is most commonly performed on linear collections or strings.
In most cases, omitting the start defaults to 0, and omitting the end defaults to the maximum value (last element/slength)
In general, using a negative index for step will reverse the thing.
In python you can assign to slices, delete them, etc.

[start:end_excl:step]|Python
.slice(start, end_excl)|JS
.substring(start, end_excl)|JS (only strings, will not count from back, but will swap start and end if start is larger)
[start,length]Ruby

#### ranges

Ranges may be a syntax for generating iterators/arrays, or may be their own type. They may also be both, pythons range is an interable type that as all iterables generates an iterator if needed.
Step is pretty much always optional.

range(start, stop, step)|python|lodash/underscore (js)
seq start step stop|sh

Bash calls its range syntax a »sequence expression«.
Bash also supports characters as start and stop.

### misc

does the thing contain the thing?
include?|Ruby (Array, String, Enumerable)
includes()|JS (Array, String)

Is there a truthy value in an iterable
any(iterable)|Python

Are all the values in an iterable truthy 
all(iterable)|Python

Sum up all the elements in an iterable
sum(iterable)|Python
enumerableWhichIsJustASynonymForIterable.sum()|Ruby
Iterator.sum()|Rust


count occurrences of element
foo.count(bar)|Python|Ruby
no easy way|JS

## Iterators

An iterator is an object (or similar) whose purpose is to iterate over some data. 
An iterator has a next() method that returns the next element.
Most other functionality that an iterator offers can be derived from the next() method
An iterable is generally something that can create an iterator of itself.
Something being iterable is generally implemented as an interface.
Something being an iterator may be implemented as a type or interface

### Iterator implementation

`Iterator` trait/interface|Rust

In rust, to implement `Iterator` you only have to implement `next()`, and Rust will automatically implement a bunch of other methods for you.

### iterables


In ruby, iterables are called enumerables.
In most languages that have iterables, most collections are iterable, as are strings and ranges. 
Java Strings are not iterable, JS objects aren't either.

#### iterable ↔ iterator

Iterables generally require explicit or implicit conversion to become/spawn iterators.
iterables are always automatically converted to iterators|
iterables are only automatically converted to iterators in loop contexts, manual conversion otherwise|rust


In rust, you call `collect` on the iterator to turn it back into a data structure.

##### rust

In rust, iterators themselves must always be mutable, since calling next() changes the iterator.

‹iterable›.iter()|iterator of immutable references
‹iterable›.iter_mut()|iterator of mutable references
‹iterable›.into_iter()|iterator of owned values


### next()

in JS, the next() method returns an assoc array {
  done: bool,
  value: ...
}
In JS, Array.from() transforms a given iterable into an array. (list() does the same in Python and foo.to_a does it in ruby)

### Generators

A generator is a form of iterator. Generators are created via a generator function (thus you control what the next() method returns), but otherwise behave like any other iterator.
In JS, generators are indicated by a * after the function keyword.
In JS at least, generators continue from where they left off after the last yield.
In JS, returning or encountering an error ends the generator.
In JS, the next() function of a generator's iterator can be passed an argument that will be assined to the yield expression.
Returning the current iterator element 
yield|JS

yield another generator (JS) yield*

### iterator methods

someIter.⟮zip⟯() takes ⟮two iterators⟯ and returns ⟮a new iterator⟯ which will for each call to ⟮next()⟯ return a ⟮tuple⟯ with the values ⟮the other two would have returned⟯ with ⟮next()⟯
In rust, methods (most of them higher-order functions) called on iterators are known  as adapters or consumers, depending on what they do.
Iterator adapters take an iterator and return another iterator
Iterator consumers take an iterator and return something else (thus consuming the iterator)

## Strings

A string type is generally a type for an arbitrary sequence of characters.
Depending on the language, strings may be mutable or immutable.
In general, more languages lean to the immutable string direction.
Languages with mutable strings I know include Perl, Ruby.
While it may be tempting to change strings by assigning to indices, in languages with immutable strings, it does not work. However, in JS in non-strict mode it will not trow an error
If a language has immutable strings, string operations actually create a new string.
In many languages, especially those that do not have a char type, string literals can be indicated either with single or double quotes.
In languages that have a char type, the char type is generally indicated with single quotes, and the string type with double quotes. Examples: C#, Java, Rust
Some langauges that don't have a char type differentiate between string literals with single and double quotes (e.g. treating single quote string literals as raw strings, e.g. sh, Perl, Ruby), some languages (CSS, HTML, lua, liquid, python, JS) do not.
In languages that have single-quoted string literals, interpolation is generally also not allowd in them.
JS has a specific, especially featureful type of sting called a template literal, which are delimited by backticks (`foo`)
sh is a little special in that it accepts strings with no surrounding quotes in some cases.
YAML accepts unquoted strings if they don't interfere with other syntax, of which the most common case is them containing ` :`
In some languages, most notably C, strings are ended by the NULL (0x00) character, these are known as null-terminated strings.

A raw string is a string literal where character escapes have been disabled and so everything is a literal.
r or R"foo"|Python|Rust
String.raw`foo`|JS
'foo'|sh|Perl|Ruby|TOML

Multiline string delimiters
`containsnewlines`|JS
\[\[containsnewlines\]\]|Lua
"containsnewlines"|Rust (all strings are multiline)
"""containsnewlines"""|Python|TOML
|\nproper indentation|YAML

Strings that stretch over multiple lines in source code but are actually folded into a single line in the resulting thing (for source code readability)
›\nproper indentation|YAML

The type for css strings is ‹string›

### chars

The datatype storing a single character is generally called char.
In rust, a char contains a single UTF-32 encoded unicode codepoint.

### String interpolation/String formatting

String interpolation is evaluating a string with placeholders and replacing them with their values
String interpolation is a form of template processing (cf other cards)
In JS, string interpolation can only be performed within template literals.

\${expr}|JS|only in template literals
\#{expr}|Ruby|SCSS/SASS
‹sigil›{expr}|Perl
‹sigil›variable|Perl

sh's various $-introduced expressions are similar to string interpolation.
Python has three ways to perform string interpolation:
old-style stirng formatting: is just c-style string formatting. The whole string is followed by a % character, which itself is followed by a single value or a tuple of values to interpolate
new-style string formatting:
{} or {0}, {1} ... interpolates within the string, if calling format() on the string. Interpolated expressions are args to format method, format specifiers go within {}, if passing to format by name, refer to these things like so {name}. 
If combining w/ format specifiers \{‹name›[!‹conversion›][:‹format_specifier›]\}
"Error code: {errno:x}".format(errno = ...
f-strings: allow arbitrary expression within {}. String must be prefixed by f
f"Hello, {name}"

rust defines its format syntax in std::fmt, which largely tracks python's str.format() specifier
rust allows its std::fmt formatting syntax in its format! and println!/eprintln! macros, with the difference being that the former returns a string and the latter prints.
specifying a ? as the final element in a rust formatting syntax specifier makes it use the trait `Debug`, otherwise it will use the trait `Display`

#### C style string formatting

(C) format strings aka printf (print formatted) format strings are names for a specific type of string formatting syntax using % and originating from C.
C format strings specify the format of a given argument with a format specifier
format specifier: % followed by a char or a few chars to indicate the format.
Which strings to interpolate where is determined positionally (the first string is interpolated )
Positional arguments to interpolate are specified after the string separated by a %
c-format-string-format-specifier ::= %[‹parameter›]{‹flag›}[‹width›][.‹precision›][‹length›]‹type›
parameter ::= ‹n›$
flag ::= -|+| |0|'|#
width ::= ‹positive-integer› # specifies minimum width.
precision ::= ‹positive-integer› # specifies maximum width

flag meaning
-|left-align output
+|prepend a + sign for positive numbers
 |prepend a space for positive numbers
0|use zeroes when padding via width
'|The integer or exponent of a decimal has the thousands grouping separator applied. 
#|

for the types in c-style format strings, if there is an uppercase variant this normally uppercases the cahracters

common types
x or X|hex (unsigned numbers only)
o|octal (unsigned numbers only)
d or i|signed int
u|unsigned int
f or F|decimal number
e or E|use exponent based notation e±dd
g or G|decide between e/E and f/F depending on maginitude
s|string
%|percentage (python .format() only)
b|binary (python .format() only)

#### python-style string formatting

python's str.format() method takes a C format string inspired but somewhat different syntax.
[[‹fill›]‹align›][‹sign›][#][0][‹width›][‹group›][.‹precision›][‹type›]
where width, precision and type are the same as with C format strings
fill|what character to use to pad (takes a string)
align|what direction to align
sign|is a sign included for numeric values
#|causes an explicit base indicator to be shown for binary, octal, and hex
0|pads with 0
group|indicates a separator character for groups of numbers

align ::= \‹|\›|^|=

‹|align left
›|align right
^|center
=|place padding between number and sign

sign ::= +| |-

+|+ for positive numbers, - for negative numbers
-|nothing for positive numbers, - for negative numbers
 |space for positive numbers, - for negative numbers



### String multiplication

x n|Perl
* n|Python (can also be used for arrays)|Ruby (can also be used for arrays)
.repeat(n)|JS|Ruby

### String concatenation

string concatenation is joining strings together into a single string.

..|Lua
+|Java|C#|Python|Ruby|Rust|JS
.|Perl
.push_str()|Rust (for str + str)
.push()|Rust (for str + cahar)
Adjacent string literals are automatically concatenated|Python|Ruby

### Regex matching

JS has regex literals: /‹regex›/‹flags› (which creates a RegExp object)
and a constructor: new RegExp("regex","flags"), often used if you need to construct the regex dynamically at runtime
In JS, you can both use methods on strings which take regexes, or methods on RegExp objects which take strings
The RegExp Object has a property lastIndex which indicates the offset that the RegExp will search for a match at next time (if the regex is global or sticky). This stays the same even if you switch the string in the meantime!

Does the string match the regex?
RegExpObject.test(string): boolean

RegExpObject.exec(string): {
  0: wholeMatch, 
  1: captureGroup1, 
  2: captureGroup2...,
  index: indexAtWhichTheMatchBegan,
  input: origialString
}

somestr.match() and .matchAll return string matches for a Regex.
somestr.replace() and .replaceAll replace the regex they got as a first arg with whatever is specified as a second arg, be that a string (using $1 etc. optionally) or a replacerFunction
The replacerFunction recieves the following arguments:
match|The matched substring.
p1, p2, ...|The nth string found by a parenthesized capture group
offset|The offset of the matched substring within the whole string being examined
string|The whole string being examined.
groups|named capture groups

the All() versions of the regex methods of strings both require the regex to be global and throw an error if it isn't.

What somestr.match(regexp) returns depend on whether the regex is global (g) or not:
If global, match() returns all matches, but no capturing groups. If not global, match() returns the same thing as RegExpObject.exec. matchAll() returns an iterator with individual things that are  the same thing as RegExpObject.exec returns.


### common string methods

Capitalizations

convert to uppercase|.upper()|Python
convert to lowercase|.lower()|Python
convert to uppercase|.toUpperCase()|JS
convert to lowercase|.toLowerCase()|JS
convert to uppercase|text-transform: uppercase|CSS
convert to lowercase|text-transform: lowercase|CSS
switch upper and lower case chars|.swapcase()|Python
capitalize all first letters|.title()|Python
capitalize all the first letters|text-transform: capitalize|CSS
capitalize the first letter of the string|.capitalize()|Python
capitalize the first letter of the string| bar capitalize|Liquid
pad stringth to specified length by adding to the left/right|.padStart/padEnd(‹length›, ‹pad-string›)
pad stringth to specified length by adding to the left/right|.rjust/ljust(‹length›, ‹pad-string›)


does a string start with?/end with?|somestr.startsWith/endsWith(searchstr)|JS (accepts an optional second arg of the index to start searching)
does a string start with/end with?|somestr.startswith/endswith(searchstr)|Python
remove whitespace from beginning and end of string|trim()|JS, Ruby
remove whitespace from beginning and end of string|strip()|Python
remove whitespace from beginning of string|trimStart()/trimLeft()|JS
remove whitespace from end of string|trimStart()/trimLeft()|Ruby
split string on foo|.split(foo)|Python|JS(empty string for char array)|Rust
split string on whitespace|.split_whitespace()|Rust
split string on newlines|.lines()|Rust

to char array/iterator
chars()|Rust

parse sting to other type
‹string-object›.parse()|Rust (Returns a `Result`, often requires turbofish annotation.)

SCSS/Sass
⟮unquote(foo) or string.unquote(foo⟯)|⟮unquote a string (so that css gets the value as the correct type, eg. when using maps⟯)
⟮quote(foo) or string.quote(foo⟯)|⟮return string, but quoted⟯



#### String replacement

somestr.replace(foo, bar)|JS|Python

#### Join to string

separator.join(iterable)|Python
somearray.join(separator)|JS|Ruby

separator defaults to , for JS and to nothing for Ruby

### JS oddity: tag functions

Tag functions are functions prefixed to template literals (but not called)
Tag functions recieve a first argument an array of all constituent string parts of a template literal, and all interpolated values as following arguments.
Whatever the tag function returns will be what the string evaluates to.
Tag functions can return whatever.


# Polymorphism

something is monomorphic if it works for one type
something is polymorphic if it works for several different types
monomorphization is a compile-time process in which polymorphic code is transformed into n monomorphic variants

ad-hoc polymorphism is polymorphism where different implementations are selected based on the type of the argument(s)
→ callable unit overloading, operator overloading

## dispatch

dispatch is choosing which method should be invoked in response to a method call.
displatch is based on the type of the thing
dispatch is only relevant if there are multiple implementations of a thing.

### static dispatch

static dispatch is choosing an implementation of a polymorphic operation at compile time
callable unit overloading and operator overloading are forms of static dispatch, since the implementation is chosen based on the declared type of the parameters

#### Overloading

##### callable unit

Overloading of callable units is creating multiple callable units with different callable unit signatures.
Languages I know that support overloading are C#, Java, TS.
When overloading, each signature generally has its own implementation, exept in TS.
In TS, function '⟮overloading⟯' exists, but you specify ⟮all possible signatures⟯ ⟮first⟯, and then the ⟮implementation⟯ with a ⟮signature⟯ that is ⟮compatible with all the specified signature⟯ (e.g. using ⟮optional parameters⟯), and not compatible with ⟮non-specified signatures⟯
For TS ⟮overloaded⟯ functions, ⟮all but the last⟯ signature(s), which ⟮do(es)n't have any body⟯, is/are called ⟮overload signatures⟯
For TS ⟮overloaded⟯ functions, ⟮the last⟯ signature(s), which ⟮has the body and thus the implementation⟯, is/are called ⟮the implementation signature⟯
In TS, in general: prefer ⟮union types⟯ over ⟮overloads⟯
In TS, things that can be overloaded anything that is callable: functions, callable objects, methods (whether in object types, interfaces or classes), constructors/newables.

Operator overloading is where different operators have different implementations based on their operands.

### dynamic dispatch

dynamic dispatch is choosing an implementation of a polymorphic operation at runtime.
dynamic dispatch is accomplished by means of virtual methods/functions.
both single dispatch and multiple dispatch are forms of dynamic dispatch.

#### single ＆ multiple dispatch

single dispatch is where only the type of one parameter (the reciever of the message = the thing it was called on, mostly) is used to choose the implementation

multiple dispatch is where the type of multiple parameters (the reciever of the message = the thing it was called on as well as the method parameters) is used to choose the implementation
Overloading would be multiple dispatch if it was performed at runtime, but it isn't, so it isn't.

#### virtual method table

VMT = virtual method table
virtual method table is also called (virtual) function/call/dispatch table
virtual method/function/call table is sometimes abbreviated vftable or vtable.
A vtable contains all relevant virtual functions.

#### rust

In rust, `dyn ‹trait-bound›` is the type of a trait object.
A trait object is an opaque type of another type that implements a set of traits.
A trait object uses dynamic dispatch to select the implementation at runtime (in contrast to rusts' parametric polymorphism, which ofc uses static dispatch)
A trait object is a dynamically sized type, and thus we need a pointer to it such as ＆ or Box‹›.
For something to be object safe, the return type may not be `Self` and there may not be any generic type parameters.
A trait object must be object safe.
The reason a trait object may not have any gemeric type parameters is that these will already be monomorphosized away by compile-time.
The reason a method of a trait used in a trait object may not return `Self` is that we don't known `Self` at compile-time, thus we can't reason about its size and can't guarantee safety.
In rust, we can specify that we want dynamic dispatch where we chose an implementation of a trait at runtime by having a pointer (e.g. Box) to `dyn ‹trait-list›`

## parametric polymorphism

Parametric polymorphism is polymorphism that only uses one implementation, instead taking a generic (that is perhaps subject to some contraints) and performing one's operatons based on that.
A generic is a stand-in for a type that is not yet specified or unknown. 

### type parameters ＆ generics

A type parameter is a specifier of one or more types that a thing (callable unit, object, ...) is defined over.
Type parameters go in angle brackets.
Type parameters are generally written in UpperCamelCase
Within type parameters, multiple type specifiers are separated by `, `.
Generics are specified within type parameters.
Names of generics are typically single characters.
A generic of any type is typically indicated T

#### binding generics

Once the name of a generic is bound, any reference to that name refers to that generic.
Two generics of different names are independent, even if they may be filled by the same concrete type at runtime.
It may sometimes seem like a generic is being bound twice when it's actually being used the second time.
E.g. impl‹T› SomeStruct‹T› is saying that you're implementing SomeStruct such that SomeStruct's generic ‹T› (second mention) satisfies being any type ‹T› (first mention), which is of course not particularly informative, and would be equivalent to impl SomeStruct‹T›, if that were possible.
Binding ‹T› via the `impl` already allows one to do more interesting things.
e.g. `impl‹T: Copy› SomeStruct‹T, T›` for a `SomeStruct‹T, U›` is saying that you're implementing this for all SomeStructs whose type parameters are of the same type which implements copy.

### constrainment

Many languages have a way to specify contraints a generic should satisfy.
Rust specifies a set of traits as constraints for generics, these are called »trait bounds«.
Trait bounds are a set of traits that a generic must satisfy.
In rust, we may specify trait bounds by indicating it within a type parameter as \‹‹generic›: ‹trait-bound›\›, with a 'where clause', or by not using generics at all and instead writing the type as `impl ‹trait-list›`
trait-bound ::= ‹trait-name›{ + ‹trait-name›}
where-clause-syntax ::= where {‹generic›: ‹trait-list›‹newline›}
TS allows specifying constraints for generics via the `extends` keyword.
The TS `extends` keyword in type parameter contexts takes a type specifier to specify the constraints of the generic.

### implementation ＆ monomorphization

Javas ArrayList, C# List and Rusts vec are dynamic arrays defined over a generic, and are thus parametrically polymorphic.
C# List and rusts vec are monomorphosized for each type usedas a generic; Javas ArrayList instead only generates a single implementation for ArrayList‹Object› - therefore in Java all values in an ArrayList must be boxed.
In Rust, parametric polymorphism using generics is monomorphizised, so that Option‹T› with e.g. i32 and f64 produces the relaizations Option_i32 and Option_f64.

Interfaces/traits often enable parametric polymorphism.

## subtyping

# operators

overloading
In Ruby, all operators are actually just syntactic sugar for methods. that is, + 3 is .+(3), somearr[1] is somearr.[](1), !3 is 3.! etc.

## precedence

Operator precedence in programming mirrors the math concept of order of operations.
Operator precedence / order of operations is in which order to apply operations.
In most programming languages, math operations have the same operator precedence as they would in math itself.
Parentheses can modify the order of operations just as in math.
The power operator has unclear order of operations for historical reasons (in other programming languages), so JS throws an error if you use it without parentheses where it would make a difference
In liquid, the order of operatons is right to left, parentheses are forbidden.

## relational opearators

In computer science, a relational operator is an operator that tests or defines some kind of relation between two entities. These include numerical equality (e.g., 5 = 5) and inequalities (e.g., 4 ≥ 3).

### standard relational operators

~=|not equals|lua
!=|not equals|C#|Java|JS
==|equals|most programming languages
‹=|less than or equals|most programming languages
›=|greater than or equals|most programming languages
›|greater than|most programming languages
‹|less than|most programming languages
‹=›|returns 1 if left arg is larger, -1 if right arg is larger, and 0 if both are equal|Perl|Ruby

### types of equality

For anything that is a data structure, there can be two kinds of equality (using Kotlin terminology)
structural equality = equivalent content
referential equality = same reference
Most languages use structural equality for scalars.
comparison operators for non-scalars use...
referential equality|JS, Java, C#
structural equality|Ruby, Python, TS

#### `is`

Python uses the `is` operator for referential equality

### strings

greater/smaller with strings is generally relative to their position in unicode, which for latin characters tracks ASCII and thus "Z" ‹ "a"

### in different languages

#### JS

JS has versions of the equality operators with one extra =. The shorter ones coerce before comparisons. Specifically, any of the shorter ops containing ‹ or › coerce to string or numbers (including null, but not undefined). == coercion is more complicated, but will coerce null to undefined.

#### test

since relational operators are handled by test in sh, they are actually all arguments to test.

test uses the normal equality operators (e.g. !=, ›, etc.) for strings, but has a different set of operators for integer equality.
test uses the single (!) = sign for string comparison, though bash has a non-POSIX extension that allows for the more standard ==

##### integer equality

-ne|is not equal to
-lt|is less than
-le|less than or equal to
-gt|is greater than
-ge|greater than or equal to
-eq|is equal to
Perl uses sh-style comparison operator without the leading -

##### fs equality/existence

test has a number of options/operators for file existence and type

-e foo|foo exists and is a file
-d foo|foo exists and is a directory
-r foo|allowed to read foo

##### [[

[[ is an extension of `test`\[ which allows for a syntax superset (mostly)
specifically, [[ but not test/[ allow for ＆＆ and || for multiple conditions, () for grouping, pattern matching on the right hand side of =/== and the use of ~= for regex matching.
^in fact, POSIX test also doesn't support ‹ and › natively, but these are so commonly supplemented that it's kinda pointless to claim that test doesn't have them
^in fact, POSIX does support grouping with \(\) and and/or with -a, -o, but both of these features are super limited, error-prone, and are marked deprecated, so it makes more sense to say `test` doesn't have them.
Within [[]], in contrast with test/[], there will be no word splitting or globbing.
[[]] and most versions of test allow `!` to negate an entire expression

### comparison with self

Comparing a thing with itself is always true, except for: 
in JS, NaN

### interfaces

Things using the ruby mixin Comparable must define ‹=› operator, and then gain access to the other comparison operators, as well as between? and clamp

is x between foo and bar?
x.between?(foo, bar)|Ruby

### string relational operators used in a set of a language

e.g. CSS attribute selectors, youtube-dl 

^=|begins with value
$=|ends with value
*=|contains value at some point

~=|attr is a whitespace-separated list of words, one of which is exactly value.
bar=|attr  is exactly value or begins with value immediately followed by a hyphen. It is often used for language subcode matches.

## boolean operators

logical and|and|python|liquid|lua|Ruby (lower precedence)
logical and|＆＆|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical or|or|python|liquid|lua|Ruby (lower precedence)
logical or|barbar|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical not|not|python
logical not|!|C#|Java|JS

In ruby, between and/or and ＆＆/|| the former have lower precedence, and even have lower precedence than the equality operator.
Double not can generally be used to get the truthiness/falsiness of a thing, even outside of a boolean context.

### short-circuiting

Short circuiting is more properly short-circuit evaluation.
Short-circuit evaluation  an expression stopping evaluating⟮as soon as it's outcome is determined⟯
Short-circuit evaluation is most commonly found in the boolean operators of most programming languages
with short-circuiting of binary operators, the second argument is executed or evaluated only if the first argument does not suffice to determine the value of the expression.
specifically, expr1 LAND expr2 will not evaluate expr2 if expr1 is false/falsy
expr1 LOR expr2 will not evaluate expr2 if expr1 is true/truthy
Can be used to ensure a variable never gets assigned a falsy value by using logical/boolean or, since (only) if the first expression is falsy the second expression will be evaluated.
It is possible to create a kind of if statement using only short-circuiting operators: CONDITION ＆＆ IFTRUE || IFFALSE
(ba)sh

⟮??⟯ is like ⟮||⟯ but ⟮only returns its right-hand value on nullish values⟯

## bitwise

Bitwise operations operate on the underlying binary value (regardless of type in the programming language).
Most C-family languages support bitwise operations.

bitwise not|~
left shift|‹‹ ‹n›
right shift|›› ‹n›
bitwise XOR|^
bitwise OR|bar
bitwise AND|＆

when using the left shift operator, the newly created places will be filled by zero

## math

addition|+
multiplication|*
subtraction|-
division|/|Python: always returns a float, JS: it depends (but no distinction between floats and ints anyway)
floor division|//
remainder|%
power|**
increment|++
decrement|--

unary plus does different things in different languages: in some it does nothing (with numeric types) or throws an error (with non-numeric types). In JS it converts it to an number.


The increment and decrement operators do not exist in python.
The increment and decrement operators behave differently based on their position in relation to the number in some languages: 
++somevar or --somevar will crement first, and then evaluate, somevar++ or somevar-- will evaluate first, and then crement

## comma

In the C and thus in JS, Perl, the comma operator (represented by the token ,) is a binary operator that evaluates its first operand and discards the result, and then evaluates the second operand and returns this value (and type). (this is distinct from the comma e.g. in parameter lists)

A trailing comma is a comma at the end of a list of arguments, array elements, etc. 
In most programming languages (all of them I know), trailing commas are ignored (do not produce an error or empty elements).
In JS, trailing commas produced errors in some situations until recently (the newer ES versions such as 2017)

## element in collection/substring in string?

stringOrColl contains elem|liquid
elem in stringOrColl|Python|JS
stringOrColl.includes(elem, optionalSearchStartPos)

`in` in JS works amusingly if used on arrays: it will look for integer keys, and not for values, so that it will return false for "foo" in ["foo"] but true for 0 in ["foo"] (this is because arrays are objects, and thus the integer keys are actually object keys)

## remove element from collection

del|python
delete|JS

## Type of element

typeof foo|JS
type(foo)|Python
std::any::type_name(foo)|Rust

typeof in JS returns a string, and can return 'number', 'string', 'boolean', 'undefined', 'object' or 'function'

typeof...
{a: 1}|'object';
undefined|'undefined';
true|'boolean';
null|'object';
new Date()|'object';
function() {}|'function';
[1, 2, 4]|'object';
NaN|'number';
Infinity|'number';
37|'number';
3.14|'number';
/regex/|'object';
"something"|'string';
""|'string';
!!342|'boolean';
"1"|'string';

To test whether sth is an array in JS, you need to use Array.isArray()

## Length of strings, collections, etc.

foo.length|Java|JS|Ruby
foo.Length|C#
len(foo)|Python
#foo|lua|sh (must be surrounded by ${}, and followed by [@] if an array)

length() for strings in perl, merely generating a scalar context is enough for arrays

## Spread operator/Rest syntax

Both JS and Ruby have an operator that allows them to do similar things in relation to arguments and arrays.
Ruby calls this operator the splat operator, while js calls it a rest operator in the context of callable unit parameters (not arguments), and spread syntax otherwise

...|JS
*|Ruby|python

In the context of callable unit parameters, JS rest syntax and Ruby/Pythons's Splat both gather the remaining arguments into an array. the parameter so marked must be the last in the list.
funcName(1,2,3)
‹keyword› funcName(... OR *foo)
foo will now be [1,2,3]
When not in callable unit parameters, JS spread and Ruby/Pythons splat transform an array into its constituent members, or in the case of assoc arrays into its constituent mappings.
Ruby uses a double splat operator for associative array destructuring.
[... OR *[1,2,3], 4] == [1,2,3,4]
{**{:foo =› 1, :bar =› 2}, :quuz =› 3} == {:foo=›1, :bar=›2, :quuz=›3} and {...{foo: 1, bar:2}, quuz:3} === { foo: 1, bar: 2, quuz: 3 }
Rust's struct update syntax has some similarities to JS associative array destructuring
Rust's struct update syntax uses the oparator ..
for including all values of a struct instance into the current struct instance, use struct update sytnax.

## traits/interfaces/methods that implement math operators

Add|Rust

# Errors

Some languages distinguish between recoverable and unrecoverable errors.
recoverable errors e.g. not finding a file, unrecoverable errors e.g. stack overflow
Java and C# call recoverable errors exceptions and unrecoverable errors errors.
It can make sense to catch recoverable errors, but it is generally impossible to catch unrecoverable errors

## types

Errors can on one level be divided into ⟮syntax⟯, ⟮static semantic,⟯ and ⟮logic errors⟯.

A syntax error is an expression which violates the syntax of the language (will be detected during syntax analysis)
forgetting a parenthesis
A static semantic error is an expression which is syntactically correct but semantically meaningless. (will be detected during semantic analysis)
3/"kawaisa"
A logic error is an error where the program runs without problems, but produces an unintended result. (will only be detected on running the program, generally)

Based on when they occur, we separate compile-time and runtime errors

## Error handling

### Throwing errors

Generally take an expression as arg.

keywords
die|perl
throw|JS|Java|C#
error()|lua
@error|SCSS?Sass
raise|Ruby
panic!()|Rust

for rust, panicking is throwing an unrecoverable error

### Error handling control structures

most commonly: try ‹block› catch (‹error-specifier›) ‹block› finally ‹block›
In Ruby begin ‹block› rescue (‹error-specifier›) ‹block› ensure ‹block›
Rust is notable for not having any error handling of this kind.
In general, having a try and either a catch or a finally block is necessary for the construct to be syntacitcally correct.
In JS, the ‹error-specifier› for catch was necessary until ES2019, and has been optional since

### assert

Assertions are predicates that deliberatly crash the program if the predicate is false.
Assertions are generally used when something should be logically impossible to be false, and thus aren't handled by error handling.
Assertions are typically only used during development.
Rust implements assertions via macros.
rusts ⟮assert_eq!⟯ macro tests wheter ⟮two expressions are equal⟯ (using the trait ⟮PartialEq⟯), and ⟮panics if they are not⟯
rusts ⟮assert!⟯ macro tests whether ⟮something is true⟯, and ⟮panics if it is not⟯

# Callable units

Callable unit is a cover term for anything that can be called, be that functions, methods, procedures...
A call is a thing that executes a callable unit.
Callable units generally can take arguments if specified.

Keyword to start a callable unit
function|JS|Lua|sh|SCSS/Sass (@function ofc)
fn|Rust
def|python|Ruby
sub|perl
no keyword|C#|Java

Callable units can generally be split into callable unit signature and callable unit body. The callable unit signature usually specifies at least return type, name, and parameters, as well as the keyword if necessary. In sh, a callable unit signature contains nothing but the keyword and name/
The body of the callablue unit contains the code to execute.
In java, the callable unit signature also specifies parameter type, access modifier, and optionally staticness/finalness/abstractness.
In JS, function keyword defined callable units generate their own this, while arrow functions do not.

## Declaration

In most languages, functions can only be declared in statements, however languages that have functions as first-class citizens often also allow declaration via expressions.
function expressions are generally assigned to variables for later usage.
JS calls function declarations that are statements function declarations, and function declarations that are expressions function expressions.
since classes in JS are merely syntactic sugar for functions, there are also class declarations and class expressions

## signatures

Languages with manifest typing typically require the returned type to be declared in callable unit signatures.
void is commonly used for no return type in languages that require a return type to be specified.
return type is indicated:
-› ‹type› at the end of signature|rust
: ‹type› at the end of signature|TS
‹access-modifier› [static|abstract] ‹type› ‹callable-unit-name›|C#|Java

## returning

Across most languages, the keyword to return whatever value is the `return` keyword.
The datatype of the thing that is returned from a callable unit is known  ⟮The return type⟯
In non-manifestly typed languages, the default return value of a function is the null type
In general, using the return keyword without a value returns the languages null type.
Multiple values: separated by comma|lua
In Rust, using the return keyword is frowned upon, as blocks return their final expression anyway.

### returning and side effects

A side effect is a modification of the state of something that is outside of the local environment the operation is performed in.
A callable unit must return something or have side effects, else it does nothing.
A procedure (using a narrow definition) is a callable unit that does not return a value, instead causing side effects.
A function is a callable unit that returns a value.
A pure function is idempotent and has no side effects.


## Closures

A ⟮closure⟯ is the combination of ⟮a callable unit⟯ and ⟮the lexical environment⟯ (= ⟮any variables that were in scope⟯) within which that function was declared.
Closures are created when the functions are created.
All callable units automatically create closures in JS, lua.

### rust

In rust, only closures create closures.
In rust, there are three traits that indicate closures: Fn, FnMut and FnOnce.
Rust decides whether our closure is fn, Fn, FnMut or FnOnce by looking at what the closure does
the keyword `move` before a closure forces the closure to become `FnOnce` (take ownership).
Rust only closes over the environment actually used
In rust, closures don't necessarily need type annotations, however once a closure has been used with a certain type, rust fixes the types and other types become impermissible.
fn|does not form closure (but still can be used as first-class value)
Fn|forms closure of immutable references
FnMut|forms closure of mutable references
FnOnce|forms closure of owned values

## Anonymous, first-class, higher-order functions and callbacks

### distinguising

A callable unit not bound to an identifier is an anonymous function/callable unit.
First-class functions/callable units are callable units that are first-class citizens.
A higher order function is a function that takes a first-class function as an argument, or returns a function. All other functions are first-order functions.
callbacks are first-class functions passed to other callable units to be executed at some other point

### relationships

anonymous functios are almost always first-class functions, and are thus often passed as arguments, etc.
However, often non-anonymous functions can also be first-class functions
callback functions are typically also anonymous

### callbacks

The deep nesting of callbacks that result in unreadability is known as callback hell or the pyramid of doom
Error-first callback look like  (err, value) =› ...
Node generally takes error-first callbacks.

### first-class functions

#### which functions are first-class

In JS, lua, python, rust all functions are first-class. 
In Ruby, only functions created with a special syntax are first-class.
While in rust only closures form closures, all functions are in fact first class. Even things written with the closure syntax actually become `fn` type functions if they don't actually close over anything. (tested)

#### types of first-class functions in statically typed languages

In statically typed languages, first-class functions must have a type that describes them.
\(‹ts-param-list›\) =› ‹return-type›|TS
(fn|Fn|FnMut|FnOnce|fn)\([‹param-type›]{, ‹param-type›}\) -› ‹return-type›|Rust

‹ts-param-list› ::= [‹param-name›: ‹param-type›]{, ‹param-name›: ‹param-type›}

### anonymous functions

In JS, anonymous functions have no special syntax, you merely leave out the identifier.

### anonymous first-class functions

#### name

In ruby, anonymous first-class functions are called blocks.
In rust, anonymous first-class functions are called closures.
In JS, there is a special type of first-class anonymous function called an arrow function.

#### syntax

In ruby and rust, parameters to blocks/closures are surrounded by |...|
In ruby and rust, blocks/closures are surrounded by {}
{|params| code...}
In ruby, blocks may also be surrounded by do ... end
In rust, one-line closures may have their curly braces left out.

#### ruby

in ruby, to call a passed block, use the yield keyword. 
Anything passed to the yield keyword will be available as arguments to the block
In ruby, the ＆ operator converts a block to a proc object.
Calling #call on a proc object is similar to yielding a block
instead of a block with the syntax {|elem| elem.method} you can also pass ＆:method for the same effect

#### JS

Arrow functions function similarly to normal js functions, but have a shorter syntax: (‹params›) =› ‹block›.
Instead of a block, you may also specify a single expression, whose value will be returned. 
The parentheses are optional if there is a single param

### IIFE

An immediately invoked function expression (IIFE) uses function scoping to create a fake block scope.
IIFEs were used for the same reasons as block scope is used generally, and preventing hoisting.
IIFEs generally use anonymous functions.
in JS IIFEs need to force an expression to be able to immediately invoke it (since a declaration cannot be immediately invoked)
The most common way to force functions to be expressions is via surrounding them in (), but other ways are possible.
With the introduction ES6 let and const, IIFEs have become mostly irrelevant.



### common higher-order functions

There are many built-in higher order functions, generally as methods on data structure types.
since higher-order functions must take first-class functions as arguments, in languages that only have a special type of anonymous function as a first-class function, a higher-order function must take these.


language|higher-order functions are called on
JS|Arrays
Rust|Iterators


language|higher-order function recieves arguments
JS|value, index wholeArray


In JS, any higher-order function can take a thisArg, which is then the final argument. This argument will be what the passed fucntion recieves as this.

#### map

In many programming languages, map is the name of a higher-order function that applies a given function to each element of a collection, e.g. a list, returning a list of results in the same order. 
thing.map(func)|Java|JS|Ruby|Rust
map(func, iterator)|Perl (is list not iterator though)|Python
Select(func)|C#
no map function|sh|SCSS/Sass

Thing map is called on
arrays (or ggf. other iterables), not iterators|JS|Ruby|C#
iterators, not arrays|Rust
streams (whatever that is, but not the same as an iterator)|Java
globally|Perl|Python

##### flatmap

A flatmap function is a map function which may return an array and which flattens all elements of the array into the resulting thing.
effectively, flatmap is merely map with flat called on the array returned.
Most languages that have map function have a flatmap (flatMap) version of it, except for Python,. C# calls it SelectMany. Perls ordinary map is actually a flatmap, so really perl doesn't have a map.

#### sort

Sort is a higher-order function that takes a function which itself takes two arguments. Depending on the language, return values are handled differently.
JS function must return value smaller 0 if the first argument is to be first, larger 0 if the second argument is to be first, and 0 if it should not reorder.
The sort function passed must be deterministic.
In many languages, sort sorts with a predefined sorting algorithm if no sorting function is provided
In some languages sort does not take a sorting function, instead only using the predefined sorting algorithm, in those languages sort is not a higher-order function.

sorted(foo)|Python (takes an iterable)
foo.sort(callback)|JS (takes an optional sort function, only Arrays)
foo.sort()|Python (in-place!)
foo.sort(may be callback or nothing)|Ruby


#### filter

Filter in a narrow sense is a higher-order function that processes a data structure to produce a new data structure containing exactly those elements which the passed function returns true.
filter()|JS|Rust

#### reduce

The reduce function/method takes a function known as the reducer function
The reducer function recieves the return value of the last execution of the reducer function, and the current element of the collection. 
The reducer function return a single value.
In effect, the reducer function applies an operation to the current element, and the accumulated result of all other elements.
Many languages allow specifying a 'previous result' element for the first time the reducer function runs, as there will not be one.
js has the variant reduceRight that starts from the end
reduce()|JS|Ruby|Python

#### some/every/

some is a higher order-function that takes a function and returns true if the passed function returns true even once.
every is a higher order-function that takes a function and returns true if the passed function returns true for all elements.
JS

python has the functions any(iterable) and all(iterable), that merely return the result of calling bool() on each item, not taking any higher-order function

#### find

find is a higher-order function that takes a function and returns the first element for which the passed function returns true. findIndex instead returns the index.
find()|JS|Ruby
findIndex()|JS
find_index()|Ruby



## Arguments ＆ Parameters

### arguments vs parameters

How are parameters and arguments are often used synonymously, although they are more properly not synonyms
for a callable unit,  ⟮parameters⟯ are the values you specify the function will be passed, most commonly in its signature.
for a calllable unit, arguments are the values/variables you actually pass.
When passing things, using a car metaphor, you can think of the ⟮parameter⟯ as a ⟮parking space⟯ and the ⟮argument⟯ as an ⟮automobile⟯
function foo(a, b){...
foo(12, "whistles") 
a, b are parameters, 12, "whistles" are arguments

### syntax

#### both

most languages separate both the parameteres and arguments with commas.
sh separates arguments with space

#### parameters

most languages require the possible parameters defined in a callable unit definition to be wrapped in parantheses.
sh doesn't allow specifying parameters at all

#### arguments

most languages require the arguments to a function call to be wrapped in parentheses.
sh does not wrap arguments at all

Exceptions:
1 arg doesn't need parens|lua
always optional|ruby|perl
never|sh

### operations

#### refer to all passed arguments as an array

$@|(ba)sh
arguments|JS (not arrow functions)

#### amount of arguments passed

\$#|(ba)sh

### Positional and named

#### definition

A positional argument is one where the language knows which parameter to assign it to based on its position in the argument list.
A named argument is one where the language knows which parameter to assign it to because it directly refers to the name of the parameter.
While arguments may be positional or named, the parameters themselves nearly always have names. However, in sh parameters do not have names, instead you refer to them positionally via $0...$9. 

#### in languages

positional parameters exist in pretty much all languages, except GraphQL
named parameters exist in GraphQL, Python, SCSS/Sass @mixin, @function

#### positional

##### operations

###### move

Move remove the first positional argument and shift all arguments one to the left
shift|Perl|sh

#### named

Named arguments usually use normal assignment syntax

### Default parameters

#### definition

A default parameter is one which will take on a default value if no argument for it is specified in the call.

#### syntax

the general syntax is `paramname = defaultval` (within the parameter list)

#### in languages

GraphQL, Python, JS, SCSS/Sass @mixin, @function have default parameters TODO Check other languages

#### interaction with null

In general, default parameters will also take on the default value if the argument passed is the language's null type. 
In JS, the default parameter will take on the default value if undefined is passed as an argument, but not if null is passed.

### Optional

#### general situation

In most languages, callable units must be recieve the exact amount of arguments specified as parameters, unless things like the splat operator or default parameters are used.

#### JS ＆ TS

JS does not require the same number of arguments as parameters, it will assign unpassed parameters `undefined`, and put all arguments into the array-like `arguments`, allowing for retrieval of extra arguments.
TS moves JS in line with other programming languages, requiring arguments for parameters by default, and only accepting the not-passing of arguments if the parameter is optional.

#### marking as optional

in TS, optional parameters and optional fields are marked with a ? after the name, which changes their type to be whatever | undefined

### evaluation strategy

An evaluation strategy is a set of rules for evaluating expressions.
Evaluation is equivalent to reduction in math.
The concern most of interest within the evaluation strategy is the parameter-passing strategy.
The fundamental parameter passing strategy distinction is between strict/eager evaluation/applicative order and non-strict/lazy evaluation/normal order.
The parameter passing strategy may be the same for all constructs in a language, there may be keywords or other constructs to indicate the parameter passing strategy, or the strategy may differ by context/value.
Different implementations of parameter-passing strategies are often called call by x or pass by x.

Arguments are generally bound to parameters. 

A function is strict if it evaluates to ⊥ if one of its arguments evaluates to ⊥
= A function is strict if it fails to evaluate/terminate if one of its arguments also fails to evaluate/terminate.
Strict evaluation is evaluation that guarantees a function is stict.
Applicative order makes sure a function is strict by evaluating its arguments before the function is applied.
A function is non-strict if does not necessarily evaluate to ⊥ if one of its arguments evaluates to ⊥
A function is non-strict if it does not necessarily fail to evaluate/terminate if one of its arguments also fails to evaluate/terminate.
Non-strict evaluation is evaluation that does not guarantee that a function is strict
Normal order implements non-strictness by evaluating its arguments only once they are used within the function.
In math, strict reduction proceeds from the inside out, so that hitting a bottom type will always be encountered.
In math, non-strict reduction proceeds from the outside in, so that something containing a bottom type may have already been eliminated by outer reductions.
Applicative order is a rough synonym to eager evaluation.
Normal order is a rough synonym to lazy evaluation

Call-by name implemens normal order by substituting the arguments of a function into the function body.
Call-by-need is a memoized version of call-by-name.

##### extracurricular binding

JS's bind() method has the potential to change the idea that arguments passed to a function call are bound to parameters.
JS's bind() is called on a function.
JS's bind() method binds the first argument that it is passed to the this of the function, and any following arguments to the parameters of the function it was called on.

##### applicative order

call/pass-by-value/-reference/sharing are all forms of strict evaluation.

call/pass-by-value|pass the value of the expression/variable (= copying)|changes to passed variable will be lost if not returned
call/pass-by-reference|pass the reference of variable (i.e. the loc in memory)|changes to passed variable (incl reassignments) will be preserved even if not returned
call/pass-by-sharing/object/object-reference|pass by value, but only the object reference for objects|changes to passed variables contents will be preserved even if not returned if object, reassignments will not.

Most popular languages with objects that are said to be pass-by-value are actually pass-by-sharing.
In purely functional languages, cb/pb value ＆ reference are the same.
In purely functional languages, everything is immutable, so while the semantics are similar to pb value fron the outside, inside actually only references are passed (since it's cheaper), thus it is actually pb reference
Call by sharing is a term that is kinda rarely used.
In call-by-sharing

sharing|lua|JS|Java

moving seems like copying b/c you can't mess with it after, but in fact ofc only the reference changes hand.

##### non-strict binding

## Asynchronous callable units

Asynchrony, in computer programming, refers to the occurrence of events independent of the main program flow and ways to deal with such events.  

A process that is blocked is one that is waiting for some event, such as a resource becoming available or the completion of an I/O operation.
A blocked process cannot do anything in the meantime.
Asynchrony is a common way to deal with blocking.

A promise is a proxy for a value that will eventually become available.
In JS, a promise is an object
You react to promises by calling the then() method on them.
In JS, something you can call then() on is called a thenable.
in JS, most interfaces for promises work on any thenables.
A promise can have the states ⟮pending⟯, ⟮fulfilled⟯, or ⟮rejected⟯.
A promise is called ⟮settled⟯ if it is either ⟮fulfilled⟯, or ⟮rejected⟯.
Ergo a promise is either settled or pending.
We may return a rejected promise manually, additonally, if an error occurs in our async function, it will reject automatically.
Once a promise has settled, the attached thens will run as soon as possible / awaits will resolve.
If a promise is settled, and we then attach a then()/catch()/finally(), it will run immediately
While a promise is pending, thens will not yet run / awaits will not yet resolve.
A promise may have the fates resolved, unresolved.
Whether a promise is resolved depends on whether we can still resolve it: If we can still resolve a promise, it is unresolved, otherwise resolved.
A promise being resolved means that its outcome is already determined, even if we may not yet have the outcome.
Promises with the states fulfilled or rejected also have the fate resolved.
A promise with the state pending is resolved if it has been resolved to a itself pending Promise, else a promise that is pending is also unresovled.
//generally true, not jus js

In many languages, the async keyword marks the callable unit as asynchronous and allows it to call asynchronous functions.
await is a keyword/function available in many programming languages that calls an asynchronous function and then returns the value the function returns once it does.
In JS (and other languages w/ promises), await takes a promise (and is the rough equivalent of calling then() on it)
to handle errors resulting from await, use try/catch as normal.

In JS, then() takes two callbacks, one to run in case fullfilment and one to run in case rejection.
then(), catch() and finally() themselves return thenables, which allow them to be chained.
is the thing the last promise returned is what then(), catch(), and finally() get as an argument. What they get depends on if the callback running is one for rejection or one for fulfillment
In JS, catch() is a version of then() with only the callback to run in case of rejection, finally() is a version whose callback will run no matter if rejeciton or fulfillment
In JS, async functions always return promises.

you can create promises in a number of ways
create a promise that is already rejected: Promise.reject(reason)
create a promise that is already resolved: Promise.resolve(value)
If it is passed a non-promise, it will immediately be fulfilled w/ that value, if it is passed a promise it will be resolved to that promise

creating a new promise (that is not auto-rejected/resolve)is done via the promise constructor.
The promise constructor takes a callback known as the executor function.
the executor function itself takes the arguments resolutionFunc, rejectionFunc.
We do not implement resolutionFunc and rejectionFunc ourselves, the executor function will get them passed in when necessary.
The only thing we do with the executor functions argumetns resolutionFunc and rejectionFunc is call them when we want to resolve/reject.
As with the Promise.resolve and .reject, you pass the rejectionFunc the reason for rejecting, and the resolutionFunc the thing you want to fulfill with, or another promise

JS has a few methods for acting on multiple promises at once:
Promise.race() takes n promises and runs the attached callback ⁑once⁑ the first promise resolves.
Promise.all()/allResolved() runs the attached callback once all passed promises are resolved. The attached callback will recieve all returned results as an array.
⟮Promise.allSettled()⟯ is like ⟮Promise.all()⟯, but the ⟮former⟯ will ⟮continue even if one rejects⟯, the ⟮latter⟯ will ⟮not⟯

Pretty much all operations of the fs module in node have an ⟮async⟯ and a ⟮synchronous⟯ method, where if the ⟮async⟯ method is called `⟮foo⟯` the ⟮synchronous⟯ method is called `⟮fooSync⟯`
In node, asynchrony is by default implemented via callbacks.
In node, any asynchronous operation that could fail takes a error callback.
In node, any asynchronous operation that could return something useful takes a success callback.
in node, most functions are still designed for callbacks, however you can use util.promisify().
util.promisif()y takes a function following with a error-first callback as the last argument, and returns a version that returns promises.

Promisifying is making someting return a promise which wouldn't normally.

### asynchronous techniques

hooks and event handlers are asynchronous programming techniqyes.

#### hooks

A hook is an action that is defined on a thing and is called when the thing is in a certain state, e.g. before a function call.

#### Events

Technically, an event listener watches for an event, at which point it calls the event handler to deal with it.
In casual use, event listener and event handler are synonyms.

## misc

Memoization is the form of caching that caches the return value of a deterministic callable unit

### recursion

recursion ≈ self-inclusion

# Records

A record is a collection of fields, possibly of different data types, typically in a fixed number and sequence. 
A type that defines a record is a record type.
Most programming languages allow creation of instances of record types.

## Principles

Encapsulation refers to grouping together related things somehow, e.g. within records.
In OOP, encapsulation is often used to mean bundling the data and the methods that operate on it in one construct
Information hiding is hiding the internals of a thing from the  outside.

## Class and instance entities

A class x is a x operates on/is defined on a class rather than an instance.
An instance x operates on/is defined on an instance of a record.
A class function may also be known as an associated function.
Class x ≈ static x
generally, one mainly talks of class, instance methods, which operate on classes/instances, and class, instance variables
class variables + instance variables = fields
Members are generally all methods and fields of a record, no matter if class or instance.
ergo: members = member fields + member bariables
A piece of data on a record is called a field

In rust, a class method/associated function is called by using the :: operator

static|Java|C#|JS
does not take self as argument|Rust

## self-reference

self/this are keywords to reference the current record/other thing

### self/this in different languages

self|Python|Ruby|Rust
this|C#|Java|JS

### typeof self

In rust, `Self` is the type of the current record.
In rust, `self` has the type `Self` (or `＆Self` if borrowed)

### self/this binding

Many languages bind self/this automatically in methods, all others typically bind self/this explicitly by taking self/this as their first arguments.
In JS, any function binds this, even those that are not methods. Outside of a function, this refers to the global object.
to refer to the this representing the global object even within places that bind this to something else, use `globalThis`.

#### self and methods/assocated functions

In certain languages (Rust, Python), methods must take self as the first argument, else they are class methods/associated functions.
In rust, taking `self` takes ownership and thus invalidates previous references, ergo one generally wants to take ＆self or ＆mut self.
In rust, one uses :: instead of . to call associated functions

## Methods

A method is a callable unit that is a member of a record.
To make an object B do something, an object A must send a message.
in OOP, a method call is the way to send of message: The originator object is implicit, the target is specified manually, the method called is the message, and the arguments are well the arguments.
Ergo, in OOP objects generally use message passing to communicate.
In JS, methods are specified without using `function`, merely name and param list.
There is an older version of specifying methods in JS that is ‹name›: ‹anonymous-function›, this only works for object literals.

### Getters and setters

Also called accessors and getters.
A getter returns a field of a record.
A setter changes a field of a record.
Setters are often used to perfrom some sort of validation before changing the field of a record.
Getters and setters may help enforcing information hiding.

Ruby syntax:
def name=(value)...|setter

JS ＆ TS:
get foo()
set foo()
only within a class

You can only interact w/ ruby instance variables via getters and setters, trying to use it without those will give you a NoMethodError

## passive data structure

AKA plain old data structure (PDS)
A passive data structure is a data structure, especially a record with fields but no other object-oriented features.

## Structs

Struct is not an incredibly well-defined term, but is generally a record with the possibility for methods, but not the whole inheritance etc. stuff of classes.
In rust, struct declarations use the keyword struct.
Both struct delcarations and initializations in rust use a very assoc-array like syntax.
struct User { username: String, ...}
Tuple structs are either 'tuples with a name which can be instantiated' or 'structs with anonymous but ordered fields'.
if a variable and a struct field have the same name, you can write `foo,` instead of `foo: foo,`

## impl

Rust allows implementing methods or associated functions for structs, tagged unions (enums) and traits via the impl keyword.
when used for implementing things on structs/enums/traits, the construct used is called an impl block
the syntax for impl blocks for structs and enums is `impl ‹name› ‹block›`
the syntax for impl blocks implementing traits for structs is `impl ‹traitname› for ‹thingname› ‹block›`
Any thing may have as many impl blocks as you like.
For any impl block, we may indicate that we only want to implement it for something whose generics either are of a certain type or implement certain traits.
When we implement something, we can only rely on other things of the thing we're implementing existing, plus whatever trait bounds we've established.
we may `impl` a Trait without any `for` clause to provide a default implementation.
`impl ‹trait-list›` does not start an impl block and instead refers to a type that implements trait-list, with the advantage that this syntax can be used outside of a type parameter.

## fields 

In JS, fields themselves have properties (such as enumerable).
In JS, enumerable fields are those that will be enumerated over in a `for-in` loop.
generally, properties added 'normally' are also enumerable
‹object›.propertyIsEnumerable(‹name›)
properties that are not inherited (that is, they are there not because of the prototype chain, they of course then be inherited by other things) are called own properties
‹object›.hasOwnProperty(‹name›) 
The ⟮Object⟯.⟮assign⟯⟮(foo, bar)⟯ method ⟮copies⟯ all ⟮enumerable⟯ ⟮own⟯ ⟮properties⟯ from ⟮one or more source objects⟯ to ⟮a target object.⟯ 

## Classes ＆ objects 

An object in object-oriented language is essentially a record that contains procedures specialized to handle that record; and object types are an elaboration of record types.

Keyword to declare a class is done by the keyword `class` in pretty much all programming languages which have it.

A singleton (AKA the singleton pattern) is a class that can only have a single instance of that class. It is useful when you don't need multiple instances of a thing (the null object, a logger), or to coordinate states.

method in lua function object:method(...)

in languages with type annotation, the type annotation of an object is generally its class (e.g. MyClass myObject = new myObject();)


### Methods ruby

In ruby, methods that will return a boolean are marked by a ?
In ruby, methods that do something destructive are marked by a !

In ⟮documentation⟯, these methods are referenced...|
⟮class methods⟯|⟮.method or :​:method⟯
⟮instance methods⟯|⟮#method⟯



### pure OO

A pure object oriented language is one where everything is treated as an object.
There is much discussion on what it means to be 'treated as an object' for pure OO languages, but most commonly, it is at least:
1) Everything you operate on is a first-class Object
2) The only thing you can do with an object is call a method on it.
Therefore, 
1) Methods may only return other objects.
2) Operators (if they exist) are syntactic sugar for methods.
It is a matter of debate which languages are sufficiently pure OO to qualify: 
Ruby, Python, and JS allow methods to be called on pretty much anything, even primitives, since all primitves are boxed.
Only Ruby (of the languages I know) is quite pure enough to be called a pure object oriented language, I think

### Inheritance

Superclass aka base class
subclass aka derived class
In most programming languages, you refer to your superclass=base class with the keyword `super`.
In most programming languages, you specify a subclass/superclass relationship like so: Subclass extends Superclass
In ruby, you specify a subclass/superclass relationship like so: Subclass ‹ Superclass
In C#/Java, making a class final disallows a subclass from inheriting from it.
In C#/Java, making a method/static function final disallows a subclass from overriding it it.
Most languages only support single inheritance, some languages (among those I know Perl and Python) also allow multiple inheritance

### abstract ＆ static classes 

Abstract classes are generally declared with the abstract keyword. 
Within abstract classes, members are also declared with the abstract keyword.
Both abstract and static classes/members are not instantiable.
Abstract classes/members are designed mainly to be inherited from.
Since abstract classes/members cannot be instantiated, they must be overriden to be used.
JS does not support abstact things, however you can simulate it by using the @abstract/@virtual JSDoc tag.

### Constructors/object creation

Creating a new object via a constructor is done by the new operator in most languages, but not in Ruby or Python.
TS calles things that can be used to create new things `newable`.

A constructor is generally a callable unit and thus called with ()
Rust doesn't use any operator to create new Structs. In general, you use literals, some type provide a new() associated function.
In C#, Java, the constructor has the same name as the class.
In Ruby, the constructor is defined by the initialize function within the class (class SomeClass\n  def initialize(...), and called by calling the new() method on the class (SomeClass.new())
In JS, the constructor is named constructor
Many languages allow us to declare many different constructors with different arguments.
Most languages provide a default constructor if you don't provide one, which does nothing besides create the object.
In JS, you may not use arrow functions as constructors

A factory function is any callable unit which is not a class/constructor that returns a new object.
Ergo, factory functions create things without using the new keyword.
in Rust, many things are created by a factory function `new()`, which is an associated function of the struct.

### immutable objects

an immutable object is an object which cannot be changed once it's been created.
in JS, Object.freeze(obj) makes the object an immutable object.
In TS, Readonly ‹T› constructs a version of T whose properties are all set to readonly, making it a immutable object.

### Access modifier

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. 

default accessibility|language
default (= package)|Java
public|Python, JS
private|Rust
Most language with any kind of access modifiers have at least a public private distinction
public (most programming languages), pub (Rust)|any code
private|code within the class
Most languages with a public/private access modifier distinciton will use the public/private keyword to mark the one that is not the default anyway
JS is an exception, it marks private members with #

protected|same class and subclasses|Java
package|within the same package|Java
in java, the package access modifier is the default
JSDoc allows the simulating of the four access modifiers that Java has by using @access ‹access-modifier› or @‹access-modifier›

A ⟮private item⟯ can be accessed by ⟮its immediate parent module⟯ and ⟮all its child modules⟯
A public item can be accessed as a private item can, and additionally also through a chain through its ancestors.
In rust, each field of a struct has its own access modifier, which must be set to public if desired.

### Interfaces

mixins are pretty similar concepts.
In OOP an interface is a set of methods that anything that implements that interface must also implement.
Interfaces in programming standartize behavior
If a given programming language has syntax for them, generally keyword interface.
Indicating that one follows an interface is generally done with the implements keyword.
Something conforming to an interface is generally said to implememnt it.
If something implements an interface, it generally must implement all methods of that interface.
In the past, Java did not allow variables in interfaces. as of today, they are allowed, but subject to heavy restrictions.
In interfaces in Java/C#, you most commonly merely specify method stubs. (in the past this is the only thing you could do, this is no longer true)
Method stubs are method signatures without the implementation, in Java/C#, they are followed by a ;.
In most languages, a record may implement multiple interfaces/traits.

#### Traits

Traits in Rust are broadly similar to intefaces in other programming languages.
Traits in Rust can be implemented for types you did not define.
However, the trait ∨ the thing its implemented on must be local to the crate
Traits allow for blanket implementations, that is implementing a trait for anything that implements one or more other traits.
impl‹T› ToString for T where
    T: Display + ?Sized,
{ ... }
In rust, the keyword to declare a trait is `trait`
`trait ‹name› ‹block›` 
blocks of trait declarations contain method signatures.
In rust, deriving a trait is automaticallly generating trait implementations for a given thing.
In rust, derive is implemented via an annotation that takes a list of Traits.

In rust, the orphan rule says that either a trait or the thing it is being implemented on must be local to our crate.
In rust, the reason for the orphan rule is that otherwise when using multiple crates, they may end up trying to implement the same trait on the same type in different ways, creating conflicts (and dependency hell)

In rust, traits may exist in a supertrait/subtrait relationship.
A supertrait S of trait T means that any type implementing T must also implement S.
A subtrait S of trait T means that any type implementing S is also guaranteed to implement T.

syntax for declaring a trait with a supertrait: `trait ‹subtrait› : ‹trait-bound›`

### OOP

C#, Java

### is X an object of Y

someobj instanceof class|JS

### Duplication/Replication

A deep copy is a copy of a data structure where things referenced in the original data structure are also copied.
A shallow copy is a copy of a data structure where references in the original data structure are merely copied, and still refer to the same thing.
Deep copying is recursive and more computationally expensive.

shallow copy
copy (module copy).copy(foo)|Python
foo.copy()|Python (only collections)|Rust

deep copy
copy (module copy).deepcopy(foo)|Python
foo.clone()|Rust

### toString()

Most languages with objects have a tostring method to convert these to strings for debugging purposes.
It can often be useful to overwrite the default tostring implementation for more useful custom debugging.
tostring methods are often called implicitly during coercion.

‹thing›.toString()|Java|JS
‹thing›.ToString()|C#
‹thing›.to_string()|Rust
‹thing›.__str__(), called via str(‹thing›)|Python
‹thing›.to_s() or .to_str()|Ruby

The difference between Ruby's to_s() and to_str() is that to_s() is implemented in the (almost) top type (Object), and is called for some coercions only, while to_str() indicates that we want to treat the thing as a string in most cases, and thus allows for coercion in more circumstances.

to_string() is part of the ToString trait.

### Boxing

A box is a minimal object wrapper around another type.
The types that are most commonly boxed are primitives, sometimes boxing is restricted to this narrower definition.
putting values into a box is called boxing, the opposite unboxing
A wrapper is any entity that encapsulates/wraps around another thing.
Implementation-wise, it may be that the whole box is stored on the heap as an object would be, and we only have a pointer to the box, or as Rust seems to do it the Box may merely contain a pointer to whatever data, which is moved to the heap. (though I wonder if these are different)
Memory-wise, since boxes are objects, boxed data will be stored on the heap.
Boxing primitives allows us to interact with them using a similar interface as other objects; this enables the Everything you operate on is a first-class Object constraint of pure OO, consequently most primitives are boxed in languages aspiring to pure OO such as Python, JS, Ruby...
Autoboxing is the conversion of primitves to boxed types when relevant.
Since boxed data will be stored on the heap, it is not necessary for it to have a constant size, thus boxed data allows more flexibility.

Rust's construct for boxing is Box‹T›.

# Pragmas

In computer programming, a directive or pragma (from "pragmatic") is a language construct that specifies how a compiler (or other translator) should process its input
Perls pragmas have the syntax use ‹name›;
Perls pragma use warnings; causes the perl program to display warnings in certain circumstances.

## Strict mode

Both perl and JS have a strict mode pragma.
Strict mode pragmas cause programs to fail in certain cases.
Start strict mode in JS: "use strict";
in JS, non-strict mode code is called sloppy mode
In JS, modules and classes are strict by default
In JS, strict mode applies to the whole file if it's the first statement if the file, and to the whole function if it's the first statement in the function

Strict mode in JS:
- reserves certain keywords (for future proofing)

## shebangs

An interpreter directive is a type of pragma that specifies which interpreter to use for a thing.
On a unix-like OS, if a script starts with the shebang, followed by a path, this is an interpreter directive, and specifies with which binary to execute the script.
The shebang consists of the characters #!.

## attributes

Attributes are pragmas (mostly) for rust.
attribute begins|applies to
#!|whole crate
#|next item

attributes have four forms for taking arguments (or none)
ø|no arg
= "‹value›"|one arg
\(‹value›{, ‹value›}\)|one or more unnamed args
\(‹key› = "‹value›"{, ‹key› = "‹value›"}\)|one or more named args

rust-attribute ::= #[!]\[‹rust-attribute-name›‹rust-attribute-arguments›\]
rust-attribute-arguments ::= ø|(= "‹value›")|(\(‹value›{, ‹value›}\))|\(‹key› = "‹value›"{, ‹key› = "‹value›"}\)

# modules

The main purpose of modules is encapsulation.
A module is as self-contained set of code.
Most commonly, a module is defined by each code file.
In Rust, modules are instead defined manually via mod ‹name› { ... }, or via `mod ‹filename›`
Packages and modules are sometimes synonyms.
conta
In python, a package is a collection of modules (and perhaps other packages).
In python, each .py file is a module.
A package must contain a __init__.py file

If you want to import/export multiple members, most languages have the syntax {member1 [as name1], member2 [as name2], ...}
In some languages, when you're importin multiple members and want to bring the module itself into scope, you can include the keyword for self-reference (this or self) in the list of things to im-/export.
Import/export anything uses * in most languages
in JS, you can only import/export within modules.

## prelude

Most languages have a number of things that are automatically imported. Rust (and haskell) calls this prelude.

## module systems

### Rust

Rust allows nesting of modules in a module tree.
In rust, the root node of the module tree is `crate`, sometimes called the crate root.
The crate root serves as the entry point for the rust compiler.
rust allows for both `use`ing/referring absolute and relative paths for the module tree, where absolute paths start at the crate root, and relative paths start at the current module.
Rust's module nesting is defined either directly by nesting `mod ‹name› {...}`s or by a combination of file hierarch and `mod ‹filename›`
calling `mod ‹filename›` without a block argument integrates an existing rust file as a child of the module we're currently in in the module tree, however the file structure must also reflect this.

Rust also allows having multiple crates with independent module trees in the same package.
In rust, there are two types of crates, binary and library.
A package can contain 0-1 library crates and 0-∞ binary crates.
the crate root for binary crates is called main.rs.
the crate root for library crates is called lib.rs

### JS

#### CommonJS

CommonJS is ⟮a module ecosystem⟯ mainly used by node

let/var/const ‹name› = require(‹path›)

#### ES Modules

To contrast with module systems such as CommonJS, the official implementation of modules in JS are known as ES Modules.
In JS, ES Module import/export statements can only be used within a module.
Modules are declared in script tags by adding type="module".

## importing

Import statements tell whatever's executing the program to act as if the specified entities were part of the file, potentially renaming them.
In most languages, you can only import things that were first exported.
In most languages, import statements must be in the beginning of the file.
In most languages, you may only export top-level items.
Import statements have the general syntax
import ‹members› [as ‹name›] from ‹path›
In many systems module/index.‹suffix›  can be imported as just module

### Runtime importing

JS supports an import() function that allows dynamic runtime imports.
import() returns a promise.

### in various languages

#### JS

in JS you can leave out `‹members› from` if you only want the side effects

#### Python

Python instead has the order from ‹path› import ‹members› [as ‹name›]

#### CSS

In vanilla CSS, you can import other stylesheets via the non-nested at rule @import.
@import syntax: @import ‹path› (‹media-query›|‹feature-query›);
For CSS, the ‹path› may be an ‹url› or a ‹string›

#### Rust

Rust uses `use` instead of import.



### SCSS/Sass 

Three keywords: @use, @import, @forward (@include is not an import statement!)
Syntax alwas keyword ‹path› [as ‹name›]
@forward foo doesn't allow the current stylesheet bar to access the things in foo, but ⟮allows anything @using bar to access them.⟯

### latex

⟮\input⟯ and ⟮\include⟯ both ⟮import latex code into the current file⟯. 
⟮\input, \include⟯ are useful if ⟮you want to split up you latex into multiple files⟯. 
both ⟮\input⟯ and ⟮\include⟯ take ⟮a path of the file to import⟯. 
⟮\include⟯ but not ⟮\import⟯ ⟮adds a \clearpage when importing⟯, and thus ⟮can't be used in the preamble⟯ 
using ⟮\include⟯ allows you to use ⟮\includeonly⟯, which takes ⟮an argument⟯ of ⟮a list⟯ and will ⟮only import the \includes listed within⟯, cutting down on ⟮compile time⟯. 

## exporting

Exporting is selecting entities for potential import.
In most languages, exporting is required so they can then be imported.
General syntax: export ‹members› [as ‹name›] [from ‹path›]
re-exporting members is exporting members from a different (generally child) module.

JS allows one default export per module. The default export is the only thing that may be imported without curly braces, and can be renamed without `as`.
JS default exports are funtionality-wise not super useful, but be useful in indicating that it is the most important export / only relevant export.
In JS, non-default exports are known as normal/named exports.
In JS, using the from ‹path› component of exports allows for re-exporting.
JS re-exporting allows aggregating exports in a single file.

In rust, re-exporting works by making a `use` itself public.

In commonJS, exports are declared as properties of the module.exports object.

### default exports

# Memory 

Memory allocation is setting aside memory for a purpose, e.g. to store entities of a programming language.
Memory deallocation is releasing previously allocated memory.

## The stack and the heap

The call stack is often only called the stack.
The call stack implements the stack ADT
The call stack is made up of stack frames.
The stack frame usually includes at least ⟮the arguments⟯, the ⟮return address⟯, and ⟮local variables⟯.
When we call a callable unit, a new stack frame is pushed on the stack, and the stack pointer is updated.
When we return from a callable unit, the stack frame at the top of the stack is popped, and the stack pointer is updated.
The stack frame at the top of the stack is the stack frame of the currently executing callable unit.
The stack pointer points at the most recently referenced location on the stack.
The memory address at which the stack starts out when it is size 0 is the stack origin.
If the stack has size 0, the stack pointer is (or better be :P) at the stack origin.
The stack may grow upwards = larger memory addresses or downwards = smaller memory addresses (however this needs to be fixed in advanced)
stack grows upwards|stack overflow|address › stack_origin_addr+ max_stack_size
stack grows upwards|stack underflow|address ‹ stack_origin_addr
stack grows downwards|stack overflow|address ‹ stack_origin_addr-max_stack_size
stack grows downwards|stack underflow|address › stack_origin_addr
Since each call to a callable unit adds a stack frame, infinite recursion causes a stack overflow (unless the compiler optimizes the recursion away)
The stack is significantly faster than the heap, since it's implementation is far simpler.
The heap can become fragmented.
The heap is managed much less strictly than the stack.

In general, there is one stack per thread and one heap per process (instance of a program)


## stack trace

A stack trace is a report of the active stack frames during the execution of a program.
Stack traces are often automatically printed in the case of unrecoverable errors
to show a stack trace on error in rust, set the env variable `RUST_BACKTRACE=1`

## static and dynamic as size

static types/statically sized types (!= static variables) have a size that can be known at compile time.
dynamic types/dynamically sized types have a size that cannot be known at compile time. 
One of the main cases for static arrays is that they are static(ally sized) types.
Only statically sized types can be stored on the stack (= in automatic variables).
Dynamically sized types are stored on the heap. 
To store dynamically sized types on the stack, one typically has a pointer.
Most record types are dynamically sized types.
In rust, statically sized types implement `Sized`, dynamically sized types implement `?Sized`
In rust, pointers to dynamically sized types are fat pointers.
In rust, the most common dynamically sized types are trait objects and slices.
Pointers to slices are fat pointers because they also store a length of the slice.
trait objects are fat pointers because they also store a virtual method table.

## static, automatic and dynamic variables

The lifetime of a variable is the time where it is in a valid state, which generally coincides with when it has memory.
The lifetime of a value is the time where it occupies a certain region of memory.
The lifetime of a variable cannot outlive the the lifetime of its value.

A static variable is allocated for the entire lifetime of the program.
Static variables fall outside of the clear stack heap distincition, as they are stored in a data segment.
A data segment is a part of the object file (file of object code = compiler output, see compilers) that contains static variables.
The read-only data segment is the part of the data segment (or an extra data segment) that contains read-only static variables (ergo static consonants)
the read-only data segment may be called rodata.

### automatic and dynamic variables

The terms automatic and dynamic variables/memory allocation are mainly used in C-style languages.

An automatic variable is a variable that has its memory allocated and deallocated automatically when the program enters and leaves the variables scope.
Automatic variables have a lifetime of the variables scope.
In general, automatic variables genrally must be statically sized.
Any automatic variable can go out of scope.

Dynamic memory allocation creates lifetimes of your choosing: their memory is allocated and deallocated by you or a memory management system.
(dynamic variable isn't a real term, I've introduced it here for terminological parallelism)
Def: Automatic/static variables use automatic/static memory allocation.

Use-after-free is a vulnerability where memory is used after it has been deallocated.
Use-after-free can generally only occur to dynamically allocated memory.

### lexical and nonlexical lifetimes

In lexical lifetimes, the lifetime of a value is until the end of its lexical scope
In non-lexical lifetimes, the lifetime of a value is until it is last used within its lexical scope.
In general, the difference between lexical and non-lexical lifetimes does not matter, however if the value is a reference Rust's borrow checker cares about if you're holding on to it. Hence, rust implements non-lexical lifetimes for references.

lifetime-annotation ::= '‹name›
lifetime-annotations specify named lifetimes
You must specify all lifetimes you are gonna use as type parameters.
In rust, in theory all references used in callable units require a lifetime annotation, though in most cases it can be left out due to lifetime elision.
lifetime annotations cannot be elided in cases where the compiler cannot figure out how parameters and return value relate.
ergo, lifetimes cannot be elided if the function returns a reference, the function takes more than one reference as a input parameter, and the function is not a method.
Importantly, lifetime annotations beside 'static do not change lifetimes, merely indicate how lifetimes of references relate (specifically, "treat all these lifetimes as the lifetime of the shortest one")
Rust indicated static variables with a 'static lifetime annotation

## memory management

Memory management is managing the memory of an application.
One of the main jobs of memory management is memory allocation and deallocation.
Memory management may be manual = performed by the programmer or automatic = performed by the programming language automatically.
Dynamic memory allocation can be handled by manual memory management or by automatic memory management.
Automatic variables are handled by automatic memory management.
static variables are not subject to memory management.
Most higher-level programming languages have no manual memory management at all.

A destructor is a method which is envoked just before the memory of a thing is released.


### types of data

Garbage data is data that cannot be used anymore (e.g. reference out of scope)
The opposite of garbage data is live data.
Outside of programming, garbage data is sometimes used for data that is unusable in some way (e.g. corrputed, garbled)

### manual memory management

In C, dynamic memory allocation is done by manual memory allocation.
malloc() allocates the specified number of bytes
calloc() allocates the specified number of bytes, and sets them to 0
free() releases teh specified block of memory back to the system.

### automatic memory management

The three most common types of automatic memory management are garbage collection, automatic reference counting, and RAII.

#### garbage collection

Garbage collection is a form of automatic memory management in which a garbage collector deallocates garbage memory.

#### reference counting

(manual) reference counting is a form of manual memory management
automatic reference counting is a form of automatic memory management
In reference counting, when no more references to a certain value exist, then it is destroyed
In reference counting, a value (most commonly an object) as some kind of field indicating how many references to it exists.
In manual reference counting, we call increment and decrement methods to indicate how many references there are.
In automatic reference counting, increment/decrement methods for refrences are called automatically. 
Circular set of references are called reference circles.
reference circles can allow things in refrence counting to never reach reference count 0 and thus be destroyed.

In rust, reference counting is implemented by Rc‹T›.
Rc‹T› allows multiple owners, where each call to clone() increases the reference count.
In rusts implementation of reference counting, dropping Rc‹T› decreases the reference count.

#### RAII

RAII = resource acquisition is initialization
In RAII, memory for a value is allocated by its constructor and deallocated by its destructor.
In rust, the destructor for RAII is drop() of the Drop Trait.
In rust, when a variable goes out of scope, the value it owns is dropped.

# libraries


## web frameworks

A framework is a set of libraries where the framework itself has control by default, and only exposes an API.
A framework: Don't call us, we'll call you.
A web framework is a framework for use in web development.

### commonalities

#### templating

⟮a template engine/processor⟯ is something that ⟮combines⟯ ⟮a template⟯ and ⟮data⟯ ⟮into some kind of result⟯ 
⟮templatees⟯ are written in ⟮template languages⟯ 

###### Liquid


⟮liquid⟯ is ⟮a template language⟯) 
⟮Liquid⟯ was develped from ⟮Embedded Ruby Templates (ERB⟯) 
⟮Liquid⟯ is ⟮kinda similar to Ruby⟯ due to ⟮it being developed from Embedded Ruby Templates (ERB⟯) 

⟮Liquid⟯ ⟮tags⟯ look like this ⟮{% ... %⟯}. 
Liquid ⟮tags⟯ ⟮surround⟯ ⟮logic/control flow⟯. 
In liquid, ⟮outputting⟯ is generally done ⟮within double curly braces {{ ... ⟯}} 
```
{% if user %} 
Hello {{ user.name }}! 
{% endif %}
``` 
⟮adding a -⟯ ⟮to {{ or {%⟯ ⟮h9,10;like {{-, {%-⟯ ⟮strips whitespace from the relevant side⟯ 


⟮Liquids⟯ ⟮loops⟯ are odd in that the⟮y accept a number of additional parameters⟯ ⟮after the main condition⟯, in the format ⟮key:value⟯ and separated by ⟮spaces⟯ 


span:2;Liquid loop parameters
⟮start where the previous loop of the same iterator left off⟯|⟮offset:continue⟯
⟮start at the offset/index n⟯|⟮offset:n⟯
⟮iterate through the array in reverse⟯|⟮reversed⟯
⟮only do n iterations⟯|⟮limit:n⟯


```
{% for item in array foo:bar foo2:bar2 %}
  {{ item }}
{% endfor %}
```


⟮cycle⟯ ⟮takes n arguments⟯ and ⟮prints the next one (from the last time this  was called⟯). 


```
{% cycle item1, item2... %}
``` 


⟮Cycle⟯ can be used to apply classes for ⟮even/odd elements⟯ or ⟮to any nth elements⟯. 
⟮Without the cycle group paramter⟯, ⟮all cycles in the document⟯ ⟮cycle the same thing⟯ 
⟮if you want to cycle multiple things⟯ in ⟮the same document⟯, you need to ⟮use cycle group paramters⟯. 
The syntax for the cycle ⟮group parameter⟯ is ` ⟮"name":⟯`. 
```
{% cycle "name": item1, item2... %}
```

⟮{% liquid ... %}⟯|⟮write liquid logic in a single block⟯
⟮{% raw %} ... {% endraw %}⟯|⟮disable tag processing (different from comments in that non-liquid stuff will be rendered⟯)
⟮{% render "foo" %}⟯|⟮render another template foo⟯
⟮{% tablerow foo in bar ...⟯|⟮generate html tables⟯


```
{% liquid
case section.blocks.size
when 1
  assign column_size = ''
when 2
  assign column_size = 'one-half'
when 3
  assign column_size = 'one-third'
else
  assign column_size = 'one-quarter'
endcase %}
```

There are ⟮two different namespaces⟯ for ⟮variables⟯ in ⟮liquid⟯: one for ⟮assign/capture⟯ and one for ⟮increment/decrement⟯ 
⟮Normal variable assignment⟯ uses the ⟮assign⟯ keyword 
```
{% assign my_variable = false %}
```
⟮{% increment / decrement foo %⟯} ⟮increments/decrements⟯ a variable foo ⟮increment⟯ ⟮variables⟯ start at ⟮0⟯ and ⟮decrement⟯ ⟮variables⟯ starts at ⟮-1⟯ 
⟮everything within⟯ ⟮a capture block⟯ is ⟮assigned to the specified variable⟯ 
⟮capture⟯ captures ⟮a whole string⟯ into ⟮a new variable⟯, allowing ⟮string interpolation⟯ or ⟮other complex logic⟯ to generate the variable 
```
{% capture my_variable %}あっ！いやだ！{{page.author}}によってバリアブルに入れられてしまいました。！{% endcapture %}
``` 

### front-end frameworks

#### types of web pages and their generation

Fundamentally, a ⟮web page⟯ may either be ⟮static⟯ or ⟮dynamic⟯. 
A ⟮static⟯ web page is ⟮delivered to the web browser⟯ ⟮exactly as stored on the web server⟯. 
A ⟮dynamic⟯ web page is ⟮generated in some way⟯. 
⟮Static generation⟯ merely creates ⟮static web pages⟯. However, since ⟮they are often generated in a manner similar to dynamic web page⟯, ⟮static generation⟯ is often seen as ⟮something inbetween dynamic and static web pages⟯. 
A ⟮dynamic web page⟯ may be generated ⟮client-side⟯ or ⟮server-side⟯. 
A ⟮dynamic webpage⟯ ⟮generated client-side/server-side⟯ is said to use ⟮client-side/server-side rendering⟯. 


⟮Client-side rendering⟯ ⟮(c:34;s4;CSR⟯) generally involves only having ⟮a minimal HTML page⟯ and ⟮a JS bundle⟯, which then ⟮handles everything elsee.⟯ 
The pages ⟮CSR⟯ produces are generally called ⟮single-page applications⟯. 
⟮Server-side rendering⟯ ⟮(c:36;s35;SSR⟯) has ⟮a server generate the web page⟯, generally using ⟮a server-side programming language (in the past most commmonly PHP⟯), which is then ⟮served to the user fully baked⟯. 
⟮CSR⟯ only ⟮needs to communicate w/ the server⟯ if ⟮new data is needed⟯. 
Whenever ⟮the user navigates to a different page⟯, ⟮CSR⟯ ⟮can usually handle it internally⟯, while ⟮SSR⟯ ⟮needs to make a new request for a new page⟯. 
⟮Client-side rendering⟯ has ⟮longer⟯ ⟮initial load times⟯ and ⟮shorter⟯ ⟮subsequent load times⟯ than ⟮server-side rendering⟯ 

⟮Client-side rendering⟯ often has ⟮problems with SEO⟯, as ⟮the original HTML basically contains nothing⟯ 
The difference between ⟮static generation⟯ and ⟮server-side rendering⟯ is that ⟮static generation⟯ ⟮generates the HTML⟯ ⟮at build time⟯, while ⟮server-side rendering⟯ ⟮generates the HTML⟯ ⟮on each request⟯ 

⟮Static-site generator⟯ by ⟮github⟯: ⟮Jekyll⟯ 

#### different products

Express is the most popular server-side web framework for node.
Angular is the successor to AngularJS
Angular is sometimes called Angular 2
While AngularJS was written in JS, Angular (2) was written in typescript.
Angular and Vue.js are the two most popular front-end frameworks that are clearly frameworks.
React is often called a framework and would be the most popular front-end framework if it was, but is more like a library.
Svelte works like a front-end framework, but actually compiles in advance.

#### react 

##### unsorted

{{c4::setState}} may take a value, or a {{c1::callback}} which {{c2::recieves the previous value}} and {{c3::returns the next value}}

{{c4::custom hooks}} are meant for {{c3::reusing logic}}, which you can't just {{c1::do via a normal function}}, since {{c2::normal functions can't call the built-in hooks}}

{{c3::the useState function}} is a {{c2::Hook}} called the {{c1::State}} {{c2::Hook}}

{{c2::outputting}} the {{c3::virtual representation of a component}} into the {{c4::final UI representation}} (most often the {{c4::actual DOM}}) is known as {{c1::mounting}}

{{c1::useEffect}} takes {{c2::a callback}} to specify the side effect
{{c1::useEffect}} runs {{c2::asynchronously}}, if you need a {{c2::blocking}} version, use {{c3::useLayoutEffect}} instead
{{c1::useEffect}} is called when? {{c2::after every render}} (by default)
{{c1::useEffect}} is a {{c2::Hook}} that allows you to do {{c3::side effects}} such as {{c3::changing the DOM}} from a {{c4::function component}}

{{c1::useContext}} is a {{c2::hook}} that {{c3::takes SomeContext}} and {{c3::returns the value for that SomeContext}} (the one determined by {{c4::the nearest SomeContext.Provider}})

{{c1::until which breakpoint on the container will follow the 100% plus padding thing}} is set in react-bootstrap by {{c2::the fluid="breakpoint" prop}}

{{c1::react-devtools}} are specific devtools that should make {{c2::inspecting react a lot easier}}

{{c1::formik}} and {{c2::react-hook-form}} are the most popular {{c3::react form libraries}}

{{c1::Lifting state up}} is putting {{c2::state}} that {{c3::needs to be shared}} in {{c4::the closest common ancestor}}
When lifting state up, the {{c1::state changes}} are then {{c2::passed back down}} as {{c3::props}}
To {{c1::lift state up}} in react, {{c2::child components}} {{c4::should not}} depend on {{c3::state}} anymore, but on {{c3::props}}
If child components have to {{c2::handle events}} when {{c1::lifting state up}}, the {{c3::event handlers}} should be {{c4::passed in}}, so they can {{c5::change the correct state}}

within {{c1::the render function}}&nbsp;≈ {{c2::the main body of a function component}} (≈ outside of&nbsp;{{c2:: useEffect and similar}})&nbsp;respectively, you may not do things {{c3::that cause side effects&nbsp;}}

within {{c1::&lt;SomeContext.}}{{c2::Consumer&gt;}} tags, you can {{c3::specify a function}} that takes {{c4::the value of the closest provider}} and returns {{c5::react elements/JSX to render}}<br/><div class="sub">
<pre><code>&lt;MyContext.Consumer&gt;
  {value =&gt; /* render something based on the context value */}
&lt;/MyContext.Consumer&gt;
</code></pre>
</div>

within class components, {{c2::outside of the constructor}}, you can {{c3::only change state}} via {{c1::setState()}}

when we're generalizing over all {{c2::foos}} and {{c2::setFoos}} we might {{c3::get from useState}}, we call them {{c1::state}} and {{c1::setState}}

what would you set to this.state.somekey to have a input type="text" be a controlled component? <span class="divider">-></span> {{c1::value}}

to {{c1::clean up}} useEffect stuff, <b>return</b> {{c2::a callback from it}}

the {{c1::useState}} function returns an {{c2::array of length 2}}, {{c2::[0]}} being {{c3::the current state}}, and {{c2::[1]}} being {{c3::the function to change the state}}

the values of variables that we {{c2::assign the useState() return values to}} are preserved even {{c1::after the function exits}}

the only time we can assign to {{c1::this.state}} is in the the {{c2::constructor}}

the hook {{c1::useState}} takes an argument of {{c2::the inital value}}<br/><div class="sub">
<div class="sub all-b">both useEffect and useContext take different arguments</div>
</div>

since you can {{c1::call useEffect multiple times}}, it's recommended to call it based on {{c2::separate concerns}}, not just {{c3::cram everything the component should do into the same useEffect}}

in contrast to {{c2::built-in hooks}}, {{c2::custom hooks}} can {{c1::take any arguments}} and {{c1::return anything}}

if you {{c1::return a callback from}} {{c2::useEffect}}, React will run it {{c3::before any new render (and before finally dismounting)}}

if you want to specify {{c1::an inital state}} that is {{c2::complicated}}, instead of {{c3::passing useState a value}}, you may also {{c3::pass it a callback}}

if you use {{c1::setState}}, but only {{c2::specify some of the keys}}, they will be {{c3::merged in to the previous state object}}

create-react-app&nbsp; Custom Templates are always named in the format {{c1::cra-template-[template-name]}}, however you only need to provide the {{c2::template-name}} to the {{c3::creation command}}.

conventionally, {{c1::the first value returned}} from {{c3::useState}} is called {{c4::e.g. foo}}, and {{c1::the second value}} is then called {{c2::setFoo}}

both {{c2::this}}.{{c1::props}} and {{c2::this}}.{{c1::state}} may be updated {{c3::asynchronously}}, if you want to make sure that {{c4::things are updated in the correct order}}, pass a {{c5::callback}}

a {{c3::custom hook}} is a JS {{c4::function}} whose name {{c2::starts with use}} and which may {{c1::call other hooks}}

You're not limited to putting {{c2::other elements}} within {{c3::the component tags}} to pass it as props.children, you can also {{c1::insert arbitray {someJS} }} in here.

You can only call {{c2::hooks}} {{c3::at the top level,}} that is not in {{c3::loops,}} {{c3::conditions}}, or {{c3::nested functions}}, because React {{c1::relies on the order in which the Hooks are called to determine which state is what}}

You can only call {{c2::hooks}} from React {{c3::function components}} (not {{c3::plain JS functions}}, even if {{c3::called from react components}}), or from {{c1::custom Hooks}}

Within the component class, besides {{c1::lifecycle}} methods, constructors etc., we can add {{c2::custom}} methods

While you can {{c2::pass an empty array}} to useEffect as the second arg, causing it to {{c3::only run once on mount}} (and {{c3::the return value once on unmount}}), it is {{c1::generally discouraged}}

While it's ideomatic to call a {{c1::render prop}} {{c2::<code>render</code>}}, any prop that {{c3::is a function}} and {{c4::another component uses to know what to render}} is a {{c1::render prop}}

When {{c2::specifying the array optional secondary arg}} for useEffect, you need to include {{c1::any states you will use in the array,}} or it will {{c3::use outdated values}}

When React sees an {{c1::element representing a user-defined component}}, it passes JSX {{c2::attributes}} and {{c3::children}} to it as {{c4::a single object}}. We call this object “{{c5::props}}”.

Whatever you {{c2::put in between}}&nbsp; {{c3::JSX component opening&amp;closing tags}} gets {{c4::passed on to the component}} as {{c1::props.children}}

Using JSX with React is... <span class="divider">-&gt;</span> {{c1::optional}}

To {{c3::pass arguments}} to React {{c4::event handlers}}, use {{c1::anonymous functions}} or {{c2::bind}}

To {{c2::conditionally render things}}, use {{c1::native JS constructs such as if, ternary, log-op}}

To make sure react {{c5::event handlers}} {{c1::get the correct <code>this</code>}}, you need to {{c2::<code>bind</code> them in the constructor}}, or use {{c3::public class fields}}/{{c4::arrow functions}} (which have their own downsides)

To instantiate a context provider of context Foo within JSX, use {{c1::&lt;}}{{c2::Foo.Provider}}{{c3:: value={somevalue} }}{{c1::&gt;&nbsp;}}

The {{c1::optional}} {{c2::second argument}} to useEffect is {{c3::an array of states}} - useEffect will only be called if {{c4::one of the values}} in {{c3::the array}} changed,&nbsp;

The steps react recommends to building an react app: {{c1::create a mockup of your site -}}&gt; {{c2::iidentify components}} -&gt; {{c3::build a static verion in react}} -&gt; {{c4::find out all the things that need state}} -&gt; {{c5::find out who should own the state}} -&gt; {{c6::add a way for handling changes}}<br>

SInce in react-bootstrap {{c1::.key-value often becomes key="value"}}, to {{c2::add new key="value" pairs}}, {{c3::add new .key-value classes}}

Normally you can only return {{c1::one element}} as a react component, but you may want to return {{c1::multiple elements}} without {{c2::a wrapper.}} for this, you can use {{c3::&lt;React.Fragment&gt;}}...{{c3::&lt;/React.Fragment&gt;}} or the short syntax {{c4::&lt;&gt;}}...{{c4::&lt;/&gt;}}

In the react {{c2::component constructor}}, we always need to call {{c1::super(props)}} first

In sharing information, react prefers {{c1::composition}} over {{c1::inheritance}}

In react, {{c1::inheritance}}-like behavior is achieved by {{c2::the more general component}} {{c3::recieving props from}} {{c2::the more specific component}}<br/><div class="sub">
<div class="sub all-b"><pre><code>function FancyBorder(props) {
  return (
    &lt;div className={'FancyBorder FancyBorder-' + props.color}&gt;
      {props.children}
    &lt;/div&gt;
  );
}
</code></pre></div>
</div>

In react, you can use {{c2::Context}} to {{c3::store global data}}, but you should {{c1::think if there isn't a better way to do it first}}

In react, to create a Context object, call {{c1::React.}}{{c2::createContext}}{{c3::(defaultValue)}}<br/><div class="sub">
<pre><code>const ThemeContext = React.createContext('light');
</code></pre>
</div>

In react, everything {{c2::nested within}} a {{c1::context provider}} has acces to {{c3::the Context}} with {{c3::the specified value}}

In react, a {{c1::controlled component}} has react as {{c2::the only thing managing its behavior}}, making its content {{c3::reflect the react state}}, and having {{c4::react update it}} based on {{c5::events}} (e.g. {{c5::onchange}})

In react, a component with a {{c1::render prop}} takes a {{c2::function}} that {{c2::returns}} a {{c3::react element}} and {{c3::calls it (the function)}} instead of {{c4::implementing its own render logic}}

In contrast to {{c3::most HTML attributes in react}}, {{c2::aria attributes}} are written in {{c1::kebab-case}}

In React, which <code>{{c1::&lt;option&gt;}}</code> is selected is not specified by {{c2::a <code>selected</code> attr}}&nbsp;on {{c2::the <code>&lt;option&gt;</code>}}, but by {{c3::a <code>value</code> attr}}&nbsp;on {{c3::the <code>&lt;select&gt;</code> tag}}

In React, the content of a {{c1::textarea}} does not live {{c2::between its tags}}, but instead {{c3::in a value attribute}}

How mutable are React elements? <span class="divider">-&gt;</span> {{c1::immutable}}

For easy list generation, it is often idiomatic in react to {{c1::return JSX}} from a {{c2::map function}}

Before {{c2::hooks}}, if you were writing a {{c1::function component}} and needed {{c3::e.g. state}}, we would have to have {{c4::converted it to a class component}}

<pre><code>function Example() {
  // Declare a new state variable, which we'll call count
  const {{c1::[count, setCount]}} = useState(0);

  return (
    &lt;div&gt;
      &lt;p&gt;You clicked {count} times&lt;/p&gt;
      &lt;button onClick={() =&gt; setCount(count + 1)}&gt;
        Click me
      &lt;/button&gt;
    &lt;/div&gt;
  );
}
</code></pre>

<div class='c1-f'>
When should the parentheses be here?
</div><br/><pre><code>const layout = (props) =&gt; {
  return (
    &lt;Aux&gt;
    ...
    &lt;/Aux&gt;
  )
}</code></pre> <span class="divider">-></span> {{c1::if the JSX returned is more than one line}}

<div class='c1-f'>
What's the problem here?
</div><br/><pre><code>  
  if (name !== '') {
    useEffect(function persistForm() {
      localStorage.setItem('formData', name);
    });
  }</code></pre> <span class="divider">-></span> {{c1::call hooks only at toplevel}}

<div class='c1-f'>
What's missing here?
</div><br/><pre><code>render() {
  return (
    &lt;ChildA /&gt;
    &lt;ChildB /&gt;
    &lt;ChildC /&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::the children should be wrapped in a fragment}}

<div class='c1-f'>
What would happen if we didn't include the &lt;&gt;...&lt;/&gt;?
</div><br/><pre><code>render() {
  return (
    &lt;&gt;
      &lt;ChildA /&gt;
      &lt;ChildB /&gt;
      &lt;ChildC /&gt;
    &lt;/&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::it wouldn't work}}

<div class='c1-f'>
What provides the props.children here?
</div><br/><pre><code>function FancyBorder(props) {
  return (
    &lt;div className={'FancyBorder FancyBorder-' + props.color}&gt;
      {props.children}
    &lt;/div&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::html content within &lt;FancyBorder&gt; tags}}

<div class='c1-f'>
What is setCount doing here, related to state?
</div><br/><pre><code>function Example() {
  // Declare a new state variable, which we'll call count
  const [count, setCount] = useState(0);

  return (
    &lt;div&gt;
      &lt;p&gt;You clicked {count} times&lt;/p&gt;
      &lt;button onClick={() =&gt; setCount(count + 1)}&gt;
        Click me
      &lt;/button&gt;
    &lt;/div&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::changing it}}

<div class='c1-f'>
What is count doing here, related to state?
</div><br/><pre><code>function Example() {
  // Declare a new state variable, which we'll call count
  const [count, setCount] = useState(0);

  return (
    &lt;div&gt;
      &lt;p&gt;You clicked {count} times&lt;/p&gt;
      &lt;button onClick={() =&gt; setCount(count + 1)}&gt;
        Click me
      &lt;/button&gt;
    &lt;/div&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::representing the current state}}

<div class='c1-f'>
What are we using here to manage state?
</div><br/><pre><code>function Example() {
  // Declare a new state variable, which we'll call count
  const [count, setCount] = useState(0);

  return (
    &lt;div&gt;
      &lt;p&gt;You clicked {count} times&lt;/p&gt;
      &lt;button onClick={() =&gt; setCount(count + 1)}&gt;
        Click me
      &lt;/button&gt;
    &lt;/div&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::hooks}}

<div class='c1-f'>
What are we doing here?
</div><br/><pre><code>class MouseTracker extends React.Component {
  render() {
    return (
      &lt;div&gt;
        <mark>&lt;Mouse render={mouse =&gt; (
          &lt;Cat mouse={mouse} /&gt;
        )}/&gt;</mark>
      &lt;/div&gt;
    );
  }
}
</code></pre> <span class="divider">-></span> {{c1::creating a render prop}}

<div class='c1-f'>
This is shorthand for?
</div><br/><pre><code>render() {
  return (
    &lt;&gt;
      &lt;ChildA /&gt;
      &lt;ChildB /&gt;
      &lt;ChildC /&gt;
    &lt;/&gt;
  );
}
</code></pre> <span class="divider">-></span> {{c1::<pre><code>render() {
  return (
    &lt;React.Fragment&gt;
      &lt;ChildA /&gt;
      &lt;ChildB /&gt;
      &lt;ChildC /&gt;
    &lt;/React.Fragment&gt;
  );
}
</code></pre>}}

<div class="c1-f">
What does the content between &lt;FancyBorder&gt; tags do?
</div><br><pre><code>function WelcomeDialog() {
  return (
    &lt;FancyBorder color=blue&gt;
      &lt;h1 className=Dialog-title&gt;
        Welcome
      &lt;/h1&gt;
      &lt;p className=Dialog-message&gt;
        Thank you for visiting our spacecraft!
      &lt;/p&gt;
    &lt;/FancyBorder&gt;
  );
}
</code></pre> <span class="divider">-&gt;</span> {{c1::becomes accessible as props.children}}

##### core react

###### using JSX

JSX is syntactic sugar for React.createElement(/*args*/)
Using JSX with React is optional.

###### components and elements

React components accept arbitrary inputs as `prop`s and return react elements.
Elements are either components or native DOM tags.
Typcially, the ⟮top-most⟯ react component is called ⟮App⟯
React components are UpperCamelCase'd

####### attributes of components

######## props

all attributes that a react component recieves are gathered together and passed to the render logic as `props`

######## state

state is by default encapsulated in a component.
Passing state down is passing state to a child via props.

####### implementation

Components can be implemented via functions + hooks or classes.
function components = components implemented with a function
class components = components implemented with a class.
The thing implementing the render logic is the function for function components, and the render method for class components.
The thing implementing the render logic of a component must be a pure function, side effects may only be performed in the class methods or relevant hooks.
the thing implementing the render logic recieves props.
to make a component hide itself, return null from tthe render logic.

react class components always extend React.Component. 
in the render() method of class components, you access most things via `this`

the function implementing a function component takes props as a parameter
For anything besides rendering based on props, react function components require hooks

table:action|function|class
referring to props|props (is parameter)|this.props
referring to state||this.state

###### the tree

React maintains a component tree called »the virtual DOM«, which is an in-memory JS representation.
Because React maintains the virtual DOM as an in-memory JS representation, creating react elements is far cheaper than browser DOM elements.
Eventhough react's component tree is called 'the virtual DOM', it can be outputted to many things, including but not limited to the DOM.
`ReactDOM` is an inteface to the output DOM.
ReactDOM.render(‹root-element›, ‹DOM-container›[, ‹callback›]) 
calling ReactDOM.render() is most commoly done to render the initial the virtual DOM into the output DOM once, where subsequent changes are handled by the render() method of components.

###### changes

The render logic of a given component is called when state or props change, initating the render phase.
Calling ReactDOM.render() also initiates the render phase for everything.
For any change, react has two phases (with a rare inbetween phase): Render phase, commit phase (and pre-commit phase)
The render phase is pure and has no side effects, may be paused aborted or restarted by react.
The render phase involves react calling a constructor for newly mounted components, and the render logic for any component.
The render logic of React components creates a tree of React elements.
In the commit phase, we figure out how to output the tree of React elements to the output (e.g. the DOM)
In an performance-unlimited word, react would just completely output the virtual DOM tree to the DOM.
Since performance is limited, react needds to figure out what has changed between the new and old virtual DOM trees and how to change the DOM based on that as little as possible, which is called »reconciliation«.
Since complete tree diffs are O(n^{3}), reconciliation uses certain heuristics.

####### component lifecycle

In react, a component may change in three lifecycles, mounting, updating and unmounting.
Mounting is outputting the virtual DOM representation of a component to its output representation (i.e. creating the output representation).
Updating is changing the component's state or props.
Unmounting is removing the virtual DOM representation of a component from its output representation (i.e. destroying the output representation).
For each stage in the component lifecycle, react has a method.
For the mounting and updating stages, the methods are called after the DOM representation has changed.
For the unmounting stage, the method is called before the DOM representation changes.

mounting|componentDidMount()
updating|componentDidUpdate()
unmounting|componentWillUnmount()

####### reconciliation

If react hits an element in its tree that has a different type (e.g. from ‹Article› to ‹Comment›), it will destroy (unmount) and rebuild (mount) the whole subtree.
when a DOM subtree is destroyed, all components of that subtree recieve `componentWillUnmount()`
when a DOM subtree is rebuilt, all components of that subtree recieve `componentDidMount()`

If react hits an element that has the same type, it will look at the attributes of both, kees the same underlying DOM node, and only updates the changed attributes.
When updating style, React also knows to update only the properties that changed. 
when a component's attribute change, it recieves `componentDidUpdate()`

```
‹div className="before" title="stuff" /›
‹div className="after" title="stuff" /›
```
```
‹div style={{color: 'red', fontWeight: 'bold'}} /›
‹div style={{color: 'green', fontWeight: 'bold'}} /›
```

However, if the DOM nodes are out of order compared to the last rerender, react is forced to assume that the children are different and destroy the subtrees.
To prevent a reorder of DOM nodes destroying the subtree, react offers the `key` property, where it can assume that elements with the same key property are the same.
`key`s should be stable over time, e.g. IDs or hashes of some description.
`key`s should not be abstracted into subcomponents, as react cannot use them for element identity assertions form there.

###### events

React wraps browser events in `SyntheticEvent`s, which generally have the same interface but prevent browser inconsistencies.
In react, you can't return false to prevent the browser default for an event, you actually have to call preventDefault

##### react native

⟮React Native⟯ is a ⟮framework⟯ for building native applications using ⟮React⟯ and ⟮the platforms native capabilities⟯
The most common targets for react native are android and iOS, but you can also target desktop OSs, qt, TVs and even the web.
You can use react native for your ⟮whole app⟯, but you can also ⟮integrate it into an existing project⟯
React Native implements a polyfill for WebSockets, initialized via importing React. Other modules using WebSockets therefore need to be imported after React.

###### components

Native Components: React Components transformed into native views
Core components: Native Components that are part of React Natives standard library
React Native|HTML
‹View›|a non-scrolling ‹div›
‹TextInput›|‹input type="text"›
‹Text›|‹p›
‹ScrollView›|a scrolling ‹div›
‹Image›|‹img›

‹TextInput› is a Core Component that allows the user to enter text.
onChangeText|event when text is changed
onSubmitEditing|event when text is submitted

flex-container:✫sm_2021-09-16--16-10-01-screenshot.png✫✫sm_2021-09-16--16-08-57-screenshot.png✫

A list with ⟮sections/headings⟯ should probably use the ⟮‹SectionList›⟯ component
A list with ⟮no sections/headings⟯ should probably use the ⟮‹FlatList›⟯ component

All the elements and views of a ScrollView are rendered, even if they are not currently shown
‹ScrollViews› can be configured to allow paging through views using swiping gestures by using the pagingEnabled props. 
The ‹ScrollView› Core Component can scroll in y-direction and, if `horizontal` is specified, in x-direction.
On iOS a ScrollView with a single item can be used to allow the user to zoom content. Set up the maximumZoomScale and minimumZoomScale props for that.

###### switching based on platform

Platform.version returns the os version (e.g. 10.1) on iOS and the API level on android
Platform.OS returns the current os
React Native supports two ways of generating plaform-specific code, the Platform module and platform-specific file extensions
to target React Native files specifically to android or to iOS, use the file extensions .android.js and .ios.js respectively
Platform.select takes an object with keys "ios", "android", "native", and "default", and runs the code contained in the relevant value
As far as I can see, for Platform.select "native" will trigger on native targets, while "default" will trigger on all targets, including web

### server

Web servers provide web pages.
CMS|Content Management System
SSR|Server-side Rendering
⟮Routing⟯ is relating ⟮paths⟯ to ⟮what should be shown⟯
while ⟮react⟯ is by default a ⟮client-side-rendered⟯ thing, using ⟮next.js⟯, ⟮gatsbyjs⟯ or ⟮other custom tools⟯, you can make it ⟮SSR⟯

#### JS

Node.js was created in 2009.
Node.js uses V8 as its JS engine/interpreter.
⟮Deno⟯ is a ⟮perhaps-sucessor⟯ to ⟮node⟯ by ⟮the same creator⟯.
⟮Deno⟯ is wrtten in ⟮rust⟯, provides native ⟮TS⟯ support, uses ⟮ES⟯ modules, and ⟮URLs⟯ for the location of dependencies

#### Python

Flask and Django are the most popular web frameworks for Python.

### both (Static generation / hybrid between CSR and SSR)

#### jekyll

Jekyll|Ruby
⟮Jekyll⟯ uses ⟮liquid⟯ as its ⟮template language⟯ 
You can write ⟮Jekyll⟯ pages in ⟮HTML⟯ or ⟮Markdown⟯ 
Jekyll pages/layouts/includes can have ⟮metadata⟯ associated with them, which is specified in ⟮the front matter⟯ 
⟮Front matter⟯ in Jekyll ⟮starts and ends⟯ with ⟮three dashes ---⟯ 
⟮Front matter⟯ in Jekyll is written in ⟮YAML⟯ 


for any page, the `⟮page⟯` assoc array contains ⟮the keys of that pages front matter⟯ 
the `⟮page⟯` assoc array is ⟮autopopulated with certain keys⟯ beyond ⟮the ones specified in the front matter⟯, amongst others the key ⟮`url`⟯ 

⟮Layouts⟯ ⟮wrap around⟯ your content. 
⟮Layouts⟯ are stored in the ⟮_layouts directory⟯. 
For a given post or other page, you specify ⟮which layout it's using⟯ by using ⟮the `layout` front matter key⟯. 
Layouts can ⟮inherit⟯ - you do this by ⟮referring to the parent layout⟯ ⟮within the child layout⟯ using ⟮the `layout` front matter key.⟯ 
Within a layout, ⟮`{{content⟯`}} refers to ⟮the content of the post using⟯ the layout, or ⟮the next-deeper child layout.⟯ 
As a convention, ⟮the root level layout⟯ is called ⟮default.html⟯. 
the `⟮layout⟯` assoc arr contains ⟮all metadata of the current layout⟯. 
⟮`layout.foo`⟯ allows you to ⟮access key foo of layout front matter⟯ 


⟮Includes⟯ are basically ⟮components⟯, you can ⟮refer to and include from anywhere you like⟯. 
⟮Includes⟯ are stored in ⟮the _includes directory.⟯ 
⟮Includes⟯ may take ⟮arguments⟯ as ⟮key=value⟯. 
Within an include⟮, a parameter foo⟯ is referred to as `⟮include.foo⟯` 
Include syntax: `⟮{%⟯ ⟮include⟯ ⟮include-name.html⟯ ⟮%}⟯` 

the `⟮site⟯` assoc arr contains ⟮all global data⟯. 

Syntax for jekyll ⟮post⟯ ⟮file names⟯: ⟮YYYY-MM-DD⟯⟮-title⟯⟮.extension⟯ 
Jekyll will ⟮auto-generate⟯ ⟮a `post.title`⟯ from ⟮the URL = file name⟯ if not specified 
Jekyll will ⟮auto generate⟯ ⟮a `post.excerpt`⟯ from ⟮the first paragraph⟯ if not specified 
⟮Posts⟯ are specified in ⟮./_posts⟯ 
`⟮site.posts⟯` contains ⟮an array⟯ of ⟮all the posts in ./_posts⟯ 


Jekylls supports keeping data stored in ⟮./_data⟯ for ⟮global use⟯ 
Jekyll ⟮data files⟯ may be specified in ⟮yaml, json::2 similar ones⟯, ⟮csv or tsv::2 similar ones⟯. 
Jekyll ⟮data files⟯ can be accessed via ⟮`site.data.filename` (no extension⟯) 
Jekyll supports keeping ⟮small mini-posts⟯ in so-called ⟮collections⟯. 
⟮Any directory in the root folder⟯ ⟮starting with _⟯, but not ⟮being one of the predefined directory names (such as _data, _posts⟯) is considered ⟮a collection⟯ of ⟮the same name⟯. 
Jekyll supports ⟮designating a directory for collections⟯ instead o⟮f specifying them in the project root in the config⟯, but this must then ⟮also contain _drafts and _posts, if extant⟯. 
Besides ⟮creating a directory⟯, ⟮collections⟯ must also be ⟮referenced in the collections array in the config⟯. 
⟮collections⟯ are ⟮arrays⟯ available via ⟮the `site.collectionname` propert⟯y 


##### themes

Jekyll ⟮themes⟯ are often ⟮gems⟯. 
By default, if you use a ⟮gem theme⟯, ⟮some of the directories of your site⟯ are ⟮in the gem itself⟯. 
If you want to ⟮edit things⟯ ⟮in gem themes⟯, you need to ⟮copy then out of the gem itself⟯, and ⟮reference the gem's dependencies in your gemfile/config⟯. 

##### plugins

⟮Jekyll plugins⟯ are specified within ⟮the _config.yml⟯ and within ⟮the gemfile⟯. 
In the ⟮gemfile⟯, ⟮jekyll_plugin⟯s are specified within ⟮the `group :jekyll_plugins`⟯ 


Jekyll Plugins2§
⟮jekyll-feed⟯|⟮Generating an RSS feed (jekyll⟯)
⟮jekyll-seo-tag⟯|⟮Generating a few SEO tags (jekyll⟯)
⟮jekyll-sitemap⟯|⟮Generating a sitemap⟯
⟮jekyll-paginate⟯|⟮allow pagination⟯


##### config
⟮defaults⟯|⟮default front matter⟯
⟮paginate: n⟯|⟮paginate with n pages⟯



#### next.js

##### unsorted

{{c1::next/head}} contains a component for {{c2::appending things to the &lt;head&gt;}}.

{{c1::getStaticProps}} and {{c1::getStaticPaths}} claim to only run {{c2::during build time}}, but {{c3::actually also can run during runtime}} if using {{c4::Incremental Static Regeneration}}

{{c1::getStaticProps}} and {{c1::getServerSideProps}} will both pass the value {{c4::in the props key}} of {{c5::the return value}} to the {{c2::react component}} {{c3::defining the page}}

{{c1::Next.js}} is a {{c2::framework}} for {{c3::react}}

to {{c1::add custom stylesheets}} you <code>{{c2::import}}</code> them in {{c3::pages/_app.js}} ({{c4::and only there!}}) {{c6::stylesheets from npm modules}} can be {{c2::imported}} {{c5::anywhere}}

to change how next.js {{c1::image optimization}} works, specify {{c2::{images:}} {{c3::{loader:}}

the three functions (which are all a{{c2::sync}}) for {{c1::fetching data}} in next.js are {{c3::getStaticProps}}, {{c4::getStaticPaths}}, {{c5::getServerSideProps}}

the getStatic/ServersSide... functions have {{c1::TS types}} that are {{c2::the same but capitalized (UpperCamelCase)}}

create-next-app supports using {{c1::typescript}} with the {{c2::--ts}}/{{c2::--typescript}} flag

What's the benefit of specifying layouts for individual pages, instead of just also returning this from the main component? <span class="divider">-&gt;</span> {{c1::react will be able to tell what changed and thus enable more SPA-like operation}}

The functions for getting data, getServerSideProps/getStaticPaths/getStaticProps are functions that are {{c1::written}} and {{c2::exported}} by {{c3::you}} for {{c4::any page that needs them}}

Nextjs supports {{c2::modern browsers}} + {{c1::IE11}} by default

Next.js {{c1::auto-optimizes your images}} if you specify them using the {{c2::<code>Image</code> component}}&nbsp;in {{c3::next/image}}
<div class="c1-f">
What would we have to do to use this?
</div><br><pre><code>&lt;Image
  src="/me.png"
  alt="Picture of the author"
  width={500}
  height={500}
/&gt;
</code></pre> <span class="divider">-&gt;</span> {{c1::<pre><code>import Image from 'next/image'
</code></pre>}}
<div class="c1-f">
What is the advantage of specifying images like this in next.js?
</div><br><pre><code>&lt;Image
  src="/me.png"
  alt="Picture of the author"
  width={500}
  height={500}
/&gt;
</code></pre> <span class="divider">-&gt;</span> {{c1::uses built-in compression, lazy-loading etc}}
<div class="c1-f">
Allows us to do what?
</div><br><pre><code>module.exports = {
  images: {
    domains: ['example.com'],
  },
}</code></pre> <span class="divider">-&gt;</span> {{c1::use next.js image component with external images}}
(next.js) For production, it is recommended that you install the npm package <code>{{c1::sharp}}</code> for {{c2::<code>Image</code> component minification}}

Next.js itself is built on top of {{c1::node.js}}

Next.js auto {{c2::inlines}} {{c1::font}} css

In next.js, any {{c1::react component}} {{c3::exported}} from a {{c2::.js}}({{c2::x}}) or {{c2::.ts}}({{c2::x}}) file in {{c4::the pages directory}} is {{c5::a page}}

If you want to have {{c5::different layouts}} for {{c5::different pages}}, you need to attach a <code>{{c1::getLayout}}</code> {{c1::method}} to the {{c2::function implementing your page}}, which takes an argument of {{c3::the page}}, and returns {{c4::the page with whatever modifications}}.

If you want to have some stuff that every page of your next.js website will have, what should you do? <span class="divider">-&gt;</span> {{c1::override the global App component}}

Define a layout for this page specifically<br><pre><code>//... imports
export default function Page() {
  //...
{{c1::Page}}.getLayout = function(page) {
  return // {page} surrounded by some other stuff
</code></pre>
Define a layout for this page specifically<br><pre><code>//... imports
export default function Page() {
  //...
Page.{{c1::getLayout}} = function(page) {
  return // {page} surrounded by some other stuff
</code></pre>
Define a layout for this page specifically<br><pre><code>//... imports
export default function Page() {
  //...
Page.getLayout = function(page) {
  return // {{c1::{page} surrounded by some other stuff}}
</code></pre>

Converting {{c2::static HTML websites}} (either from {{c2::SSR}} or {{c2::statically generated}}) into {{c3::dynamic web pages}} via {{c4::client-side JS}} is known as {{c1::hydration}}.

By default, {{c1::next.js}} {{c2::pre-renders}} ({{c2::generates the HTML of in advance}}) {{c3::every page}}

By default, what decides the route of a next.js page? <span class="divider">-&gt;</span> {{c1::the filename}}

By default, next.js only allows images {{c1::in the project itself}} to be used {{c2::for the Image component}}, if you want to use others, specify the {{c3::domain}} in {{c4::{images:}} {{c5::{domains:}} [...

Both {{c1::getServerSideProps}} and {{c1::getStaticProps}} return a {{c2::props object}} that {{c3::the react component}} implementing the page will recieve

Both {{c1::getServerSideProps}} and {{c1::getStaticProps}} recieve {{c2::a single argument}} <code>{{c3::context}}</code>

<div class="c1-f">
What will every page now have?
</div><br><pre><code>import Layout from '../components/layout'

export default function MyApp({ Component, pageProps }) {
  return (
    &lt;Layout&gt;
      &lt;Component {...pageProps} /&gt;
    &lt;/Layout&gt;
  )
}
</code></pre> <span class="divider">-&gt;</span> {{c1::the same global layout}}

<div class="c1-f">
What are we doing here?
</div><br><pre><code>//... imports
export default function Page() {
  //...
Page.getLayout = function(page) {
  return // {page} surrounded by some other stuff
</code></pre> <span class="divider">-&gt;</span> {{c1::defining a layout for this page specifically}}

<div class="c1-f">
For next.js, what will About become?
</div><br><pre><code>function About() {
  return &lt;div&gt;About&lt;/div&gt;
}

export default About</code></pre> <span class="divider">-&gt;</span> {{c1::a page}}

Each page is defined by a react component.

##### globals

The global component acts as a globabl template for all pages.
The global component is stored in `pages/_app.js`
For rare cases, there is a higer global template `Document`, which is only rendered on the server and does not support data fetching methods.
Overriding the global component is often doe to create global components, styles or state.
Stylesheets are imported by JS's `import` (as in webpack, which next.js uses in the background).
Stylesheets may only be imported from the global component.

##### layouts

Defining layouts for pages allows react to easily perform reconcilliation between the pages.

##### ways to serve content

Next.js allows you to mix and match static generation, SSR and CSR for each page.
Next.js distinguishes between static generation, SSR and CSR by how the components implementing the page will recieve props.
Next.js's »data fetching methods« are getStaticProps/getStaticPaths/getServerSideProps.
Next.js's data fetching methods are all async.
To use the data fetching methods, you need to `export` them


## IO

### shell environment

Modules which contain most of the environment stuff, though they may contain other stuff


rust
std::env|env ＆ argv
std::io|stdin, stdout, stderr and reading input lines
std::process|run a system command
no module (just std)|printing


python
sys|stdin, stdout, stderr, argv
os|env, run a system command
no module|printing


node
process|stdin, stdout, stderr, argv, env
console|printing
child_processes|run a system command


ruby
no module|stdin, stdout, stderr, argv, env, printing, run a system command 

#### stdin/stout

‹relevant-module-if-any›.stdin/stdout/stderr generally gets a streamlike io object referring to stdin/stdout/stderr

std::io::stdin/stdout/stderr|Rust (returns a handle of std::io::Stdin/Stdout/Stderr)

#### environment variables ＆ command-line arguments

argv = argument vector
Command-line arguments
@ARGV|Perl
process.argv|node
sys.argv|python
std::env::args()|Rust

Environment variables
%ENV|Perl
process.env|Node
os.environ|python
std::env::vars()|Rust

A signle environment variable
std::env::var(‹name›)|Rust

##### parsing

for any kind of involved CLI argument parsing in Rust, use `clap`.

#### print to ＆ read from console

Print functions in different languages
the JS console library works both in the browser and in node.js

print()|lua|perl (no final newline)|python|Ruby (no final newline)
say()|perl (final newline)
puts|Ruby (final newline)
console.log()|JS
@debug|SCSS/Sass
System.out.prinln()|Java
Console.WriteLine|C#
echo|liquid (within liquid block)|(ba)sh
println!|Rust

echo options
-n|no trailing newline

Print functions using C format strings
printf|(ba)sh, but it doesn't take format strings any more than echo|C (ofc)|Perl|Ruby
string.format|Lua
% syntax|Python

Print an error to console (but don't throw one)
console.error()|JS
@warn|SCSS/Sass
eprintln!|Rust

clear the console/terminal window
clear|sh
console.clear()|js
ø (no easy native solution)|python|ruby

console.count(foo)   count how many times a string foo has been printed

the sh printing commands all don't read from STDIN
besides taking more options, printf has exit codes other than 0 (echo always exits 0), echo adds a "\n" at the end while printf doesn't
printf options
-v foo|save the output in a variable foo

##### fancy printing

Command line output coloring: chalk (node)
CLI progress bar: progress (node)

##### fancy reading

inquirer.js   A collection of common interactive command line user interfaces. (node)

#### run commands in system shell

system()|ruby
‹system-module›.system()|python

#### exit status

process.exitCode|node

### file system

#### current working directory

process.cwd()|node
__dirname|Node

#### paths

module for working with paths
path|node

‹path-module›.resolve({‹items›})|glue passed things together into an absolute path (glues the path of the working directory onto the beginning if necessary)

### files ＆ streams

#### relevant modues

std::io, std::fs|Rust

#### non-stream based file interaction

Many programming languages feature utility functions to read an entire file to a string/write an entire file to a string, without having to use streamlike I/O.
The functions to instantly write a file typicallly take at least a path and the contents plus named arguments or an assoc arr for options.
The functions to instantly read a file take at least a path.
Most functions to read a file instantly, but not Rust, also take named arguments or an assoc arr for options.
the node async instant read/write file function also takes an error callback, as usual
readFile(Sync)/writeFile(Sync)|Node
std::fs::read_to_string|Rust

#### interaction

Once aquired, files and other streams such as stdin, stdout, stderr are often generalized in their functionality to a common interface, often called a stream, though sometimes called a file object.
Streams may be distinguished by if they support input, output, or both, or if they represent text, binary or something else (but not necessarily the case).
Streams often work similar to iterators, consuming input gradually.
Streams as the programming-centric I/O concept get their name and basic idea from the stream ADT.
Sometimes, instead of conceptualizing inputs as streams, programming languages instead conceptualize the way of consuming input streams, and thus call their interface for consuming streams `Reader` or similar.
For languages that have separate readers, getting the reader typically locks the stream to the given reader.

##### implementation of streamslike IO in different languages

Pythons streamlike I/O class/interface is `File`, even for things we wouldn't typically call files.
Ruby's streamlike I/O class/interface is `IO`.
Node's streamlike I/O class/interface is `Stream`.
In node, `Stream`s that can be read/written/both implement `Readable`/`Writable`/`Duplex`
JS has `ReadableStream` and `WritableStream` for streamlike I/O class/intefaces.
Rust doesn't have one class/struct for working with streams, but things that are readable implement the traits `Read` andor `BufRead`.
For some things, Rust only returns things implementing `Read` andor `BufRead` after calling `.lock()`
For files, rust's struct implementing `Read` is `File`.
JS returns the actual reader `ReadableStreamDefaultReader` after calling `.getReader()` on the stream, which locks the stream.

###### streamlike IO that can be read

read(‹integer›)|return next ‹integer› bytes/characters
read()|return whole file
readline()|return next line

Ruby doesn't support `readline()` for its streamlike object, but does support `readlines`, which returns all lines as an array.
Node doesn't support `readline()` on `Stream`, however it offers a whole library `Readline` to consume `Readable` `Stream`s line by line.

###### streamlike IO that can be written

write(‹content›)|write the content to the string

#### aquisiton and holding

##### not quite dispose

createReadStream/createWriteStream|node

##### dispose

The dispose pattern is a pattern for resource management.
In the dispose pattern, a resource is held by an object.
In the dispose pattern, a resource is typically aquired by calling a global function.
In the dispose pattern, a resource is used by calling methods on it.
In the dispose pattern, a resource is released by calling a method on the object.
The dispose pattern is common for interacting with files, in which case the resource is a file handle.

###### aquisition

to aquire files for the dispose pattern, most languages use a open() function, taking the path and returning a streamlike io thing.
Most languages have a positional or named parameter for `open()` allowing the specification of the encoding.

####### mode letters

Established by *nix/C, many functions to open/create new files/file handles across languages take a certain set of letters with certain meanings

r|read
w|create/clobber (eqiv to › in shell)
x|try create and fail if exists
a|create/append (equiv to ›› in shell)

###### releasing

‹resource›.close()|release the file handle

###### language constructs

some languages have language constructs for the dispose pattern: 
with|Python
using|C#
Languages that have language constructs for the dispose pattern typically require the things they act on to implement a certain inteface with methods for aquiring and releasing the resources, which will then be called automatically.
The language constructs for the dispose pattern typically assign the resource to a local variable.
The language constructs for the dispose pattern typically only execute their code if the resource could be successfully aquired.
In python, the interface for the dispose pattern is a context manager object, which must have __enter__ and __exit__ methods.
python-construct-for-dispose-pattern ::= with ‹context-manager› as ‹variable-name›:
c#-construct-for-dispose-pattern ::= using(‹type› ‹variable-name› = ‹thing-implementing-IDisposable›){...

## fancy IO

### visual

#### UI

widget tookit   library for creating UIs
gtk   GNU widget toolkit
qt (read cute)   cross-platform widget toolkit

#### Data visualization

d3 is a JS library for mainipulating/visualizing data

### web 

table:span=2;web IO library
requests|python|requests only
ureq|Rust|requests only
`http`/`https`|node|requests ＆ server=responses
none|native js|requests only
axios|node ＆ native js|requests (promise-based)

#### requests

table:span=2;requests
‹request-library›.get()|GET request|python, node
‹request-librar›.request()|any request|python, node
fetch()|any request|native JS

Most web request libraries take an object of type `Request` as an argument.
Node instead gets a OutgoingMessage object, which is also the same object the callback to createServer sends.
Most web request libraries return an object of type `Response`.
Node instead returns a IncomingMessage object, which is also the same object the callback to createServer gets.
Most async web request libraries return a promise or equivalent which resolves to a `Response`, or else take a callback that recieves a `Response`


‹reqres-object›.headers|HTTP headers|node, js, python
‹response-object›.url|url of request or final url of document|js, python, node


‹request-object›


‹response-object›.status_code/statusCode|HTTP status code|python, node
‹response-object›.status|HTTP status code|js
‹response-object›.reason|HTTP status message|python
‹response-object›.statusText|HTTP status message|js
‹response-object›.statusMessage|HTTP status message|node
‹response-object›.ok|is success status code (200-299)|js, python
‹response-object›.content|Returned thing as binary|python
‹response-object›.encoding|Page encoding|python
‹response-object›.text|Returned unicode text|python
‹response-object›.body|Returned body as stream|js


If the response object is going to be sent, as e.g. in node, it supports additional methods/fields:


‹response-object›.setHeader(‹key›, ‹val›)|set HTTP header to value
‹response-object›.end()|finish the message


##### XHR

XHR|XMLHttpRequest
Ajax|Asynchronous JavaScript And XML

##### fetch

the Fetch API features fetch() as its main method 
The Fetch API is the new, modern method to fetch data via the interfet after a site has loaded.
fetch(‹resource-to-get›, [‹options-object›])
fetch() returns a Promise which itself resoves to a `Response`
Response
.json()|return promise with contents of response as parsed json

Node doesn't have the Fetch API natively, but you can install it via a package, and Next.js polyfills it automatically

#### sending responses

to send a response to requests, you generally first need to create a server

table:span=2;method to create new servers
‹server-library›.createServer|create new server

createServer takes a callback to then respondd to requests

## scientific computing

pandas|python

## performance monitoring

time|measure elapsed time in executing a command|sh
console.time(), console.timeLog() ＆ console.timeEnd()|measure elapsed time in running code.

## dates

most languages have a date object (or multiple different ones) that allows convenient manipulation of datetimes

### js

In js, ⟮Unix time⟯ is almost always interacted with in ⟮milliseconds⟯, 
as opposed seconds, which is more standard
the `⟮Date.parse()⟯` method takes ⟮a date in a few common formats⟯ and outputs ⟮Unix time (in millis, as is common in JS)⟯
`⟮new Date()⟯` takes ⟮Unix time milliseconds⟯ and returns ⟮a `Date`⟯
`⟮someDate.toISOString()⟯ ` returns the datetime ⟮as ISO 8601⟯

### rust

In rust, the most featureful library to use to interact with dates is chrono.
chrono has `Date` and `DateTime` to represents dates and datetimes, which both take a type parameter of the `TimeZone`.
chrono also has `NaiveDate`, `NaiveDateTime` and `NaiveTime` to represents dates, datetimes and times without timezone awareness.
In generaly chrono structs implement traits in such a way that you can use standard arithmetic operators for them.
In general, using arithmetic operations in chrono calls the underlying `checked_‹operation›_signed` method
chrono has three `TimeZone`s, `Utc`, `Local` and `FixedOffset`
`Local` or `Utc` (but not `FixedOffset`) :: `today()` or `now()` produce a new `Date` or `DateTime` with the speciied timezone.
Behavior of things that work ⟮like dates⟯ / ⟮like times⟯ is standartized in the ⟮traits⟯ ⟮Datelike⟯ and ⟮Timelike⟯
you can get ⟮the time components⟯ of ⟮Timelike⟯ using ⟮the length you want as a method⟯ (e.g. hours → ⟮sometimelike:​:hours()⟯)
you can get ⟮the date components⟯ of ⟮Datelike⟯ using ⟮the date component you want as a method⟯ (e.g. months → ⟮somedatelike:​:month()⟯)
chrono represents durations with `Duration`
for chrono `Duration`s there are a bunch of constructors for different amounts of time such as `::weeks()`, `::hours()` etc.
For rust, if you only need simple duration handling, chrono might be overkill, and the things in `std::time` might be more appropriate.
Weekdays in chrono are implemented by the enum chrono::Weekday and the variants( ::Mon,  ::Tue,...)

## internationalization

table|library/object|language
`Intl`|JS

### Intl

The `Intl` object contains a bunch of constructors for creating internationalized versions of different types of things (dates, numbers, plurals, lists).
Most `Intl` constructors take at least a locale or array of locales as well as an options object.
If a list of locales is specified, it is interpreted as a priority hierarchy.

#### locale specification

Using `Intl`, locales are specified according to BCP 47.
Locales for `Collator`, `NumberFormat` or `DateTimeFormat` may include additional specification in BCP extension format, however these same options can also be set in the options object.

#### objects

Any object created by the various constructors on `Intl` besides `Intl.Locale` feature a `resolvedOptions()` method which returns the computed options based on the extension part of the BCP locale specifier and the options object.
Many Intl-constructor's options objects take a key `style` which takes `narrow`, `short` and `long`.

##### format

All the Intl objects that end `Format` (e.g. `DateTimeFormat`, `NumberFormat`, ...) have a `format` method and a  `formatToParts` method.
`DateTimeFormat` and `NumberFormat` also have a range version of the `format` and formatToParts` methods.

###### parts

`WhateverFormat.‹whatever›()` returns a string, while `WhateverFormat.‹whatever›ToParts()` returns an array of the parts this would format to.
the array returned by `WhateverFormat.‹whatever›ToParts()` consists of objects with keys `type` and `value`

```
new Intl.NumberFormat('de-DE', {
  style: 'currency',
  currency: 'EUR'
}).format(3500);
// return value:
[
  { type: "integer",  value: "3"   },
  { type: "group",    value: "."   },
  { type: "integer",  value: "500" },
  { type: "decimal",  value: ","   },
  { type: "fraction", value: "00"  },
  { type: "literal",  value: " "   },
  { type: "currency", value: "€"   }
]
```

###### to range

`WhateverFormat.format[ToParts]()` takes one argument and returns a simple return value
`WhateverFormat.formatRange[ToParts]()` takes two arguments and returns a range of whatevers (e.g. separated by a hyphen)

##### collator

A `Intl.Collator` is there to allow comparison and thus string ordering on a language-sensitive basis.
`Collator.compare` uses the same interface as the callback `Array.sort`.

##### locale

`Intl.Locale` grants an easy interface to return the parts of the BCP string that defined the locale, as well as some other information about how that locale does things.

##### datetimeformat

An `Intl.DateTimeFormat` has four methods to format specific dates.
the methods of `DateTimeFormat` take (a) `Date`(s) and return strings.

##### displaynames

`Intl.DisplayNames` is for the translation of the names of certain things (countries, currencies, languages, ...) into the names they have in the specific locale.
the options object for `DisplayNames` includes the keys (besides the global keys for Intl)`type`, `languageDisplay`, and `fallback`.

`type` for  the `Intl.DisplayNames()` constructor takes values such as `currency`, `language`, region, ...
The main method a `DisplayNames` object has is `of()`, which takes a unique identifier for the relevant `type`

```
new Intl.DisplayNames(['ja'], { type: 'region', style: "narrow" }).of("US"); // アメリカ
new Intl.DisplayNames(['ja'], { type: 'region', style: "long" }).of("US"); // アメリカ合衆国
new Intl.DisplayNames(['de'], { type: 'currency', style: "long" }).of("USD") // US-Dollar
```

##### listformat

`Intl.ListFormat` is for creating readable lists of arrays
`type` for  the `Intl.ListFormat()` constructor takes a value `conjunction`, `disjunction` or `unit`.

##### numberformat

`Intl.NumberFormat` is for formatting numbers.
The `NumberFormat` constructor options object takes about a bajillion options specifying things like notation, sign, sigfigs, units, currencies, separators, rounding etc. in excruciating detail.
The `format` methods of `NumberFormat` take numbers and return strings.

##### relativetimeformat

`Intl.RelativeTimeFormat` allows formatting of relative time (i.e. tomorrow, in 27 minutes)
the `format` methods take two arguments, a number value and a `unit`, which is something like year, mont, week, day...

##### segmenter

`Intl.Segmenter` is a locale-sensitive segmenter (instead of something like `split()`) 
The `Segmenter` constructor options object takes `granularity`, which can take the values `grapheme`, `word`, or `sentence`.
A `Segmenter` is applied by calling `segment` with the string to be segmented.

## Standard library

A software solution that has everything that it needs to run out of the box is said to be batteries included.
A programming language that has a large standard library is said to be batteries included.

the standard library is often indicated by fs

get list of all functions a module/package supports
dir(foo)|Python

get the smallest/largest of an amount of arguments
min()/max()|Python (also accepts an iterable as an argument)
Math.min()/Math.max()|JS

Get documentation information on the thing
help(foo)|Python

Show an output popup
window.alert("mesg")

### Modules/Objects/Namespaces

Filesystem handling
fs|node|Rust

### Query for input

Generally, show a message, have a text input field, return the inputted text.

input(mesg)|Python
window.prompt(mesg, default)

## other libraries

### utility libraries

An utility library is a library that adds a bunch of syntactic sugar methods for doing things.
in JS, there is the tradition of importing the main utility library as `_`.
As of 2021 the main js utility is lodash, before that it was underscore.

### presentations

complexity|write in|name|converts to
fancy|js|reveal.js
simple|md|remarkjs
simple|own markdown syntax|pandoc|5 html-based formats incl. reveal.js, latex beamer, ms powerpoint, pdf


# programming language categorization ＆ history

## names

Name|Prononciation
⟮C#⟯|⟮C sharp⟯


thing|slang
⟮Rust users⟯|⟮rustaceans⟯


## Programming paradigms

Functional programming languages: {Haskell}

## Programming languages I don't know

COBOL is a programming language introduced in 1959 with an englisy-like syntax that is as of 2021 mainly used on ⟮legacy mainframe computers⟯
C was created in 1972.
*nix OSs are famously written in C.
tcl is a programming language where everything is a command.
tcl has a well-known widgeting toolkit known as tk.
wish is a tcl interpreter including its widgeting toolkit tk.

## programming language relationships

### versions over time

Python ⟮2⟯ and ⟮3⟯ have ⟮some syntactic differences.⟯ 
ES2015|ES6
The rust development cycle has the three release channels ⟮Nightly⟯, ⟮Beta⟯ and ⟮Stable::S...⟯. ⟮sb;⟮Every six weeks⟯ ( = ⟮1 cycle⟯), ⟮c+; a release moves up one (beta → stable, nightly → beta) ⟯. ⟯ 
Therefore, ⟮s10:12;⟮what is beta now⟯ will be ⟮stable⟯ in ⟮a maximum of 6 weeks⟯⟯, and ⟮s7:9;⟮what is nightly now⟯ will be ⟮stable⟯ in ⟮at most 12 weeks⟯.⟯ 
⟮Breaking changes (such as reserving new features⟯) can only happen on ⟮the highest rust versioning level⟯, which are ⟮editions⟯. ⟮sb;these are released ⟮about every three years⟯, with the ones in existence as of writing being ⟮2015, 2018, and 2021⟯⟯ 

### dialects, influence, etc.

#### ECMA

JS = Javascript
ES = ECMAScript
JavaScript is a dialect/language that coforms to of the ECMAScript standard
others languages that conform to the ECMAScript standard are ActionScript / JScript. 
However, this distincition is often not made, and JavaScript and ECMAScript are often treated as synonyms. 
CoffeeScript is similar to and compiles down to JavaScript, but has more syntactic sugar/cleaner syntax.
TypeScript is a superset of javascript.

## Things programming languages do especially well

performance|rust

## language governance

After being dropped by mozilla, the rust foundation has taken over the governance of Rust (as of 2021)
The rust foundation is made up of major industry players like microsoft, google, huawei, mozilla.

# CompSci

# abstraction

abstraction is hiding implementation details in favor of a clear, semantic and elegant interface.
A high-level programming language is a programming language with high levels of abstraction.
A low-level programming language is a programming language with low levels of abstraction.
Often, abstraction has runtime overhead/costs.
Zero-cost abstractions are abstractions that have no runtime, only compile-time overhead.
Rust touts that it has many zero-cost abstractions.

# concurrency

Concurrency is executing multiple things at the same time.

## multithreading

A thread is the smallest sequence of instructions that can be independently managed by a scheduler.
Threads can be divided into kernel and green/virtual/user threads.
green thread = virtual thread = user thread.
kernel threads are those managed by the kernel to be scheduled for some CPU time.
user threads are those threads managed by a user process.
N:1 Threading   all threads of the program map onto one kernel thread
M:N Threading   some amount of threads of the program corresponds to some amount of threads of the os/kernel 
1:1 Threading   1 thread of the program corresponds to 1 thread of the os/kernel

### thread pools

A thread pool is a group of pre-instantiated, idle threads which stand ready to be given work. These are preferred over instantiating new threads for each task when there is a large number of short tasks to be done rather than a small number of long ones. This prevents having to incur the overhead of creating a thread a large number of times.
A thread pool typically processes a queue of tasks waiting for processing.

### workers

Web Workers are threadlike things in JS.
Web Workers come in two flavors, dedicated workers and shared workers.
While a ⟮dedicated worker⟯ is accessible from ⟮a single script only⟯, a ⟮shared worker⟯ is accessible from ⟮multiple scripts⟯, even if ⟮within different windows or frames⟯
Because many JS APIs are not ⟮threadsafe⟯, ⟮Web Workers⟯ have access to ⟮ only a limited subset⟯

Web Workers are created by using the Worker/SharedWorker constructor taking the JS file that implements the worker.
Web Workers as well as the main thread communicate via message passing.
For Web Workers, messages are sent by using the method postMessage and recieved via the message event.
For Web Workers, messages always send a copy of the data.
To handle events in Web Workers, use the error event.
To stop a Web Worker, call the terminate() method on it.

### thread-safety

Thread-safe code is code that will work even if many Threads are executing it simultaneously. 

## concurrency control

concurrency control ensures that correct results for concurrent operations are generated.
Mutual exclusion is the requirement in concurrency control that no thing may access the critical section while another thing is already accessing the critical section.
lock = mutex
A lock or mutex is a thing that enforces mutual exclusion.

## classic problems

### race condition

A race condition is the condition of a system where the behavior of a system depends on the sequence/timing of uncontrollable events.
A race condition is often a flaw that may cause bugs.

### deadlock

flex-container:✫1280px-Process_deadlock.svg.png✫✫220px-Gridlock.svg.png✫
A ⟮deadlock⟯ is a situation where ⟮each member of  a group⟯ is ⟮waiting on another member to do something⟯, and therefore ⟮the system is stuck⟯
⟮Gridlock⟯ is a specific type of ⟮deadlock⟯ that occurs ⟮in a street network⟯

# metaprogramming

metapgrogramming is programming that operates on other programs
An eval is a keyword/function/which executes a passed string as if it had been an expression in the language.
Using eval with data from an untrusted source is a huge security risk.
eval is a function in bash, JS, Perl, Python, Ruby. a similar function load is availabe in lua

## reflexion

reflective programming is metaprogramming where the program operates on itself
reflective programming is sometimes shortened to reflexion.

## macros

a macro is something that maps a input to a replacement output.
Rust supports macros as its main form of metaprogramming.
Rust macros end in an !.


# Programming language implementation

A programming language implementation is a system for executing computer programs written in a given programming language (s). 
There are two general approaches to programming language implementation: interpretation and compilation
While we might talk about ⟮programming languages⟯ being ⟮compiled or interpreted⟯, but actually it's ⟮the relevant implementation⟯ that is ⟮a compiler or an interpreter⟯.
A ⟮reference implementation⟯ is an ⟮implementation⟯ of a ⟮specification⟯ generally written by ⟮the creators⟯ of ⟮the API/programming language/whatever⟯ to be ⟮an example for other implementations⟯

TS compiles to JS via the compiler, interfaced with the cli tsc.

$Something that happens during execution   runtime $something
$Something that happens during compiling   compile-time $something

## Types

A compiler translates one programming language into another in one step before execution.
Most commonly, a compiler translates a programming language into machine code/assembler.
An interpreter translates the code into another language (most commonly machine code/assembler) as it goes along.
JIT = Just in time (compilation)
frequently when using JIT as a first step the code is compiled to bytecode
when using JIT, the code(/bytecode) is initially executed by an interpreter, but there is a monitor/profiler that constantly analyizes the code being executed and identifies parts of the code where the speedup gained from compilation or recompilation would outweigh the overhead of compiling that code, and then compiles this on the fly.

### Transpiling

Source-to-source translator/compiler    trans(com)piler
A transpiler compiles one (programming) language into another (programming) language, though the target language is generally not assemly.
A preprocessor most typically takes some input and transforms it into some output, often for further use of compilers.
While preprocessors generally don't transform the language, sometimes transpilers are called preprocessors, e.g. in the case of sass.

### compilers

Object code is the code that the compiler produces, generally machine code.
The object file is the file containing object code.


## Steps involved

1. lexical analiysis/tokenization/lexing
2. sytax analysis = parsing
3. semantic analysis

### lexical analysis

lexical analiysis = tokenization = lexing
Terminology around tokenization/lexical analysis is not always consistent.
Lexical analysis is converting a sequence of characteres into a sequence of lexical tokens.
Lexical tokens have some kind of meaning, relative to the language.
Lexical token is often shortened to just token
Tokens are lexical units/items in linguistic terms.
Tokens have a certain value (a string), and a certain type.
Token types that are common across programming languages are identifier, keywords, operator, literal ...
The analogue of token type in linguistics might be word class/syntactic category/part of speech
Compilers/interpeters store all the identifiers/symbols and info about them in the symbol table.
In the context of compiling/interpreting, identifier/name is a synonym for symbol.

### syntax analysis

### semantic analysis

### compiler optimizations

A compiler optmization is a feature of a compiler that tries to minimize or maximize some attributes of an executable computer program.
Optimization levels are compiler options specifying how much compiler optimizations to apply.
In the GCC C compiler and in Rust, there are four optimization levels, 0-3.
In rust, optimization levels are set via `opt-level'.

#### dead code

Dead code is code which is never or not usefully used.
Unreachable code is dead code which is dead because there is no control flow path that would lead to it.
Dead code elimination is a compiler optimization involving the removal of dead code.
In js, dead code elimination is kown as tree shaking.
unused variables are a type of dead code.
compilers and linters will typically warn about unused variables.
unused variables may be a code smell in that they are mistakenly not used.
in rust, to turn off warnings about unused variables for a certain variable, prefix it with a _.

#### call sites

A call site is the place where a callable unit is called.
Inlining is a compiler optimization that replaces a function call site with the body of the called function.

## interfaces for implementation

### Language CLI

most languages have a CLI tool to interface with them, esp. with implementations

interpreters/hybrid

lua|lua
node|JS (using node)
python, python3|python
perl|perl

compilers

sass|sass/scss
rustc|rust
tsc|ts

-c STRING|read program from string|python
-e STRING|read program from string|perl

by default, TS will ⟮compile⟯ even ⟮if there are compiler errors⟯, since it assumes ⟮you might have a good reason⟯, use --noEmitOnError to disable this.
by default, TS compiles down to ⟮ES3⟯, but you can change that with the ⟮--target⟯ flag

#### REPL

REPL is short for read-eval-print loop
⟮REPLs⟯ are also called ⟮interactive toplevel⟯ or ⟮language shell⟯

For most languages, invoking their CLI tool without arguments will open a REPL, if not
irb|ruby
tss-node|TS
is none|perl
jshell|java
csharp|C# (provided by mono)

Python calls being in the repl interactive mode
the value of the last expression
_|Python

### Shebangs

env (/usr/bin/env) can be passed a comand, in which case it will populate the environment variables (including PATH) and then run command with this environment. 
Using env in the shebang is to get the relevant executable on the path
so in general, you can specify the language of a script by doing 
#!/usr/bin/env language-command

## specific languages

### Python

CPython is the most common and reference implementation for Python.
CPython implicitly compiles Python to bytecode, and then runs the bytecode via an interpeter.
Python bytecode files produced by CPython are .pyc files.

### JS

JavaScript is run by a JavaScript engine (e.g. V8, SpiderMonkey), which may differ by browser.chromium|v8
firefox|spidermonkey
d8 is the developer shell for v8

## document start/end indicators

--- the file ... |YAML (but optional, merely allow multiple documents per file)

# algorithms

⟮An algorithm⟯ is a ⟮finite⟯ ⟮sequence⟯ (in the math sense) of ⟮steps⟯ that ⟮precisely defines an operation⟯. 

## pseudocode

⟮pseudocode⟯ is ⟮a plain-language description⟯ of ⟮an algorithm⟯. 
⟮Pseudocode⟯ generally ⟮uses (structural) conventions of⟯ ⟮programming languages⟯, but not ⟮specific syntax⟯. 

```lang=text;
When a button is pressed:
  Get some memory, which will be used to remember the floor number
  Put the floor number into the memory
  Are we already on the target floor?
    If so, we have nothing to do: finished
    Otherwise:
      Wait until the lift is idle
      Go to the required floor
      Release the memory we used to remember the floor number
```

## properties

### determinism

a deterministic algorithim/callable unit will, given a particular input ⟮always produce the same output⟯

## for

### search

#### binary


flex-container:✫sm_1280px-Binary_Search_Depiction.svg.png✫
⟮Binary search⟯ 
```
⟮take middle element⟯ 
⟮if equal, done⟯ 
⟮else take relevant half and repeat⟯ 
``` 
⟮binary search⟯ has a ⟮worst-case time complexity⟯ of ⟮O(log n⟯) 
⟮Binary⟯ search can only be done on something that is ⟮sorted⟯. 

### sorting

A sorting algorithm is an algorithm that sorts a linear collection.

#### bubble


flex-container:✫sm_Bubble-sort-example-300px.gif✫
Bubble sort is called that because the largest elements will bubble to the right in a single pass.
while true:
  for all elements in the list: 
    if currentElement › nextElement, swap them
  if no swap occurred in the loop, stop.

## complexity

Computational complexity is the amount of resources necessary to run an algorithm.
Computational complexity assumes the amount of resources to perform each operation are similar / average out.
there are two types of computational complexity commonly used, depending on the case: worst-case and average-case.
In general, if we only say 'complexity', worst case complexity is assumed.
there are two types of computational complexity commonly used, depending on the resource: time and space
Computational complexity is generally specified in Big O notation.
Computational complexity is generally specified as a function of the input size n.
Computational complexity/Big O notation only indicates orders of magnitude.

O(1)   constant complexity/time|Accessing an element in an array
O(n)   linear complexity/time|Iteratering over a one-dimensional array
O(log n)   logarithmic time
O(n⎴2⎴)   quadratic time

## static program analysis

static program analysis is reasoning about/analyzing the behavior of computer programs without actually running them
Linting is probably the most common form of static program analysis.

# information theory

## symbol rate

baud   Bd
baud   symbol rate (AKA baud rate, modulation rate)
symbol rate   symbol changes per second

# coding theory

The Hamming weight of a string is the number of symbols that are different from the zero-symbol (of the alphabet used).
This means that the hammming weight of a binary number is its digit sum. 
The hamming weight of 11101 is 4, the hamming weight of 60801 is 3

# AI

## Computer vision

⟮Computer vision (CV)⟯ is a field of study that aims to get ⟮artificial systems / AI⟯ to get ⟮meaningful information / understanding⟯ from ⟮digital images/videos/whatever⟯.

### depth

⟮Stereopsis}/{{c2::stereo(scopic) vision⟯ is ⟮the ability to percieve depth⟯ from ⟮only two eyes/optical sensors⟯.
binocular disparity is the difference between the images that the optical sensors involved in stereopsis recieve due to them being positioned somewhat apart.
stereo matching is matching the two images produced by stereopsis.
After stereo matching, one can calculate the distance via trangulation.
stereo matching is more difficult (esp. for computer sensors) if the thing is featureless (since it then has a harder time matching the relevant pixels)
To improve stereo matching on featureless things, a device intended for depth calculation via stereopsis often will project a IR dot pattern, which is a pseudorandom but known pattern of dots in the infrared spectrum, which it then can use as the things to match.

### triangulation

⟮Triangulation⟯ in surveying / computer vision / etc. is ⟮determining the location⟯ of ⟮a point C⟯ from ⟮two points A and B⟯ by ⟮forming a triangle⟯.
By knowing the ⟮distance between A and B⟯ as well as ⟮the angles at A and B⟯, we can ⟮reconstruct the distance.⟯

## safety

### technological singularity

The technological singularity is a hypothetical point at which technological progress reaches critical mass and becomes uncontrollable, causing severe but unpredictable changes.
Most commonly, the technological singularity is cashed out in terms of a intelligence explosion.
An intelligence explosion posits that there willl be a runaway reaction of self-improvement cycles of an AI, thereby bringing about the technological singularity.

# software engineering

Software engineering is term where the definition is often fought over.
Software engineering (roughly) is different from software development/programming in that it emphasizes a more holistic view including tools and processes used for development, and temporally not just the time writing code, but the time before and after too.

# software design

## decomposition

Decomposition is breaking down the problem into smaller parts.

## software architecture

Software architecture refers to the fundamental structures of software/development and creating those structures.

### properties

#### coupling ＆ cohesion

https://upload.wikimedia.org/wikipedia/commons/0/09/CouplingVsCohesion.svg
cohesion is the degree to which the elements inside a module belong together.
coupling is the degree of interdependence between software modules.
In general, cohesion is good and coupling is bad.
high coupling generally implies loose cohesion and v.v. 

A god object is an object that violates the single-responsibility principle by knowing too much or doing too much.
The single-responsibility priinciple states that (the implementation of) a thing should only change for one reason.

### solution stack

A software/solution stack is the set of technologies that are layered/combined to run something (most often an application)
A developer than can work with all layers in a solution stack is a full-stack developer

ME?N = MongoDB, Express.js, ?, Node.js
MEAN includes Angular
MERN includes React
MEVN includes Vue.js

### design patterns

#### MVC

MVC = Model View Controller

        ┌─────────────┐
      ┌─┤    Model    │◄┐
      │ └─────────────┘ │
  Updates           Manipulates
      ▼                 │
┌─────────────┐ ┌───────┴─────┐
│    View     │ │ Controller  │
└──────┬──────┘ └─────────────┘
       │              ▲
       │              │
     Sees           Uses
       │   ┌──────┐   │
       └──►│ User ├───┘
           └──────┘

# development practices

Rubber-duck debugging is problem-solving by explaining it out loud to an object or naive human.
functional requirement|function (relation between input and output)|system must do x
non-functional requirement|criteria of judgement, not specific behavior|system shall be x

## development paradigms

### Agile

#### lean

##### kanban

Kanban board tools: trello, github projects

### Scrum

## CI/CD2

### CI

CI|Continuous Integration

Before CI, integration would only happen once every few weeks or months
Continuous Integration is a software development practice where members of a team integrate their work frequently, at least once a day
The two main goals of CI are to reduce the pain of any integration, and to be able to deliver a product version at any moment

If a build failure happens in CI, the build should be fixed before work continues.

### CD2

CD|Continuous delivery OR deployment

continuous delivery|software can be deployed on any commit
continuous deployment|software is deployed on any commit
⟮Continous deployment⟯ ⟮relies on⟯ ⟮continous delivery⟯
A nightly build is one that is built every night, generally automatically

### pipelines

CI/CD requires certain steps such as testing to happen on any integration.
A CI/CD pipeline specifies the set of steps to happen on each integration.
The most common tools to implement a CD/CI pipeline are Jenkins, CircleCI, Travis CI or github actions.

#### GH Actions

##### filess

stuff for github actions is stored in a .github directory.

##### basic structure

A workflow is triggered by an event.
A workflow consists of one or more jobs.
jobs can run in sequential order or in parallel.
Thus, jobs can relate to each other in complex ways as dependencies.
Each job runs in its own runner.
A job consists of one or more steps.
Steps either run a script or an action.
An action is a reusable building block.

###### workflows

A workflow is defined by a YAML file.
Your repository can have as many workflows as you like.

###### events

Events are certain actins taken on the repo.
Besides by events in the narrow sense, workflows can also run on a schedule, by POSTing to a REST API, or manually.

###### jobs

You can share data between steps of a job.

###### actions

The repository for actions is the github marketplace.

###### runners

A runner is a VM.
You can use runners provided by GH, or host your own runners.
Github provides ubuntu, windows and macos runners.

###### artifacts

artifacts are files or collection of files.
artifacts allow persisting of data after a job has finished, either for use in a different job or as workflow output.
artifacts are uploaded/created via the actions/upload-artifact action
artifacts are downloaded/used via the actions/download-artifact action
artifacts are referred to for the purpose of using them via downloaders or as workflow output with a `name`
artifacts are uploaded by specifying their `path`
once artifacts have been downloaded by using their `name`, they are used by referring to their path.

###### expressions

Expressions are a mini-programming language within workflow files.
expressions must generally be surrounded in ${{}} unless in an if-key
Expressions use a syntax reminiscent of JS.
Expression tend to use functions, and not methods.

####### contexts

contexts contain information about something related to the repo or github actions.
Each context is an object with certain properties.
Pretty much any ＊thing＊ (e.g. job, step, runner, etc.) in the actionverse has its own context.
you refer to contexts as expressions.
many context properties also exist as corresponding environment variables.

##### workflow YAML syntax

###### toplevel

`name` specifies what to call the workflow
`on` takes a sequence of triggers for a workflow
`jobs` takes a mapping of jobs.

###### jobs

`run-on` specifies the runner you want
`steps` takes a sequence of steps.

###### if

a step may take the `if` key, which takes an expression to only conditionally execute this step.

success()|Returns true when none of the previous steps have failed or been canceled.
cancelled()|Returns true if the workflow was canceled.
failure()|Returns true when any previous step of a job fails.

###### steps

####### actions

######## uses

`uses` is used to specify an action to run for a step.
If the action is defined in the same repo, `uses` can take the path of the action.
If the action is not defined in the same repo, `uses` takes it as ‹owner›/‹repo›@‹ref›
If the action is defined in a container published on the docker hub, `uses` takes it as docker://‹image›:‹tag›

the @‹ref› part of referring to gh actions may be a tag, a commit SHA, or a branch.

######## with

the `with` key is used to provide arguments to the action.

####### CLI

`run` is used to specify a command to run for a step.
`run` can take a multiline string, of which it will then run all lines as commands sequentially
when using `run` for a step, `shell` specifies which shell to use (e.g. bash)

###### env

an `env` key contains key-value pairs that will be provided to the script as environment variables.
You can specify `env` on a workflow, job or step.

##### actions YAML syntax

the actions YAML file has the toplevel keys `inputs` and `outputs`, both taking mappings, to define the inputs and outputs.

##### GUI

You can view GH actions in the `actions` tab of the repository.

## code writing enviroments

Integrated development environment   IDE
An IDE is a software development tool that aims to include everything relevant to progragramming in a ceratin language.

The ⟮standard length⟯ of ⟮a line of code⟯ is ⟮80 characters⟯. 
⟮The standard length of a line of code being 80 characters⟯ originated ⟮with IBM punch cards⟯ in ⟮1928⟯, and later was ⟮the standard width of a terminal⟯ 
The default size in many cases for ⟮terminals⟯ is ⟮80 characters⟯ wide, and ⟮24/25 lines⟯ high

### code editor

A (source-)code editor is a text editor designed for writing source code.

#### keyboard shortcuts

##### vscode

rename a symbol|⟦f2⟧
see code actions (available refactorings and quick fixes)|⟦⌘⟧⟦.⟧
change (programming) language of current document|⟦⌘⟧⟦k⟧  ⟦m⟧
show integrated terminal|⟦⌃⟧ (even on mac) ⟦`⟧
fast scrolling|⟦⌥⟧ ⟦scroll⟧


Action|Shortcut
⟮Open IntelliSense⟯|⟮⟦⌃⟧ ⟦␣⟧⟯


####### lines

Shortcut|Action
⟮⟦⌃⟧ ⟦j⟧⟯|⟮join lines⟯
⟮⟦⌘⟧ ⟦⇧⟧ ⟦k⟧⟯|⟮delete line⟯
⟦⌘⟧ ⟦enter⟧|insert a line below
⟦⌘⟧ ⟦⇧⟧ ⟦enter⟧|insert a line above


when focused on a line but not selecting a word, ⟦⌘⟧ ⟦c⟧ and ⟦⌘⟧ ⟦x⟧ act on the line itself


copy line up/down|⟦⇧⟧ ⟦⌥⟧ ⟦up/down⟧
move line up/down|⟦⌥⟧ ⟦up/down⟧


indent/outent a line|⟦⌘⟧ ⟦]⟧/⟦[⟧


#### UI 

##### vscode elements

###### workspace

most of the time, a vscode window contains one vscode workspace.
A vscode workspace contains one (or more, with multi-root workspaces) open root directory(or -ies).
per-workspace items are placed in the root directory's .vscode directory
Opening a directory in vscode spawns a workspace with this directory as the root directory.
By default, UI state persists on a per-workspace basis.

####### multi-root workspaces

Multi-root workspaces are opened by opening a .code-workspace file.
A .code-workspace file is a JSON file that lists the folders of the workspace.


###### groups

In vscode, a editor group is a group of one or more open editors

split current editor into two editor groups|⟦⌘⟧ ⟦\⟧
switch to left/right editor group|⟦⌘⟧ ⟦k⟧ ⟦←/→⟧
move editor group left/right/up/down|⟦⌘⟧ ⟦k⟧ ⟦←/→/↑/↓⟧
close editor group|⟦⌘⟧ ⟦k⟧ ⟦w⟧

###### tabs

In vscode, by default a tab contains one editor.

move current editor tab left/right|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦⇧⟧ ⟦←/→⟧
switch to left/right tab|⟦⌘⟧ ⟦⌥⟧ ⟦←/→⟧
cycle through tabs|⟦⌃⟧ ⟦tab⟧
close all editors = tabs|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦w⟧

###### single editor

####### navigation

symbol chooser popup (shorter version for mode of command palette)|⟦⌘⟧ ⟦T⟧
go to line (shorter version for mode of command palette)|⟦⌃⟧ ⟦g⟧
go to symbol  (shorter version for mode of command palette)|⟦⌘⟧ ⟦⇧⟧ ⟦O⟧
go back in location history|⟦⌃⟧ ⟦-⟧
go forward in location history|⟦⌃⟧ ⟦⇧⟧ ⟦-⟧

####### region

in vscode, a region is a block of code you can collapse or expand (e.g. defined by a {} in curly brace languages)

fold/unfold current region|⟦⌥⟧ ⟦⌘⟧ ⟦[/]⟧
fold/unfold current regions recursively|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦[/]⟧
fold all regions|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦O⟧
unfold all regions|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦J⟧

####### editing a file

autoformat file|⟦⌘⟧ ⟦⌥⟧ ⟦f⟧

######## bookmarks

The vscode extension Numbered Bookmarks adds numbered bookmarks for lines which can be navigated to and from via keyboard shortcut

set numbered bookmark ‹n›|⟦⌘⟧ ⟦‹n›⟧
navigate to shift bookmark ‹n›|⟦⌘⟧ ⟦⇧⟧ ⟦‹n›⟧

####### search

######## search UI (box)

In vscode, one can resize the search widget by dragging its left edge.

######## modifying search behavior

######### limiting search to selection

⟦⌘⟧ ⟦⌥⟧ ⟦l⟧ creates an area search is limited to from the current selections.
a second press of ⟦⌘⟧ ⟦⌥⟧ ⟦l⟧ does not re-select, instead toggling off. One must first toggle it off, then select a new area, then toggle it back on to get a new selection.

######## aquiring ＆ navigating

######### aquiring

######### navigating 

######### hybrid

⟦⌘⟧ ⟦f3⟧ and ⟦⌘⟧ ⟦⇧⟧ ⟦f3⟧ set the word under the cursor as the search value.
⟦⌘⟧ ⟦f3⟧ and ⟦⌘⟧ ⟦⇧⟧ ⟦f3⟧ cycle forward/backward through the occurences of the word once it's been aquired
⟦⌘⟧ ⟦d⟧ uses the search widget to search for the word under the cursor, and adds a cursor for the first find match. every subsequent press adds a cursor to the next find match.
⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦d⟧ is just like ⟦⌘⟧ ⟦d⟧, except that it doesn't add more than one cursor

######## converting search to other things (e.g. selection)

######### converting search results to cursors

add cursors to all search results (if search field focused)|⟦⌥⟧ ⟦enter⟧

####### selection

######## aquiring/enlarging selections

######### by line

⟦⌘⟧ ⟦l⟧|select a line (multiple presses select more)

######### expand/contract

⟦⌘⟧ ⟦⇧⟧ ⟦⌃⟧ ⟦←/→⟧ will shrink/expand a selection by the next larger unit (word ↔ line ↔ region ↔ larger region ...)

######### selection anchors

a selection anchor is a cursor you set, which then can act as one side (anchor) of a selection later, or can be used to return to that position.
set selecton anchor at current position|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦b⟧
select from selection anchor to current position (deletes selection anchor)|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦k⟧
go to selection anchor|⟦⌘⟧ ⟦k⟧ ⟦b⟧
cancel selection anchor|⟦esc⟧

######### column/box

⟦⇧⟧ ⟦⌥⟧ ⟦drag⟧ starts selecting a rectangular area just like visual block mode, adding a cursor to the beginning/end.


######## using selections

autoformat selection|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦f⟧

####### comments

⟮add line comment⟯|⟮⟦⌘⟧ ⟦k⟧⟦⌘⟧ ⟦c⟧⟯
⟮toggle line comment⟯|⟮⟦⌘⟧ ⟦/⟧⟯
⟮toggle block comment⟯|⟮⟦⇧⟧ ⟦⌥⟧ ⟦a⟧⟯

####### vscode jupyter

⟮⟦f10⟧⟯|⟮execute next line of code⟯
⟮⟦⌃⟧ ⟦enter⟧⟯|⟮finish editing a cell/run a code block⟯


###### bars and panels

show/hide side panel|⟦⌘⟧ ⟦b⟧

####### bottom panel

show problems|⟦⌘⟧ ⟦⇧⟧ ⟦M⟧
open new terminal if terminal tab is focused|⟦⌃⟧ ⟦⇧⟧ ⟦5⟧
split terminal right|⟦⌘⟧ ⟦\⟧

##### increment/decrement via arrow keys

Arrow up/down plus..|Increments by... (assumes base 10)
⟮alt⟯|⟮0.1⟯
⟮ø⟯|⟮1⟯
⟮shift⟯|⟮10⟯
⟮command/ctrl⟯|⟮100+⟯

#### settings

##### scope

vscode settings can either be per-workspace or per-user (i.e. global).
The settings.json file lives in a plattform-dependent global location for per-user = global settings.
The settings.json lives in .vscode for per-workspace settings.

##### settings.json

vscode settings are set in a settings.json file.
vscode offers a GUI to set your settings, but this is just an interface for the settings.json.

###### syntax

Within the settings.json, settings that apply to all languages are toplevel keys.
For each language, there may be one "\[‹language-name›\]" toplevel key, which itself contains an object of settings for that language.
```
   "[typescript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
```

Generally, if you set the same key twice, the latter will be used, however objects will instead be merged.
While not nested, often keys are dotted to scope their settings, e.g. "workbench.colorTheme" or "redhat.telemetry.enable"

#### extensions

Extensions allow changing the functionality of a code editor.
In vscode, you can activate extensions globally or only for a workspace.

##### formatters

In vscode, code formatters are implemented as extensions.
In vscode, code formatters hook into existing apis which allow configuring of formatting.
To set the default formatter for any language, set the "editor.defaultFormatter" key within that language's settings object within the settings.json.

#### code snippets

code snippets feature in many different code editors 
code snippets are templates that are triggered by selecting it from code completion or typing the name and then tabbing.
vscode features some built in code snippets and allows both extensions and the user to define new ones.
vscode follows textmates syntax for defining user snippets.
vscode snippets all live in the `snippets/` directory
snippets for a given language are set in a ‹languagename›.json file.
global snippets are set in a whatever.code-snippets file.
user snippets for vscode are defined in a json file.
any top-level json object within the snippets file defines a snippet.


key|function
prefix|what triggers the snippet
body|what happens when the snipped is triggered
description|What details IntelliSense provides for the snippet


code snippets can contain tabstops, places where values can be filled in easily.
when defining a code snippet, plain tabstops look like $1, $2...
$0 as a tabstop defines the final cursor position.
the transform part of code snippets takes a regex in the usual slash-based form, though instead of the replace part it may also take specifiers like `upcase`, `downcase`, etc.
the choice specifier of code snippets specifies a choice similar to the shell syntax
```
snippet-tabstop-specifier ::= $(‹tabstop›|‹variable›)
tabstop ::= ‹integer›|\{‹integer›(‹complex-specifier›|‹choice›)\}
choice ::= \|‹string›{, ‹string›}\|
variable ::= ‹string›|\{‹string›‹complex-specifier›\}
complex-specifier ::= (:(‹snippet-tabstop-specifier›|‹string›)|‹transform›)
```
you can jump between tabstops with tabs.

# QA

QA = Quality assurance
QA are the activities done to make sure that the product meets certain standards.

⟮wave a dead chicken (over it)⟯: To perform a ritual over ⟮crashed software or hardware⟯ which one ⟮believes to be futile⟯ but is ⟮nonetheless obligatory so that others may be satisfied that an appropriate degree of effort has been expended.⟯

## debugging

### devtools (webkit)

#### elements tab

⟮press del⟯ in the dom view of devtools to ⟮delete the node⟯ 
⟮⟦⌘⟧ ⟦⌥⟧ ⟦click⟧⟯ one of those ⟮triangle arrows⟯ in devtools to ⟮expand/collapse all children⟯ 
⟮Expand and collapse⟯ DOM nodes in Chrome's devtools via the ⟮right and left arrow ⟯ keys. 
to ⟮search the DOM⟯ via ⟮string⟯, ⟮css selector⟯ or ⟮xpath selector⟯, ⟮ctrl/cmd+f⟯ in the DOM view in devtools 
to ⟮hide the DOM node you have focused⟯ in devtools, press ⟮h⟯ 
to edit the ⟮attributes⟯/⟮node type⟯ of a node while in devtools, press ⟮enter⟯ and then ⟮tab/shift tab around⟯ 
Chrome's devtools feature an ⟮element picker⟯, which can be toggled with ⟮⟦⌘⟧ ⟦⇧⟧ ⟦C⟧⟯ 
to have an ⟮element that you select in your devtools be visible in your browser window⟯, ⟮right-click⟯ and then ⟮click 「scroll into view」⟯ 
flex-container:✫FBb3y3CzDXA5P0sNEuyd.png✫


#### styles tab

⟮navigate through⟯ ⟮style declarations⟯ and ⟮selectors⟯ in the styles panel with ⟮tab/shift-tab⟯ 
⟮control-clicking⟯ a ⟮style declaration (e.g. margin: 0.5em⟯) in the styles panel devtools ⟮goes to the line where it was declared⟯ 
⟮shift-clicking⟯ ⟮the box next to a color⟯ in the styles panel devtools ⟮changes its color representation (RGB, HSLA, etc.⟯) 
flex-container:✫sm_2021-09-16--17-43-33-screenshot.jpg✫


#### elements+styles tab

You can ⟮force element state (such as hover, focus⟯) either by ⟮c+;right-clicking the DOM node › force state⟯ and then choosing the state, or by ⟮clicking the :hov button⟯ in the ⟮styles panel⟯ and choosing the state 

##### box model

flex-container:⟮h∞;✫sm_2021-09-16--18-04-22-screenshot.jpg✫✫sm_2021-09-16--18-03-06-screenshot.jpg✫⟯
Hovering over ⟮a part of the box model⟯ in the styles tab will ⟮higlight that relevant thing in the page⟯ 
Besides by normal CSS declaration, you can ⟮change any part⟯ of the CSS box model in devtools by ⟮clicking on the relevant number and setting it⟯ 

#### console

You can access ⟮the currently selected node in the elements inspector⟯ as ⟮$0⟯ in the console in devtools. 
If you ⟮c+;right-click › store as global variable⟯, the DOM element becomes available ⟮as temp1, temp2, etc.⟯ ⟮in the console⟯ 

#### other tabs/panels

Use the ⟮Media⟯ Panel in Chrome DevTools to view information and debug the ⟮media players⟯ per browser tab. 
The ⟮Issues⟯ tab in Chrome DevTools moves the ⟮issues messages⟯ that used to ⟮appear in the console⟯ into their own tab 
The ⟮Coverage⟯ tab in Chrome DevTools can ⟮help you find unused JavaScript and CSS code⟯. 
to use the ⟮Coverage⟯ / ⟮Network⟯ tab, click ⟮the record button⟯, then ⟮reload (or otherwise make network requests⟯) 

#### tab management

to ⟮close a tab⟯ ⟮within⟯ e.g.  the ⟮sources⟯ tab, use ⟮alt+w⟯ 
next to the ⟮styles⟯ tab in devtools, there are other tabs, showing you (in order) the elements ⟮event listeners registered⟯, ⟮DOM Breakpoints⟯,  ⟮JS properties⟯, and ⟮accessibility information⟯ 
Besides the DevTools tabs ⟮active by default⟯, there are ⟮a bunch more⟯ tabs, which you can ⟮show⟯ via ⟮the command palette⟯, or via ⟮the overflow menu⟯ 

#### global features

Whenever you get a ⟮function⟯ in devtools, you can ⟮go to the place where it's defined⟯ with ⟮c+;right click › show function definition⟯ 

## code review

Code review may be by any other peer or by some authority related to the project (depending on the purpose)
Code review is when another agent analyzes  the source code for bugs/errors/code quality
Code review may be performed by human agents or automated code review tools

## bugs

A regression is something that used to work no longer working.

## solutions

Bodge ≈ kludge
A bodge/kludge is a solution to a problem that is quick to implement but inelegant and hard to maintain.

## testing

### TDD ＆ self-testing code

TDD|Test-driven development

⟮TDD⟯ necessarily generates ⟮self-testing code⟯
⟮Self-Testing code⟯ is ⟮having built-in tests⟯ for ⟮ anything in the codebase (added while writing the things)⟯.
⟮Code coverage⟯ is a measurement of ⟮how much of $unit (e.g. lines, blocks)⟯ are run ⟮when automated tests are executed⟯
for TDD, you first write a test that describes the feature you're wanting to implement
If you want to fix a bug under TDD, first write a test exposing the defect

TDD core loop: 

1. Write unit test for feature
2. Run test, should fail (feature is not implemented
3. Write code
4. Test should now succeed
5. Refactor

### things used

A test double is a thing that replaces a production thing in testing
Types of test doubles: dummys, fakes, sutbs, mocks

dummys|passed but never used|never used, but take up space? dummy thicc
fakes|working implementations but use some shortcut (e.g. database in memory)|fake a part of their implementation
stubs|provide predefined answers/return values (instead of figuring them out)|similar to method stubs
mocks|make sure the method was called on it properly|ock the method that was called on them till it behaves properly (no, I've got no idea here)

### types of tests

Unit tests test a unit of code (where that might be a module, function or record).
Unit tests are generally quite fast.
Unit tests should never require you to e.g. do special things to your environment.
Unit tests often use test doubles.
End to end testing tests that with a given input, the program will flow correctly and the correct final state will be reached
⟮Integration testing⟯ is testing whether ⟮separate modules⟯ ⟮work together as intended⟯
Integration test can refer to testing only very few modules, the whole system in isolation, or the whole system incl externals, making it very confusing.
Unit tests may be narrowly defined as testing one unit only with test doubles, or more broadly as testing a few units, thus overlapping with the narrow definition of integration tests

### structure

./tests|Rust

### running tests

most build tools (cargo, ) or language CLIs feature a subcommand `test` to run tests

# principles

GIGO   Garbage In, Garbage Out
Garbage in, garbage out claims that if the input data is somehow bad ⟮the output data will be too⟯
Syntactic sugar is syntax that makes a programming language easier to use, but ⟮doesn't expand it's functionality⟯
"Anything that can go wrong will go wrong"   Murphy's law
⟮an anti-pattern⟯ is a pattern (intentional or not) that is ineffective/counter-productive 
YAGNI  You/ya ain't gonna need it
In computer programming, ⟮code smell⟯ is a characteristic in code that indicates a deeper problem.
While code smell is often defined to mean :an indication of a problem, it often just means an actual anti-pattern/problem
DRY   Don't repeat yourself
KISS   Keep it simple stupid
"⟮a camel is a horse designed/made by committee⟯" is a ⟮criticism of creating something by comittee⟯, since ⟮the camel symbolises incorporating too many conflicting elements⟯ 

## mech pol

the mechanism   what can be done
the policy   what should be done
separation of mechanism and policy.

# documentation

## self-documenting code

Self-documenting code is code that uses names of identifiers and strucutre (rather than comments) in such a way that it is easy for a human to understand what it is doing.
In self-documenting code, identifiers indicate what the thing they are identifying is/does.

## Comments

Comments in programming are (generally) ignored by compilers/interpreters.
But: Conditional comments are conditional statements interpreted by Microsoft Internet Explorer versions 5 through 9 in HTML source code. They can be used to provide and hide code to and from these versions of Internet Explorer. 
Comments are written primarily for humans
Generally, single line comments go to the end of the line

### comment syntaxes

#### single line 

While comment syntaxes diverge, most commonly single line comments are begun by `#`.

##### that are not the default `#`

--|lua
//|C#|Java|JS|Rust|SCSS/sass ('silent', will not end up compiling to CSS)
\#|cron|gitignore|hosts|i3 config|Markdown|m3u|Perl|Python|Regex (freespacing mode)|Ruby|sh|TOML|YAML
%|Latex
(?#foo)|Regex
(* foo *)|ENBF

#### multi-line

--\[\[foo]]|lua
/\*foo\*/|CSS|C#|Fountain|Java|JS|Rust
‹!-- foo -→|HTML
=begin foo =end|Ruby
{% comment %} ... {% endcomment %}|Liquid

### peculiarities

Besides comments, fountain has the notion of a note, delimited [[foo]]

## Documentation generators

### basics

A documentation generator is a tool that generates documentation from source code, most commonly taking into consideration the actual source code as well as a special documentation syntax.
Documentation generator syntax is often in the form of a special kind of comment.
Generally, you can build documentation using a documentation generator using its name as a CLI command.
Generally, documentation generators generate HTML websites, often using a certain template as a basis.

### various ones

#### mapping

Rustdoc is the built-in documentation generator syntax for Rust.
Javadoc is a documentation generator syntax for Java.
JSDoc is a documentation generator syntax based off of and very similar to JS.
ESDoc is a variant of jsdoc that tries to guess more from existing source code.
Assume whatever is true for JSDoc is probably also true for javadoc.

#### commands

For rustdoc, you can also use the cargo subcommand doc to generate documentation.

#### config

name|CLI|Config file
jsdoc|y|y

#### plugnins

Of the documentation generators, jsdoc also supports a plugin ecosystem.

#### comment syntax

for the following thing|///|Rust
for the following thing|/**...*/|Java (Javadoc)
for the thing we are in right now|//!|Rust
for the thing we are in right now|"""foo"""|Python (docstring, must be first line in function, technically not a comment but performs similar function)

##### syntax within comments

By default, jsdoc supports HTML in its annotation, with the markdown plugin it instead supports markdown.
Rust documentation comments accept formatting in markdown. Code in code blocks there is executed as tests.

### specific ones

#### JSDoc

JSDOc supports inline tags for annotating things within a thing, however most jsdoc tags are block tags.

##### basic syntax

jsdoc-comment ::= /** ‹jsdoc-comment-contents› */
jsdoc-comment-contents ::= ([‹jsdoc-description›] {‹jsdoc-block-tag›})|‹jsdoc-inline-tag›
jsdoc-description ::= ‹jsdoc-text›{‹newline›‹jsdoc-line-start›‹jsdoc-text›}
jsdoc-block-tag ::= ‹jsdoc-line-start›‹jsdoc-tag›‹newline›
jdoc-tag ::= @‹jsdoc-tag-name›[ \{‹jsdoc-parameter-list›\}][ - ‹jsdoc-description›]
jsdoc-text ::= {‹char›}
jsdoc-line-start ::= * # notice the space

jsdoc-inline-tag ::= {‹jsdoc-tag›}

##### namepaths

In JSDoc, to refer to things that are not in the thing being documented, to prevent ambiguity, namepaths are used.
jsdoc-namepath ::= ‹entity›{(#|.|-)‹entity›}
#|instance member
.|static member
~|inner member (member within an inner scope of something)

##### tags

@author ‹name› [\‹‹email›\›]|identifies the author

## book/webiste

mdBook is a rust crate and command-line tool that produces books from markdown.
mdBook produces books similar to the rust book.
mdBook and docusaurus can easily be deployed to github pages.
docosaurus is a react-based solution for writing documentation via markdown

# requirements engineering

## expectations

Hofstadter's Law: It always takes longer than you expect, even when you take into account Hofstadter's Law.

## time and importance

### parkinson's law

Parkinson's Law: Work expands to fill the available time.
The law of triviality was originally developed as a corollary to parkinsons law.
Law of triviality: people within an organization/community/project typically give disproportionate weight to trivial issues.
Most common example of the law of triviality: the choice of materials for a bike shed taking up a disproportionate time during the construction of a nuclear power plant.
Bike-shedding is discussion that conforms to the law of triviality: Disproportionate discussion about relatively irrellevant issues.

## user stories

A ⟮user story⟯ is the ⟮explanation of a feature⟯ ⟮from the perspective of the user⟯.

## code quality

Code quality tools such as linters and code formatters often have a CLI but are more commonly used as an extension in IDEs or as some sort of hook/CI pipeline step.

### linting

#### definition

A linter flags logic errors, suspicious constructs and violated conventions.
A linter often also includes a code formatter.

#### various linters

yaml|yamllint
css|stylelint
js|ESLint
shell (bash/csh/ksh etc.)|shellcheck

#### linters in detail

##### eslint

ESLint takes its config from a .eslintrc.js/yaml/json/cjs or from the eslintConfig field in your package.json
in ESlint, to ⟮inherit configs from other files⟯, specify the ⟮extends⟯ key
in ESlint, to use ⟮the default rules⟯, use ⟮extends: eslint:recommended⟯
in ESlint, the things stored in the ⟮settings⟯ key are ⟮global to all ESLint rules⟯
To ⟮extend⟯ ESLint, use ⟮plugins⟯

To prevent eslint or stylelint conflicting with prettier, install eslint-config-prettier or stylelint-config-prettier, respectively

#### as part of other things

the subcommand lint runs the relevant linter on the project (Nextjs: eslint)

### code style

#### definitions

Generally, each project has a certain code style.
A code style is a set of rules for how to format source code.

#### code formatter

##### definitions

A code formatter is a program that imposes certain stylistic conventions on the code by formatting it automatically.
A code formatter can be used together with a linter, however the code formatting functionality of a linter must typically be disabled.

##### prettier

Prettier is a code formatter that doesn't allow config, instead imposing opinonated but mostly uncontroversial defaults, thus allowing you to move on with your life.
Prettier works for most languages relevant for web development.

#### misc

nit = short for nitpick

#### style guides

PEP 8|Python

# Modelling

## UML

UML  Unified Modeling Language
UML is a general modelling language most commonly used in the field of software engineering.

### class

An UML class diagram generally consists of three parts, a class name on top, member variables in the middle, and member methods at the bottom.

flex-container:✫sm_220px-BankAccount1.svg.jpg✫

### sequence

flex-container:✫sm_paste-d8abaabcb6ec43ff8294b3567cb96b4fe4aa48f2.jpg✫


A sequencie diagram is an UML diagram showing object interactions as time flows.
In a sequene diagram, the lifelines go from the objects downwards.
In a sequence diagram, a thicker bar on the lifeline means the object is active.
In a sequence diagram, messages between objects are indicated by horizontal lines between the lifelines.
In a sequence diagram, the further down a message, the later it comes
non-filled arrowheads   Async messages
filled arrowheads   synchronous messages
request messages   solid line arrows
Answer messages   dashed arrows


### object


flex-container:✫sm_paste-7a55c6f447e4be8da11b84f2d660fe36fa529dc8.jpg✫
Objects in UML object diagrams at least contain a top field with the object name, the class name or both, often they also contain a field below that for instance varaibles

# automation

## misc

The Amazon Mechanical Turk is a service that allows crowdsourcing menial tasks.
The Amazon Mechanical Turk pays way below the minimum wage.
The Amazon Mechanical Turk is sometimes used for study subjects.


# toolchains

In general, a toolchain is a set of software tools used to do something.
In software development, a toolchain is a set of tools used in combination to develop and deploy software.

expo is a toolchain for react native that does a bunch of toolchainy stuff.
expo is accessed via expo-cli
expo's managed workflow handles pretty much everything but writing code
expo's bare workflow allows you to pick and choose whichc parts of expo to use
to test an app using expo on a phone, you need to install the expo client app on your device
If you want to use the bare React Native workflow, you will have to set up your target's devtools

## language installation ＆ setup

rustup is the rust installer

## package manifest ＆ language config file

A package manifest (though different languages call it different things) specifies metadata and config for your package/project as well as dependencies.
A language config file specifies config (e.g. compiler options) for the current programming language.
Package manifest and language config files are often the same thing.
In most package managers, besides the place where you specify your dependencies, there is also a lockfile.
While the package manifest or wherever is where you specify the versions of your dependencies you accept, the lockfile specifies the versions which are actually installed.

Cargo.toml|cargo
package.json|npm|yarn

tsconfig.json|TS


package manifest top-level keys
dependencies|specify dependencies|Cargo.toml|package.json
devDependencies or dev-dependencies|Cargo.toml|package.json
package|general package metadata (author, name etc)|Cargo.toml
none, are all their own top-level keys|general package metdadata (author, name etc)|package.json
main|entry point|package.json

package-lock.json|npm
Gemfile.lock|bundler

Most of the config for frameworks is done in a global config file, which is placed in the project root.
_config.yml/.toml|Jekyll


### dependencies

A dependency is a piece of software another piece of software relies on.
The syntax for dependencies in most package manifests is as key-value pairs, where the value is a semver version.
In rust, instead of the value of a key-value dependency pair being a version, it may also be a table with version as its one of keys, and other optional keys.

#### auto-adding

Some package managers (e.g. npm) will add a package as a dependency if you install/update it, while others will instead install dependencies listed in the package manifest automatically (e.g. cargo), some will do both, and some will do neither.
npms save dependency to package manifest automatically behavior can be disabled with --no-save
Some package managers separate dependencies (for running) and dev-dependencies (for development)
Dev dependencies are usually their own area in the package manifest.
npm allows --save-dev direct installation to dev dependencies via --save-dev

### rust

specifying features of packages
package-with-features ::= ‹package-name› = \{ version = "‹semver-version-specifier›", features = \["‹string›{, "‹string›"}\]\}

## packages ＆ package managers

Package management is managing packages, i.e. handles installing, uninstalling, updating...
some package managers support suffixing an @version to address a specific version

### package managers

A package manager is a program that does package management.
A package manager typically can manage packages from many different developers.

#### vs installers

Package managers are contrasted with installers, which usually install one piece of software only, and do not keep it updated.

### package format

A package is a file in a package format.
A package format usually is made up of an archive (format) of some kind and some metadata.

### local and global

Package managers mainly for programming languages tend to do their package management for the local project by default, and only globally for the whole system if explicityly instructed with -g or --global.
Package managers mainly for OS's typically install their packages for the whole system by default, though some have the option for installation in the home directory only, e.g. by using --user.
Most languages only allow you to import local pacakges.

### directory structure

./node_modules|directory for installed packages|npm

### (un)installation

install PACKAGE|install a package|apt|brew|npm|DIFFERENT MEANING: bundler
install|install all dependencies in package manifest|bundler|gem
uninstall PACKAGE|uninstall a package|brew|npm
remove PACKAGE|uninstall a package|apt

### updating

update|update the package index|apt|brew|DIFFERENT MEANING: bundler, npm
update|update all dependencies/installed packages|bundler|npm
upgrade|installs all available updates|apt|brew
refresh|update all installed packages|snap

### browsing

show FOO|shows information about a package foo (npm); shows path to gem foo (bundle)
show FOO version|show latest version of package foo|npm
ls/list|list installed packages|brew|npm
outdated|show a list of outdated packages|brew|npm|bundler

### publishing

pack|create a tarball of a project/package|npm
publish|publish to offical pagckage hub/repository|cargo|npm

### eject to editor

edit[ ‹name›]|open ‹name› in code editor, or default if none is provided|espanso

### repositories

A repository is anything that stores software.
Often, a repository either stores the code of a VCS, or packages of a certain type.

## project structure

### new empty

new foo|creates a new project in new directory foo|cargo, jekyll
init|set up a new project/package, incl pacakge manifest in current directory|bundler|cargo|npm

### boilerplate

Boilerplate code is repetitive code that is reused often, often also implying that it is unneccessary and would be better if it just wasn't necessary.

To set up a default repository with boilerplate, different frameworks/languages have different tools:
react|create-react-app ‹name›
nextjs|create-next-app ‹name›
react-native|expo init ‹name› 
expo init creates a project using expo's managed workflow

cargo-generate is a crate that allows using a pre-existing git repository as a template.
the npm package create-wasm-app adds the command npm init wasm-app which allows us to set up an js app which consumes our rust-generated wasm

### rust

./examples
./benches

## building

### build tools

Build tools are the tools that create an executable application from various parts.
To build something, a build tool starts at an entry point.
A dependency graph is a directed graph where each vertex is a module and each edge is a dependency relationship.
From an entry point, a build tool assembles a dependency graph.
From a dependency graph, a build tool builds it's output file(s).
Code splitting is the splitting of code into various bundles or components which can then be loaded on demand or in parallel.

#### processors

a CSS preprocessor is a transpiler from a language that is not css (though typically a superset) to css.

##### postCSS

PostCSS is a CSS processor (CSS → CSS), that does nothing by default, but can be hooked into by plugins (written in JS).
To use PostCSS you need to have added it to your build tool and have a `postcss.config.js`.
To use PostCSS with webpack, add the `postcss-loader`.
Within your `postcss.config.js`, add plugins by adding `require()` calls to them within `module.exports.plugins`
```
module.exports = {
  plugins: [
    require('autoprefixer'),
    require('postcss-nested')
  ]
}
```

###### autoprefixer 

Autoprefixer is a tool to add vendor prefixes to CSS properties automatically, implemented as a PostCSS plugin.

#### compilers

A compiler is a type of build tool.

##### compiler options

A compiler option is a setting that changes what a compiler does.
Compiler options may be set via pragmas, via a config file, via CLI options, or via a combination.
TS|config, CLI

###### TS

compiler option|function
strict|activate a bunch of other options, amongst others noImplicitAny and strictNullChecks

###### Rust

rust has a set of compiler options that allow the conditional compilation of code.
In rust, a compile-time feature flag is a compiler option that allows conditional inclusion or exclusion of code.
rust allows the creation of custom compile-time feature flags that may be used in the conditional compilaton of code via compiler options.
rust has two types of pragmas to specify a set of compiler conditions that must be met: attributes and macros, both indicated by cfg.
in rust, you specify custom compile-time feature flags in a [features] section of your Cargo.toml
in the [features] section of your Cargo.toml, each key specifies a feature, and takes an array of crates or other features to optionally require.
you can activate a feature for an external crate by referring to it within the features array that is part of the table defining the dependency.
custom compile-time feature flags are refered to in `cfg` by the ‹cfg-name› feature
compile-time feature flags are enabled by cargo build --features "‹featurename›" 
any cfg condition is enabled by --cfg "featurename"
cfg-attribute-sytnax ::= #\[cfg(‹cfg-predicate›)\]
cfg-predicate ::= ‹cfg-option›|‹cfg-logic-function-multiple›|‹cfg-not›
cfg-option ::= ‹cfg-name› = "‹cfg-value›"
cfg-logic-function ::= (all|any)\(‹cfg-predicate-list›\)
cfg-not ::= not\(‹cfg-predicate›\)
cfg-predicate-list ::= ‹cfg-predicate›{, ‹cfg-predicate›}

##### specific compilers/transpilers

###### babel

Babel is a transpiler that mainly transpiles ⟮newer JS (e.g. ES 2017, ES 2020) to older JS (e.g. ES5)⟯, but can also transpile other things.
You can add babel to webpack by adding `babel-loader`.

####### config

Babel is configured with a `babel.config.json`.
Plugins and presets are specified in the arrays defined by the `presets` and `plugins` keys.
When using `babel-loader`, config for babel instead goes into the `options` object

```
module: {
  rules: [
    {
      test: /\.m?js$/,
      exclude: /(node_modules|bower_components)/,
      use: {
        loader: 'babel-loader',
        options: {
          presets: ['@babel/preset-env']
        }
      }
    }
  ]
}
```

####### modules

Various babel modules are published at `@babel/whatever`.
Core babel functionality is at `@babel/core`.
`@babel/cli` containts babel's cli functionality

####### plugins

Babel plugins are the things that tell babel how to transpile your code.
For example, @babel/plugin-transform-arrow-function is what babel uses to transpile arrow functions
A preset is a predetermined set of plugins.
`@babel/preset-env` is the preset for transpiling to older js, choosing what is necessary automatically.
While `@babel/preset-env` allows you to set your target browsers manually by setting the `target` key within the object in `presets` array of the config, by default it will just conform to your `browserslist` config.

####### core-js

`core-js` is a set of polyfills for various JS features.
`core-js` is not part of babel, but they are often used together since babel no longer offers its own polyfills.
You use `core-js` by importing a variant of it at the top of your entry point.

core-js/features|all features, whether stable proposals or experimental
core-js/actual|stable features ＆ web standards (recommended)
core-js/stable|stable ES features
core-js/(feature|actual|stable)/‹feature-name›|import only a specific feature
for example: `import "core-js/actual/set";`

####### regenerator

`regenerator` is a polyfill for ES6 generators.
`regenerator` is not part of `core-js` since it contains a runtime component.
to import the regeneraotr runtime, just import `regenerator-runtime/runtime` at your entry point

#### module bundlers

A module bundler is a type of build tool that merges together all your JavaScript code and its dependencies into one or more bundles.
A bundle is a single file.
Most commonly module bundlers generate only a single file, most commonly called bundle.js.
A module bundler is often also just called a bundler
There are more JS build tools than you can shake a stick at. The most common is webpack.

##### webpack

A module is a independent thing you use from another file.
A module can be a code file, stylesheet, data, assets (image, videos), ...
Modules must be imported to be used, just as in any normal programming language.
A loader transforms a file into a module.
File types that are not natively supported require a loader.
In webpack, (only) json and JS are natively supported.

#######

###### loaders

Loaders are defined (in the config file) by a JS object.
The `test` key of a loader is used to match files to process with this loader via a regex.
The `use` key of a loader is used to specify which loader to use.
```
{ test: /\.txt$/, use: 'raw-loader' }
```
While transforming a file into a module, a loader may also transform them.

####### various loaders

######## data

By default, loaders for data files (tsv, xml etc.) will parse to JSON

###### CLI

webpack-cli is the command for administering webpack.

###### config

Webpack can run without a config file, nevertheless it is sensible to have a config file.
Webpack's config is a normal js file.
You specify settings in the webpack config file on module.exports.

###### plugins

Plugins extend webpack functionality.
Plugins are specified in the array `module.exports.plugins`.
Plugins are created from classes.
```
module.exports = {
  plugins: [new HtmlWebpackPlugin({ template: './src/index.html' })],
};
```
Classes for webpack plugins have a method `apply` which recieve an argument of the compiler to hook into.

###### The runtime

The manifest is webpack's internal map of modules.
Webpack's glue code used to connect different modules at runtime is the runtime.
In webpack's runtime, all import statements become `__webpack_require__` calls.
the runtime uses the manifest.

#### CLI

‹tool› build builds a production build in cargo, jekyll, next

### conditional building

#### release profiles

Release profiles are sets of compiler options for certain scenarios.
The most common profiles are one for development and one for production.


table:config key|tool
mode|webpack
profile|rust

table:name|tool
dev|cargo
development|Rust


table:name|tool
release|cargo
production|Rust



Rust allows customization of its release profiles via the Cargo.toml [profile.*] headers

#### targets

A target is the platform/environment a build tool is building for.
Browserslist is a tool to define target browsers.
Browserslist is specified in a package.json key, which accepts an array of specifiers, or the keyword "default" for a sensible default.

### hot reloading

Hot reloading reloads a thing as you change the code etc.
serve (for jekyll and webpack) and dev (for nextjs) serve your build with hot reloading 
nextjs serves your app at port 3000 by default
You can run a build you created with build (for nextjs) with start (for nextjs)

### structure

for most build tools, code lives in a src directory.


#### Entry point

In computer programming, an entry point is a point in a program where the execution of a program begins, and where the program has access to command line arguments. 

##### file

###### default

./src/index.‹suffix›|webpack
./src/main.‹suffix›|rust

##### function

The entry point of many programming languages is the main function:
public static void main(String[] args)|Java
main()|rust

##### config

`module.exports.entry` specifies the entry point.
`module.exports.entry` may take a string (of URLs) for a single entry point, or an array (of URLs) or object for multiple entry points.
Using an object for multiple entry points allows for named entry points.
```
module.exports = {
  entry: "path/to/entrypoint.js",
  // is the same as
  entry: ["path/to/entrypoint.js"],
  // is basically the same as
  entry: {foo: "path/to/entrypoint.js"}
}
```
Using an object to define multiple entry points then allows any entry point to further be another object, allowing for further configuration.


table:module.exports.entry.sometrypoint.|does
import|path of entry point as would have been specified directly before
publicPath|associate an output `publicPath` with this entry point

#### Output

Output code goes in (by default)
./dist|webpack
For module bundlers, the output directory contains the bundle(s)

##### cleaning

clean remove generated files in cargo, jekyll

## task runners

A task runner is used to run predefined tasks, which would otherwise be tedious or impossible.
Typically, task runners run shell scripts.

### npm scripts

npm scripts works as a task runner for JS.
npm scripts are defined as object fields in the scripts object of your package.json
besides custom npm scripts, npm also has lifecycle scripts, which run at particular, predefined times

#### CLI

to run your npm scripts, you use npm run/run-script
npm run = npm run-script

#### env

within npm scripts, we can access all our dependencies binaries without specifying the full path (without having to use npx)
a package.json key ‹key› is available in npm scripts as the variable $npm_package_‹key›
Certain config values are available in npm scripts as the variable $npm_config_‹name›

#### naming

npm scripts names are often written foo:bar (this is only a convention, however)

##### pre/post

npm scripts `pre‹name›` and `post‹name›` will automatically run before/after npm script `‹name›`

##### lifecycle scripts

npm lifecycle scripts (non-deprecated): prepare, prepublishOnly, prepack, postpack

##### aliases

A set of predefined npm scripts have aliases where you can run `npm ‹name›` instead of `npm run ‹name›`
Among those: npm build, start, stop, test.
`npm test` can further be abbreviated `npm t`

### vscode tasks

Vscode tasks are used to integrate external task runners, build tools, and pretty much anything else you can run in a CLI into vscode.
Vscode tries to auto-detect tasks, but you can also define custom ones.
VS Code currently auto-detects tasks for the following systems: Gulp, Grunt, Jake, and npm.
Custom tasks are defined in a `tasks.json`.
Tasks can either be user or workspace level.

#### running tasks

⟦⇧⟧ ⟦⌘⟧ ⟦b⟧ opens a picker for running a build task, or runs the default one if it is specified.
entering the `task` keyword into quick open will also show a list of tasks to run.

#### task groups

#### custom tasks

various commands allow you to create a tasks.json with a default template.

Running `configure task` from the command palette or as an option of the build task picker will create a workspace task.

##### tasks.json

Within `tasks.json`, the `tasks` array contains a sequence of task objects.

table:task property|meaning/values
label|text label in UI
type|either `shell` or `process`, meaning interpret it as a shell command or as a process to execute
command|command to execute
group|specify the group the task belongs to
presentation|specifies how the task output is handled in the UI
options|allow overriding the `cwd`, `env` and `shell`.
runOptions|define when a task is run.

while you can provide the whole command to `command` such as e.g. `mv foo/bar quuz/leroy`, you may also separate the arguments into an `args` array.
```
"command": "mv",
"args": ["foo/bar", "quuz/leroy"],
```
the array of `args` for vscode tasks may also take an object for each arg specifying the escaping/quoting style.
The escaping/quoting style of a vscode tasks may be 
escape|escape spaces
strong|quote with quotes forbidding evaluation within (`'` on *nix)
weak|quote with quotes allowing evaluation (`"` on *nix)

```
{
  "label": "dir",
  "type": "shell",
  "command": "dir",
  "args": [
    {
      "value": "folder with spaces",
      "quoting": "escape"
    }
  ]
}
```

###### composing tasks

You can compose tasks out of simpler tasks with the `dependsOn` property.
the `dependsOn` property takes an array of other tasks to run.
`dependsOrder` allows specifying how the order of tasks in the `dependsOn` array will run.

###### output behavior

https://code.visualstudio.com/docs/editor/tasks

## mapping

different tools may perform one or more roles within a toolchain.

Most commonly, the CLI for a framework will also be a build tool.

### dpkg / apt

apt is the package manager for Ubuntu.
In the past, one would have used apt-get as a way to interface with apt (but now deprecated).
PPA = Personal Package Archive
apt can interact with the four official ubuntu repositories, with PPAs, or theoretically also with third-party repositories
PPAs are repositiories in the conventional sense, but are distinguished by ubuntu from repositories proper in that they are repositories of a single developer published via launchpad (which means the dev doesn't need their own server).
The four types of offical ubuntu repositories are main, universe, restricted and multiverse.
main|canonical-supported FOSS
universe|community maintained FOSS
restricted|proprietary drivers
multiverse|Software restricted by copyright or legal issues
At least some of the repositories of ubuntu are only updated on OS updates, but I have no idea which ones.
to add/remove other repositories/ppas with apt use add-apt-repository (--remove for removing)
apt repositories/ppas are stored in /etc/apt/sources.list(.d)
aptitude is a TUI for apt
apt-cache can be used to query apt's package cache (the local record of packages)

dpkg is a package manager for .deb packages, but does not have a package repository, instead requiring you to download your packages yourself.
apt uses dpkg in the background.

### rust

cargo is the package manager and build tool for rust.
the official package repository for cargo is crates.io
There is no official task runner for rust, but one commonly used is cargo-make.

### JS

npm is the most common package manager for JS, followed by yarn. 
The official package hub for npm is the npm Registry.

### python

pip is the package manager for python.
The official package hub for pip is PyPI.
The package format for python format .whl ('wheel')

### anaconda

Anaconda is a batteries-included distribution of Python and R and a bunch of associated packages for scientific computing.
conda is the package manager for the anaconda software distribution.

### react antive

metro is the bundler for React Native.

### Latex

In latex the package manager is part of the tex distribution
The two most common latex distributions are ⟮TeX Live⟯ and ⟮MiKTeX⟯
tlmgr is the package manager for tex if you are using the TeX Live distro.
The official package hub for tex is CTAN.

### espanso

for espanso, its package manager is under `espanso package`
for espanso, `espanso package install` and `espanso package uninstall` may be abbreviated `espanso install` and `espanso uninstall`

### snap

snap is the package manager for snaps.
snaps are mainly used in Ubuntu, but can be used on many *nixlikes.
snap packages = snaps
snaps are containerized.
snaps are maintained by the snapd daemon.
snap calls its updates refreshes.
snap auto-refreshes four times a day by default.
snap stores most of its stuff in /snap.
snaps are stored in /snap/‹snapname›
snaps variable data (such as log files) are stored in /var/snap
snap has a second linux file system in /snap/core, which it mounts in specific places at runtime.
snaps are pacakged by snapcraft.

### homebrew

homebrew (command: brew) and macports (command: port) are package managers for macos.
homebrew can also be used on linux, and is written in ruby.
tap TAPNAME|add a repository|brew

in ⟮homebrew⟯, a ⟮formula⟯ ⟮describes a package⟯. 
A ⟮formula⟯ is a ⟮ruby (.rb⟯) file. 
Each ⟮tap⟯ has ⟮its own list of formulae⟯, which you can find at ⟮s4:5;⟮tap-name/Formula⟯.⟯ 
A ⟮formula⟯ contains ⟮the location of the tarball of the source⟯, and  ⟮a script that knows how to build the software from the source⟯. 
A ⟮precompiled formula⟯ is known as a ⟮bottle⟯. 
A ⟮cask⟯ is like a ⟮formula⟯, but ⟮it's used to installed native .dmg mac apps instead of cli packages⟯ 
In homebrew, ⟮all formulae⟯ are contained in ⟮taps⟯ (≈ ⟮repositories⟯). 
The ⟮default⟯ ⟮taps⟯ are ⟮homebrew-core⟯ and ⟮homebrew-cask⟯ (for ⟮Casks⟯), and you can ⟮add further 3rd party ones⟯ 

In homebrew, according to the docs, a ⟮Keg⟯ is ⟮the path a formula is installed to⟯, including ⟮the specific version⟯. 
since ⟮Kegs⟯ are ⟮always installed⟯ to ⟮the Cellar⟯ (path e.g. on apple silicon ⟮s6;⟮/opt/homebrew/Cellar⟯⟯), ⟮s8;a Keg has the following syntax (on apple silicon ⟮/opt/homebrew/Cellar/‹formulaname›/‹version›⟯ ⟯ 
If something is ⟮keg-only⟯, it is ⟮installed into (/usr/local or /opt/homebrew/ or linux)/Cellar⟯ but ⟮not symlinked anywhere else⟯, often because ⟮the OS already ships with a version that this would conflict iwth⟯ 

⟮homebrew⟯ installs ⟮anything⟯ to ⟮within its prefix⟯. 

homebrew prefixes


⟮macOS Intel⟯|⟮/usr/local⟯
⟮Apple Silicon⟯|⟮/opt/homebrew⟯
⟮Linux⟯|⟮/home/linuxbrew⟯


⟮Where homebrew has its prefixes⟯ mean you ⟮don't need to sudo anything with brew⟯, which is also ⟮highly discouraged.⟯ 
If necessary, ⟮homebrewbrew⟯ ⟮links things⟯ ⟮from its prefix⟯ ⟮into directories such as /usr/local/bin, /usr/local/lib⟯ 

### ruby

ruby has two package managers, bundler, which mostly does dependency management, and RubyGems with the command gem which mostly does installation.
In ruby, packages are called gems.
The official package hub for RubyGems is rubygems.org
bundler is kinda weird, since it is a ruby gem itself.
bundler manages the gemfile 
The gemfile contains dependencies
the gemfile is just a ruby file
In a gemfile, the first thing is a call to source, which establishes the global source
source is also a method which takes an url as the first and a block as the second argument if you want to establish additional sources
within the gemfile, gem dependencies are defined by `gem ‹name›, ‹version›`

### tools to interact with framewokrs

interact with nextjs|next
interact with jekyll|jekyll

### Mobile development

Mobile development is centered around a core IDE, Android Studio for android and XCode for iOs

# deployment

## preventing undesirable experiences

### canary

Canary release/deployment is showing an early build of an application to only a small subset of users
In canary releases/deployemnt, the users who get the early build are monitered for feedback or bugs.
In canary realeases/deployment, after we've verified that everything's all right for the subset of users, we'll release it to a larger audience eventually if okay.
Sometimes, the distinction is made between a canary release, which is a dedicated version of a program that users could choose to use (e.g. Chrome Canary), and a canary deployment, which is where it is just deployed to a group of people without their input, however, this distinction is often not made.
canary releases/deployements get their name from the canary in the coalmine metaphor

### blue-green deployment

In a blue-green deployment, there are two environments/servers, blue and green.
blue|existing production environment
green|new version
In a blue-green deployment, initially all users are routed to the blue env. Once the green env is deployed, it undergoes a heavy set of tests. After these pass, the users are instead routed to the green env. The blue env remains on standby, and if there is a problem with the green env, users can get pushed back to the blue env.

### feature flags 

feature flags (/toggles/switches) are options that allow you to turn functionality on and off without deploying new code, in DevOps contexts generally during runtime.
Feature flags can be used for hiding stuff for cd/ci (the way rust does experimental features), canary releases or user targeting (and thus A/B testing)
Rust hides ⟮unstable/experimental⟯ ⟮features⟯ behind ⟮feature flags⟯, ⟮sb;which you ⟮can only activate⟯ on ⟮nightly⟯⟯. 

# Misc/no place yet

most languages allow an arbitrary amount of spaces and tabs as indentation, YAML however only allows spaces
hot whatever|doing whatever while the system is still running
cold whatever|doing whatever while the system is not running
hot swapping may be of components, or of software

# resource leak

A ⟮resource leak⟯ occurs when a program ⟮does not release resources⟯ when ⟮it no longer nees them⟯. 
A ⟮memory leak⟯ is ⟮a resource leak⟯ involving ⟮memory⟯. 

# Indexing

Most langauges I know start linear collection indices at 0, however lua starts them at 1
In most languages, providing negative indices counts from the back, with -1 being the last element.
Square bracket notation: most commonly used for array/linear collection indexing or accessing members in associative collection, esp. if primitives in language. SCSS/Sass is special in that maps are primitive in the language, but neverthelesss square bracket notation does not work, one must use map-get() (also not map.get, which its documentation still falsely refers to)
any key in a table lua, Ruby, JS, Py, Rust
In most languages, indexing a linear collection outside of its bounds produces an error, in JS it merely produces undefined
In most languages, referring to an associative array element that doesn't exist will get you an error, in Lua and JS you merely get undefined
TS changes referring to a lin col index outside of bounds or a nonextand assoc arr element to an error
JS allows indexing strings via the charAt method.

Dot notation ⟮object⟯⟮.⟯⟮member⟯
Most languages use dot notation for accessing members of records.
Some languages also use dot notation for access of assoc arrays.
In Rust, also tuples are accessed via dot notation, but arrays are not.
dot notation: TOML also 
string keys of tables lua
members of objects in lua
but: not method calls, use : instead

Some languages have a scope resolution operator, which is typically used instead of dot notation for namespace resolution, for calling static members of classes, and for variants of enums.
The scope resolution operator is typically `::`.
The scope resolution operator comes from C++ and is used in ruby, rust.

While JS will not error if you try to access a key or index that is nonexistant, it will return undefined, and if you then try to access something of undefined, it will return an error.
TS makes referring to ⟮nonexistent properties⟯ an ⟮error⟯, rather than ⟮returning undefined⟯
In JS, the ?. is called the optional chaining operator.
In JS, the optional chaining operator works like dot notation, except that if used on a nullish value, it will short-circuit and return undefined.
the optional chaining operator short-circuiting to undefined when after something that is nullish prevents attempted indexing of something nullish, which would otherwise cause an error.
The optional chaining operator can be used instead of dot notation, and before [] notation or method calls.

A lua table can be accessed via dot and square bracket notation. (Perhaps move this to its own thing-access section)
assoc array access []|Python|Ruby|
{}|Perl

# Project Jupyter

⟮Jupyter Notebooks⟯ used to be called ⟮IPython Notebooks⟯
Jupyter notebooks are multimedia documents.
Jupyter notebooks can contain code, markdown test, math, plots, media/images.
Code within Jupyter notebooks are run by kernels.
There Jupyter kernels for a bunch of different programming languages.
The python kernel for Jupyter notebooks is the ipython kernel.
Jupyter notebooks are in fact implemented via json files.
The file type of ⟮jupyter notebooks⟯ is ⟮.ipynb⟯
The Jupyter Notebook App is a server-based application that allows editing and running notebook documents via a web browser.
The Jupyter Notebook App can be executed locally or can be installed on a remote server and accessed through the internet.
Jupyter Notebooks can be edited using many different programs, e.g. the official Jupyter Notebook App, but also VSCode
The thing managing all the Jupyter stuff is Project Jupyter

jupyter supports magic commands starting with % that do a variety of things

%system or ! executes shell commands from jupyter


# misc

https://en.wikipedia.org/wiki/Type_theory#History

Associative arrays: names, literals, other construction methods, etc.

## Computer Ergonomics

Ideally, your ⟮arm (elbow⟯) should have an angle of ⟮90°⟯ while ⟮touch typing⟯ 
Ideally, ⟮your wrist⟯ should be ⟮hovering⟯ while ⟮touch typing⟯ 

# server directory structure

Jekyll ＆ common

./assets|assets
./assets/css|css files
./assets/js|js files

# Metacharacters ＆ escapes 

A metacharacter is a character that has a special meaning to a computer program, such as a interpreter/compiler or a regular expression (regex) engine.
A reserved character is a character that cannot be used in a certain context because it is a metacharacter and thus must be replaced with an escape sequence or a different character, or not used entirely.

An escape character is a metacharacter that invokes an alternative interpretation of the following character(s)
An escape sequence is the combination of an escape character and the subsequent characters that has a specific meaning.
Weirdly, an escape sequence (but not an escape character) is sometimes called a character escape.
In C, \ acts as a/the escape character, with many programming languages having copied this, this includes latex, at least for basic things such as % and ＆.
C pioneered a set of escape sequences starting with the escape character \ and certan chars/sequences afterwards, which have been widely adopted.
In HTML, ＆ acts as a/the escape character.
Liquid is rare in that escape sequences don't exist at all.
Generally, most languages will require using an escape sequence for their metacharacters, or at least the ones that could have meaning in a given context, this is known as character quoting.
Besides character quoting, escape sequences are often used for characters that cannot (easily) be typed on a keywboard.
Escape sequences for unicode codepoints:
\u + UTF-16 escape sequence (must be a set of two \u + UTF-16 escape  sequence if surrogate pair)|JS
\‹unicode-code-point›|CSS
\u‹unicode-code-point›|Regex (some flavors)
\u‹four-hex-digits›|C-style escape sequence
\U‹eight-hex-digits›|C-style escape sequence
\x\{‹unicode-code-point›\}|Regex (other flavors)
\u\{‹unicode-code-point›\}|JS (ES 6 and beyond)
can be directly input|most programming languages

Escape sequences for ascii characters
octal
\0‹octal-digit›‹octal-digit›‹octal-digit›|Regex (some flavors)
\‹octal-digit›‹octal-digit›‹octal-digit›|C-style escape sequence, Regex (some flavors)
\o\{‹octal-digit›‹octal-digit›‹octal-digit›\}|Regex (some flavors)

alphabetic
\c‹character› (ASCII control character (‹character›-64))|Regex (some flavors)

hexadecimal
\x‹hex-digit›‹hex-digit›|Regex (some flavors)




HTML has ⟮two ways⟯ of specifying ⟮character escapes⟯. 
Both ways HTML has for specifying character escapes ⟮c+;start with an ＆⟯ and ⟮c+;end with a semicolon ;⟯.
Of these, ⟮numeric character references⟯ ⟮refer to the character position within character set (most commmonly UTF-8⟯), ⟮sb;they start ⟮c+;with # (after ＆⟯) and can be specified in decimal or hex. ⟮hb;(for example ⟮c+;＆#8203;⟯⟯⟯) 
⟮Character entity references⟯ ⟮have a short, memorable name⟯ ⟮hb;(for example ⟮c+;＆amp; or ＆quot⟯⟯) 
This distinction is however often not made, and often ⟮any name that is a combination of some of the name parts (e.g. HMTL entity, entity reference, character entity⟯) are used. 

to en/decode html character escapes, the npm package and concomittant CLI he is often used.

Character entity reference / Numeric character reference|Displays as / creates?
⟮c+;＆gt;⟯|⟮c+;›⟯
⟮c+;＆lt;⟯|⟮c+;‹⟯
⟮c+;＆amp;⟯|⟮c+;＆⟯
⟮c+;＆shy;⟯|⟮A hyphen that works as a line break, but is only displayed when necessary for wrapping.⟯
⟮c+;＆#8203;⟯|⟮A zero-width space that allows the browser to break there, when necessary⟯


# text encoding

## theory

A character is the fundamental unit of text in computing contexts.
In practice, a character is 'anything that has an unicode code point'
A character set is a set of characters grouped for some reason.
A character encoding is a set of mappings of the characters in a character set to some sort of numeric representation.
All character encodings before Unicode mapped characters directly to the binary encoding.
Unicode is a character encoding that maps characters to an abstract unit known as a code point, and then any Unicode translation format are character encodings that map unicode code points to binary rperesentations.
Once a computer has determined which character a byte or set of bytes represents, it pulls the relevant glyph from (simplified view) a font to display it.
If your computer does not have a glyph for a character in any font its willing to use in this situation, it will display something like a box or question mark.

### font

a computer font is a file containing a set of glyphs for certain characters.
There are two main types of computer fonts, based on how they store characters: bitmap and vector/outline, with the advantages and disadvatages you would expect.

## encodings

character encodings (simplified): Morse -(end of the 19th century)→ Baudot-Murray -(1960s)→ ASCII -2000ish→ Unicode

### Morse

#### genealogy

The original morse code was meant for english speakers. 
The morse code used today is an overhauled version of the original morse code called international/continental morse code.

#### encoding

Morse code varies signal length to produce different units.
In morse code, a space is signal absence.
In morse code, signal presence may either be a dot or a dash.
In morse code, length is measured relative to the dot length

A dash|three dots
A space (between words)|seven dots
A space (between characters)|three dots
A space (between dots/dashes)|one dot

#### syntax

morse-code-sentence ::= ‹morse-code-word›{‹word-space›‹morse-code-word›}
morse-code-word ::= ‹morse-code-character›{‹character-space›‹morse-code-character›}
morse-code-character ::= (‹dot›|‹dash›)‹dd-space›

#### common words

SOS is `. . . - - - . . .`
Notably, SOS does not have character spaces between characters, instead only the one-long necessary space.
SOS = `. . . - - - . . .` indicates that loss of life or major loss of property is imminent.
SOS was chosen because it is easy to recognize.
SOS is widely believed to stand for Save Our Souls, but this is a backronym.

### baudot

the baudot(-murray) code was a 5-bit binary encoding.
the baudot(-murray) code was later extended to 6-bit (ish) via a FIGS (figure shift character).
With the baudot murray code came the change to punched tape.

### ASCII

Control characters are also called non-printing characters.
ASCII (no extension) takes up 7 bit.
ASCII characters that are not control/non-printing characters are printing characters.
Control characters as a term is generally reserved for the 65 characters defined in ASCII and extended ascii, other characters such as the zero-width non-joiner may be considered semantically similar, but are called formatting characters.
the first 32 ASCII control characters are exactly 64 bit below the uppercase letters, and so may be represented by letters A-Z plus a few symbols.
In the past the control key would have lowered the sent keycode by 64 to produce the first 32 ASCII control characters; this behavior still exists (albeit emulated) in terminals.
Since the control character is often represented by a caret, and the control key plus letter was/is used to produce ASCII control characters, ASCII control characters are often indicated ^‹letter›, this is called caret notation.
Caret notation is commonly used in *nix contexts.
In ASCII, the uppercase characters are 64 above their index in the alphabet.
In ASCII, the lowercase characters are 96 above their index in the alphabet/32 above the relevant uppercase character.
In ASCII the 7th bit will be set for any letter in the alphabet.
In ASCII the 6th and 7th bit will be set for any lowercase letter in the alphabet.
In ASCII the 6th and 7th bit will never be set for any control character within the 128 original characters besides DEL.
0-31|control characters
32-64|various symbols, numbers, etc.
65-90|A-Z
91-96|various symbols
97-122|a-z
123-126|various symbols
127|DEL


The most common escape sequences (not character quoting)
C escape sequence|name|short|hex|alternative meaning
\n|new line|LF|0x0A|any newline character
\r|carriage return|CR|0x0D
\f|form feed|FF|0x0C
\t|(horizontal) tab|HT|0x09
\v|(vertical) tab (may also match any vertial whitespace in some langauges)|VT|0x0B
\b|backspace|BS|0x08
\a|bell|BEL|0x08
\e|escape|ESC|0x1B
\0|null|NUL|0x00
|end of transmission|EOT|0x04

EOT is often interpreted as EOF (which doesn't exist as a control sequence) in the contexts of files.
EOF|end of file

CRLF|Windows|The Internet
LF|Unixlike (Linux and modern mac)
CR|older macs

The bell character is sometimes used in command-line utilities for a notiification sound

### ISO/IEC 8859

The ISO/IEC 8859 encodings are based on ASCII but take up 8 bits instead of 7, with the extra 128 characters occupied by code pages for different languages

Garbled text due to character encoding errors is called 　文字化（もじば）け, which was common in japanese due to a number of incompatible encodings existing.

### Unicode

Unicode is goverened by the unicode consortium.

#### Codepoint subdivision 

While in encodings such as ASCII, a character is equivalent to a series of bits, in Unicode a codepoint is an abstract unit that can be realized in different encodings.
The fundamental unit in unicode is a codepoint.
Unicode codepoints are frequently written U+{‹hex-digit›}
All unicode codepoints are contained in the unicode codespace.
Currently, about 12% of the unicode codespace is used.
The unicode codespace consists of 17 planes. 
A unicode plane contains 2^16 = 65536 codepoints.
A plane in unicode consists of one or more blocks.
Since unicode blocks are contained within planes, they at most can be the size of a plane, i.e. 2^16=65536
Unicode blocks always sized in multiples of 16, therefore the first hex digit in an unicode block will always end 0, and the last digit will always end F.
Unicode blocks are always contiguous and disjoint with each other.
In general, an unicode block should be united by a common purpose in some way.

##### plane table

0|Basic Multilingual Plane|contains the most common unicode characters, such as most writing systems ＆ symbols
1|Supplementary Multilingual Plane|assortment of different characters and emoji
2|Supplementary Ideographic Plane|bunch of extra, mostly historical/variant CJK characters
3|Tertiary Ideographic Plane|bunch of extra, mostly historical/variant CJK characters
4-13|Currently unassigned
14|Supplementary Special-purpose plane
15-16|Private Use Area planes

All planes beside the basic multilingual plane are supplementary.
Unicode code points outside of the basic multilingual plane are sometimes called astral

#### multiple characters

A 'character' may consist of one or more (encoded) unicode code points.
Some characters can be created both by combining a character with a combining character/mark, or by using an one-codepoint precomposed version.
Combining characters/marks are unicode codepoints that modify other characters, instead of standing by themselves as characters.
Combining characters/marks come after the thing they are modifying.
You can attach many different combining characters to one character at the same time.
Precomposed characters are characters that look like the combination of a character and a diacritic but actually occupy only one codepoint.
é could be a character plus a combining character, or a precomposed character.
Two unicode characters are compatible if they share the same semantics in at least some situation.
U+FB00 (the typographic ligature "ﬀ") and U+0066 U+0066 (two Latin "f" letters) are two characters that are compatible.
Canonical equvalency is a subset of compatibility.
two unicode characters are canonically equivalent if they display the same and have the same meaning.
Two canonically equivalent characters should be treated in the same way by (pretty much) every program.
Unicode normalization takes two texts that are canonically equivalent or compatible and reduces them to the same sequence of codepoints.

#### directionality

In unicode, strongly typed characters have an associated direction (LTR or RTL)
In unicode, characters are strongly typed, or are neutral/weak.
The unicode-bidi algorithm produces directional runs of sequences of characters of contiguous characters with same directionality.
neutral characters become part of the same directional run between two strongly typed characters of the same direction.
In unicode, characters like punctuation, spaces and numbers are weak.
neutral characters between two strongly typed characters of opposite directions become part of the directional run become part of the run in the inline base direction.
‹bdo› is for the cases in which you don't want the bidirectional algorithm to anything at all, e.g. if you want to show the order of characters in memory.
‹bdi› is for wrapping text whose directionality you can't predict, but which you don't want to absorb neutral characters on other sides.
If one knows the directionality in advance, one doesn't need ‹bdi› to isolate an element from the bidi algorithm all, one can just add a span or whater with a dir attribute to force the directionality and isolate at the same time.

#### policy

Unicode follows a number of policies
Unicode encoding stability policy|Once a character is encoded, it will not be moved or removed

#### encodings

UTF|Unicode Translation Formats
There are three main unicode encodings: UTF-32, UTF-16 and UTF-8
UTF-32 encodes any codepoint as 4 bytes, and is thus very wasteful for something like latin text.
UTF-8 may take 1-4 bytes to encode a cahracter.

Today, most things default to UTF-8, however a few things such as JS and Java default to UTF-16.

##### UTF-16

UTF-16 consists of 16-bit code units.
An unicode code point encoded with UTF-16 may consist of one or two code units
UTF-16 requires one code unit(s) for things in the BMP, and two code unit(s) for anything else
if UTF-16 needs ⟮two code units⟯, these ⟮two code units⟯ are called ⟮a surrogate pair⟯
In surrogate pairs (UTF-16) the code unit that should come ⟮first⟯ is called the ⟮high surrogate⟯, the code unit that should come ⟮second⟯ is called the ⟮low surrogate⟯
⟮High-surrogate⟯ code units have a hex value ⟮0xD800-0xDBFF⟯

##### UTF-8

UTF-8 guaranteees that there would never be 8 subsequent zeroes, as that could be interpreted as 0x00, which would end an null-terminated string (and thus could produce bugs or even allow injection attacks)
UTF-8 encodes the 128 ASCII characters the same way as ASCII, but with a leading zero (since 8 not 7 bit)
First UTF-8 byte starts|character contains n bytes
0|1
110|2
1110|3
11110|4
Any UTF-8 byte but the first starts 10
To encode a character in UTF-8, first we determine how many bit the character requires, then we set the appropriate first byte header, and then insert the binary code point starting from the less significant end, finally filling up empty spaces with 0s.
7›|1
8-11|2
12-16|3
17-21|4


##### Percent

(near) synonyms: ⟮Percent encoding⟯, ⟮URL/I encoding⟯

To percent-encode a character, use the characters UTF-8 representation, and then percent-encode each byte.
percent-encoded-byte ::= %‹hex-digit›‹hex-digit›

Newline may refer to the newline character or any newline

even?|Is the thing even|Integer
next|get the next element|Integer, String
class|get the class this is an object of|any object
methods|get the methods the object has|any object

An aspect is a cross-cutting concern.
A cross-cutting concerns is a common feature that's typically scattered across methods, classes, object hierarchies, or even entire object models.
Examples for a cross-cutting concern might be logging.

Case-preservation is whether something ⟮stores or disregards case information⟯
Case-sensitivity is whether something ⟮differentiates based on case⟯

# more misc

A bricked device is one that no longer can function at all (has become as useful as a brick)
SKU|Stock Keeping Unit
An instance is something that has been created on some sort of model.

# placeholder images

Placeholder images using kittens|placekitten.com
Placeholder images using boring boxes|via.placeholder.com

via.placeholder.com/⟮width⟯[⟮x⟯⟮height⟯]
placekitten.com/⟮width⟯⟮/⟯⟮height⟯

# some internet/js stuff

{{c1::web app manifests}} are usually called {{c2::manifest}}.{{c3::webmanifest}}/.{{c3::json}}
{{c1::Progressive web app}} is not {{c2::an official term}}, but refers to creating {{c3::a flexible, adaptable app}} using {{c4::web technologies}} (though {{c5:: there have been a few technologies that have become very intertwined with it (service workers, web app manifests, etc.)}})
within a web app manifest,&nbsp; the <code>{{c1::scope}}</code> property manages {{c2::which URLs are considered to be within your app}}
within a web app manifest, you must provide {{c2::at least one}} of {{c1::<code>short_name</code>}} or {{c1::<code>name</code>}}, which appear {{c3::in the installation screen}} and {{c3::most other places where space is limited}}, respectively
within a web app manifest, the <code>{{c1::start_url}}</code> property is used to determine {{c2::from where the app starts}}
within a web app manifest, the <code>{{c1::icons}}</code> property is an {{c2::array}} of {{c2::objects}}, each representing {{c3::an icon for launchers, etc.}}
within a web app manifest, the <code>{{c1::display}}</code> property is used to determine {{c2::how the apps start (e.g. in fullscreen / back buttons, etc.)}}
within a web app manifest, the <code>{{c1::background_color}}</code> property is mainly used for {{c2::the startup splash screen}}
within a web app manifest, for the <code>{{c1::display}}</code> property <code>{{c2::fullscreen}}</code> shows {{c6::no UI}}, <code>{{c3::standalone}}</code> shows {{c6::only the OS UI (works as a normal app would)}}, <code>{{c4::minimal-ui}}</code> {{c7::additionally shows some nav elements (back/reload) but no address bar}}, and <code>{{c5::browser}}</code> {{c7::gives you a standard browser experience}}
within a web app manifest, each object within the array of&nbsp;<code>{{c1::icons}}</code> property can have the keys {{c2::sizes}}, {{c3::src}}, {{c4::type}}, and {{c5::purpose (esp. used for adapting e.g. to monochrome or maskable icons)}}
The {{c1::web app manifest}} is a {{c2::JSON}} file that tells the browser about your {{c3::Progressive Web App}} and how it {{c4::should behave}}&nbsp;when {{c5::installed on the user's desktop or mobile device.}}

{{c1::Object.fromEntries}} takes an argument that is an {{c2::iterator}} of {{c3::[key, value]}} and {{c4::transforms it into an object&nbsp;}}

{{c1::CacheStorage (normally as <code>caches</code>).open(somename)}}&nbsp;returns {{c4::a Promise}} that resolves to {{c5::the Cache object}} matching {{c2::the name passed}}, or {{c3::creates it if it does not exist}}
{{c1::CacheStorage (normally as <code>caches</code>).match(someRequest)}} is a convenience method that looks if {{c2::the someRequest is cached}} in {{c3::any of the caches}}
the <code>{{c1::Cache}}</code> interface is meant to store <code>{{c2::Request}}</code> / <code>{{c2::Response}}</code> pairs
since there can be more than one <code>Cache</code>, you {{c1::get a specific <code>Cache</code>}}&nbsp;via the <code>{{c2::CacheStorage}}</code> interface, which can be accessed via {{c3::the global <code>caches</code> property}}
for the Cache API, the {{c1::retrieval}} functions are {{c2::match}} for a {{c4::single item}} and {{c2::match}}{{c3::All}} for {{c4::an array}}. Arguments are ({{c5::request}}, {{c5::options}})
for the Cache API, the {{c1::add}}/{{c1::addAll}} methods take a {{c2::request object}}, {{c3::fetch the response}}, and then {{c4::add the response to the cache}}.
for the Cache API, if something {{c2::returns something}}, it does so in the form of {{c1::a promise}}
What is the Cache API/interface distinct from? <span class="divider">-></span> {{c1::HTTP caching}}
By whom is the <code>Cache</code> managed? <span class="divider">-></span> {{c1::primarily by you, the dev}}<br/><div class="sub">
<div class="sub c1-f c2-b" >
the one that stores Request / Response object pairs
</div>
</div>

what do we pass to process.nextTick() to be executed at the end of the current message? <span class="divider">-></span> {{c1::a callback}}

to define {{c1::app shortcuts}}, use the {{c2::shortcuts}} property in the web manifest
((h:all;::<img src="F4TsJNfRJNJSt2ZpqVAy.png">))

to create a new thing using a constructor, use what? <span class="divider">-&gt;</span> {{c1::the <code>new</code> keyword}}
the <code>__proto__</code> property refers to what? <span class="divider">-&gt;</span> {{c1::the prototype of the current object}}
null sits where, as relates to the prototype chain? <span class="divider">-&gt;</span> {{c1::at the top}}
if you want to use the constructor of a given object <q>someObject</q>, what do you call? <span class="divider">-&gt;</span> {{c1::<code>new someObject.constructor()</code>}}
getPrototypeOf() gets what? <span class="divider">-&gt;</span> {{c1::the actual prototype (__proto__)}}
__proto__ is nice to access the prototype, but is what...? <span class="divider">-&gt;</span> {{c1::non-standard}}
Why do functions have properties, how is that even possible? <span class="divider">-&gt;</span> {{c1::functions are Objects}}
Whose <code>prototype</code> property contains the constructor property? <span class="divider">-&gt;</span> {{c1::that of a constructor function}}<br><div class="sub">
<div class="sub c1-b c2-f">
but isn't anything that has this property automatically a constructor???????
</div>
</div>
Which JS methods <b>will</b> be inherited by things that are instances of from the relevant thing? <span class="divider">-&gt;</span> {{c1::things defined on the <code>prototype</code> property}}
Which JS methods <b>will not</b>&nbsp;be inherited by things that instantiate the relevant thing? <span class="divider">-&gt;</span> {{c1::things defined on the thing directly}}
Where can you find the constructor that was used to create a given object? <span class="divider">-&gt;</span> {{c1::its constructor property (which it is actually on its __proto__, as you would expect)}}
When will JS walk up the prototype chain to find a method? <span class="divider">-&gt;</span> {{c1::if the relevant Object does not have it}}
What's the problem of declaring properties on the constructor prototype? <span class="divider">-&gt;</span> {{c1::<code>this</code> will not have the correct scope}}
What sits at the top of the prototype chain? <span class="divider">-&gt;</span> {{c1::null}}
What is super confusing abut the <code>prototype</code> property in JS? <span class="divider">-&gt;</span> {{c1::it does not refer to the actual prototype -.-}}
What does the 2nd-to-top element of the prototype chain have as its prototype? <span class="divider">-&gt;</span> {{c1::<font face="monospace">null}}
What does the  <code>prototype</code> property of a constructor function definitely contain? <span class="divider">-&gt;</span> {{c1::the constructor property}}
What are JS functions actually, internally? <span class="divider">-&gt;</span> {{c1::Objects}}
The whole class syntax is what, related to how JS inheritance and objects actually work? <span class="divider">-&gt;</span> {{c1::syntactic sugar}}
The methods defined in the <code>prototype</code> property have what characteristic?  <span class="divider">-&gt;</span> {{c1::Will be inherited}}
The fact that if an object has a property with a certain name, properties with the same name further up the prototype chain will not be visited is known as what? <span class="divider">-&gt;</span> {{c1::prototype shadowing}}<br><div class="sub">
<div class="sub c1-b c2-f">
cf name shadowing
</div>
</div>
The <code>prototype</code> does not refer to the prototype of an object, instead, what does? <span class="divider">-&gt;</span> {{c1::the <code>__proto__</code> property}}
More standard way to access the actual prototype of the Object? <span class="divider">-&gt;</span> {{c1::getPrototypeOf()}}
If you want to find out what the name of the constructor function that someObject was created with is, what would you do? <span class="divider">-&gt;</span> {{c1::<code>someObject.constructor.name</code>}}<br><div class="sub">
<div class="sub c1-b c2-f">
which is obv not defined on someObject itself, but further up the prototype chain
</div>
</div>
If we wanted to delete a method from all instances of something, where would we remove it from? <span class="divider">-&gt;</span> {{c1::the prototype of the constructor function (or the __proto__ of any of the objects, since someObj.__proto__ == constructorOfObj.prototype)}}
If we wanted all instances of something to gain a method, where would we add it? <span class="divider">-&gt;</span> {{c1::the prototype of the constructor function}}
If we delete something from the prototype of the constructor, where is it deleted? <span class="divider">-&gt;</span> {{c1::from all instances}}
If we call a method on something that doesn't have that method, what does JS do? <span class="divider">-&gt;</span> {{c1::walk up the prototype chain until it finds it}}
If we add something to the prototype of the constructor, who can then access it? <span class="divider">-&gt;</span> {{c1::any instance}}
<div class="c2-f">
What does this sometimes also indicate?
</div><div class="c1-f">
How is this sometimes indicated, esp in ECMAScript design documents?
</div><br>{{c1::[[Prototype]]}}  <span class="divider">&lt;-&gt;</span> {{c2::the actual prototype}}
having prototypes of prototypes in JS establishes what? <span class="divider">-&gt;</span> {{c1::the prototype chain}}
What is the prototype chain? <span class="divider">-&gt;</span> {{c1::the prototypes of prototypes (__proto__) etc.}}
The mechanism that handles JS inheritance is what? <span class="divider">-&gt;</span> {{c1::prototype}}
if bar's <code>prototype</code> property is foo's prototype (__proto__), then... <span class="divider">-&gt;</span> {{c1::foo is an instance of bar}}
When does a function become a constructor? <span class="divider">-&gt;</span> {{c1::When it is called with the new operator}}
What is the performance impact of traversing the prototype chain? <span class="divider">-&gt;</span> {{c1::can be signifcant}}
What do almost all JS objects inherit from? <span class="divider">-&gt;</span> {{c1::Object.prototype}}
What do all functions inherit from? <span class="divider">-&gt;</span> {{c1::Function.prototype}}
What are almost all JS objects instances of? <span class="divider">-&gt;</span> {{c1::Object}}
What are all arrays instances of (directly)? <span class="divider">-&gt;</span> {{c1::Array}}
The first argument Object.create takes is... <span class="divider">-&gt;</span> {{c1::the prototype (__proto__) it will have&nbsp;}}
In JS, foo is an instance of bar if bar's what is foo's what? <span class="divider">-&gt;</span> {{c1::bar's <code>prototype</code> property is foo's prototype (__proto__)}}
Function.prototype has what as it's prototype (__proto__)? <span class="divider">-&gt;</span> {{c1::Object.prototype}}
For Object.create, the thing to use as prototype (__proto__) goes where? <span class="divider">-&gt;</span> {{c1::first argument}}
Creating an object and specifying which prototype (__proto__) you want explicitly is done how? <span class="divider">-&gt;</span> {{c1::Object.create}}
Any function that you call with the new operator is what, in JS? <span class="divider">-&gt;</span> {{c1::a constructor}}
A constructor is what which you call with the new operator? <span class="divider">-&gt;</span> {{c1::a function}}
<div class="c2-f">
Object.prototype method for?
</div><div class="c1-f">
Object.prototype method for?
</div><br>{{c1::hasOwnProperty}}  <span class="divider">&lt;-&gt;</span> {{c2::seeing if the property is not inherited or inherited}}
<div class="c1-f">
What will this be?
</div><br>Object.create(Array.prototype).__proto__
 <span class="divider">-&gt;</span> {{c1::Array.prototype including methods such as push...}}
<div class="c1-f">
What will Array.prototype be to the newly created object?
</div><br>Object.create(Array.prototype) <span class="divider">-&gt;</span> {{c1::__proto__}}</font>
Which kind of functions do not have a <code>prototype</code> property? <span class="divider">-&gt;</span> {{c1::arrow functions}}<br><div class="sub">
<div class="sub c1-b c2-f">
which is why they can't be used as constructors
</div>
</div>
Which <b>kind of </b>functions <b>can</b> you call with <code>new</code> to create a new instance? <span class="divider">-&gt;</span> {{c1::any function that is not an arrow function}}
When you create an object with object literal syntax in JS, what is its prototype (__proto__)? <span class="divider">-&gt;</span> {{c1::Object.prototype}}
When you create an object with object literal syntax in JS, what constructor is used? <span class="divider">-&gt;</span> {{c1::the Object() constructor}}
When functions are being used as constructors, where will the objects created by them have the things that were defined on constructor.prototype? <span class="divider">-&gt;</span> {{c1::their prototype (__proto__)}}
When functions are being used as constructors, the prototype of the constructor function becomes what?  <span class="divider">-&gt;</span> {{c1::the prototype (__proto__) of the new object }}
When functions are being used as constructors, the prototype (__proto__) of the new object will be equal to what? <span class="divider">-&gt;</span> {{c1::the <code>prototype</code> of the constructor function}}
What sits at the second position of the prototype chain, below null? <span class="divider">-&gt;</span> {{c1::Object.prototype}}
Object.prototype sits where, as relates to the prototype chain? <span class="divider">-&gt;</span> {{c1::one below the top (below null)}}
If you don't {{c1::supply a constructor to a <code>class</code> declaration}}, <span class="c4-5-scr">the constructor will be {{c2::an empty constructor}} if it is a {{c3::base class}}</span>, and <span class="c2-3-scr">{{c4::one that just calls the constructor of the parent class}} if it is a {{c5::derived class}}</span>.
Array.prototype has what as it's prototype (__proto__)? <span class="divider">-&gt;</span> {{c1::Object.prototype}}
Any given function has what as its prototype  (__proto__)? <span class="divider">-&gt;</span> {{c1::Function.prototype}}<br><div class="sub">
<div class="sub c1-b c2-f">
which itself has a __proto__ of Object.prototype
</div>
</div>
Any given array has what as its prototype (__proto__)? <span class="divider">-&gt;</span> {{c1::Array.prototype}}<br><div class="sub">
<div class="sub c1-b c2-f">
which itself has a __proto__ of Object.prototype
</div>
</div>
<div class="c1-f">
Why doesn't this work?
</div><br><pre><code>let temp = () =&gt; 5;
new temp;</code></pre> <span class="divider">-&gt;</span> {{c1::arrow functions cannot be used as constructors}}
The <code>typeof</code> things like <code>Array</code>, <code>Object</code>, <code>Function</code> is what? <span class="divider">-></span> {{c1::function}}<br/><div class="sub">
<div class="sub c1-b c2-f" >
they are classes (in a sense) but classes are functions
</div>
</div>

to add something to the evenet queue of another runtime, what method can one use? <span class="divider">-></span> {{c1::window.postMessage()}}

the {{c3::deviceorientation}} event contains four values, {{c1::absolute}}, {{c2::alpha}}, {{c4::beta}}, and {{c5::gamma}}
for the deviceorientation events, the things they can be relative to is the {{c1::screen}} on your mobile device, and the {{c2::keyboard}} on your laptop (generally)
Why might your laptop have acceleration sensors? <span class="divider">-></span> {{c1::protect HDD when fallign}}
<div class='c2-f'>
represents orientation changes where?
</div><div class='c1-f'>
Orientation changes around this axis are represented by what?
</div><br/>((h:all;::<img src="sm_beta2.png">)){{c1::beta (of deviceorientation event)}}  <span class="divider">&lt;-&gt;</span> {{c2::around the x axis&nbsp;}}
<div class='c2-f'>
represents orientation changes where?
</div><div class='c1-f'>
Orientation changes around this axis are represented by what?
</div><br/>((h:all;::<img src="sm_alpha.png">)){{c1::alpha (of deviceorientation event)}}  <span class="divider">&lt;-&gt;</span> {{c2::around the z axis}}
<div class='c2-f'>
represents orientation changes where?
</div><div class='c1-f'>
Orientation changes around this axis are represented by what?
</div><br/>((h:all;::<img src="gamma.png">)){{c1::gamma (of deviceorientation event)}}  <span class="divider">&lt;-&gt;</span> {{c2::around the y axis&nbsp;}}
<div class='c2-f'>
Is an event sent when?
</div><div class='c1-f'>
Which event is sent in this case?
</div><br/>{{c1::deviceorientation}}  <span class="divider">&lt;-&gt;</span> {{c2::Device orientation changes (in alpha, beta, gamma)}}
<div class='c2-f'>
Is an event sent when?
</div><div class='c1-f'>
Which event is sent in this case?
</div><br/>{{c1::devicemotion}}  <span class="divider">&lt;-&gt;</span> {{c2::moving your device (accelerometer changes)}}

the {{c1::define()}} method of window.customElements takes the arguments 1) {{c2::what the name of the element will be}}, 2) the {{c3::class}} that will {{c4::define its behavior}}, 3) (optional) an {{c5::object}} {{c6::specifying what it extends}}
The two types of custom elements are customized built-in elements and... <span class="divider">-&gt;</span> {{c1::autonomous custom elements}}
The two types of custom elements are autonomous custom elements and... <span class="divider">-&gt;</span> {{c1::customized built-in elements}}
In general, regardless of what, the class defining a custom element should at least extend something like HTMLElement? <span class="divider">-&gt;</span> {{c1::the extends parameter (3rd arg to define)}}
In general, regardless of the extends parameter (3rd arg to define), the class defining a custom element should do what? <span class="divider">-&gt;</span> {{c1::(at least) extend something like e.g. HTMLElement}}
<div class="c2-f">
You would use these in html how?
</div><div class="c1-f">
Custom elements you use like this are what kind of custom elements?
</div><br>{{c1::customized built in elements, e.g. foo-bar that extends p}}  <span class="divider">&lt;-&gt;</span> {{c2::&lt;p is="foo-bar"&gt;&lt;/p&gt;}}
<div class="c2-f">
You would use these in html how?
</div><div class="c1-f">
Custom elements you use like this are what kind of custom elements?
</div><br>{{c1::autonomous custom elements, e.g. foo-bar}}  <span class="divider">&lt;-&gt;</span> {{c2::&lt;foo-bar ...&gt;&lt;/foo-bar&gt;}}
<div class="c2-f">
What kind of element are you specifying in this case?
</div><div class="c1-f">
what about your call to define() specifies if it is this or not?
</div><br>{{c1::if you<b>&nbsp;do not</b> specify the 3rd argument to customElements.define (the one with extends)}}  <span class="divider">&lt;-&gt;</span> {{c2::an autonomous custom element}}
<div class="c2-f">
What kind of element are you specifying in this case?
</div><div class="c1-f">
what about your call to define() specifies if it is this or not?
</div><br>{{c1::if you specify the 3rd argument to customElements.define (the one with extends)}}  <span class="divider">&lt;-&gt;</span> {{c2::a customized built-in element}}
<div class="c2-f">
Function of window.customElements for?
</div><div class="c1-f">
Function of window.customElements for?
</div><br>{{c1::define()}}  <span class="divider">&lt;-&gt;</span> {{c2::definining a new custom element}}
<div class="c1-f">
what's the problem with this custom element?
</div><br>&lt;wordcount&gt; <span class="divider">-&gt;</span> {{c1::must include at least a -&nbsp;}}
<div class="c1-f">
have what restriction in their name?
</div><br>custom elements <span class="divider">-&gt;</span> {{c1::must include at least one -}}

the {{c1::ExtendableEvent}} interface has a method {{c2::waitUntil}}(), which prevents the service worker from being treated as {{c4::successfully installed}} until {{c3::the passed promise resolves successfully}}<br/><div class="sub">
 This is primarily used to ensure that a service worker is not considered installed until all of the core caches it depends on are populated.
</div>

the {{c1::ExtendableEvent.waitUntil}}() method is mainly used so that the service worker is not {{c2::considered installed}} until {{c3::all the caches it needs are populated}}.

the promise job/microtask queue (also has other names) is a secondary queue that will run when? <span class="divider">-></span> {{c1::as soon as the current message is processed (or otherwise soon, the specs aren't in agreement/clear)}}

the primary use of the {{c1::activate}} event of service workers is to {{c2::clean up}} from {{c3::a previous service worker}}
If your service worker has {{c1::previously been installed}}, and then a {{c2::new version}} of the worker is available on {{c3::refresh or page load}}, the new version is {{c4::installed in the background}}, but not {{c5::yet activated}}.
After a service worker is {{c1::active}} and the user {{c2::navigates to a different page}} or {{c2::refreshes}}, the {{c3::service worker}} will begin to receive {{c4::fetch}} events

the parameters taken by {{c1::fetch()}} and the {{c2::Request constructor}} are {{c3::identical}} (except that you can pass a {{c2::Request}} object to {{c1::fetch}} {{c4::instead of the 'proper' parameters}})
<div class='c2-f'>
fetch()/new Request() key for?
</div><div class='c1-f'>
fetch()/new Request() key for?
</div><br/>{{c1::method}}  <span class="divider">&lt;-&gt;</span> {{c2::the HTTP method to use}}
<div class='c2-f'>
fetch() options object/new Request() key for?
</div><div class='c1-f'>
fetch() options object/new Request() key for?
</div><br/>{{c1::headers}}  <span class="divider">&lt;-&gt;</span> {{c2::the headers to use}}
<div class='c2-f'>
Response (returned via the fetch api) property for?
</div><div class='c1-f'>
Response (returned via the fetch api) property for?
</div><br/>{{c1::Response.status}}  <span class="divider">&lt;-&gt;</span> {{c2::HTTP status code}}
<div class='c2-f'>
Response (returned via the fetch api) property for?
</div><div class='c1-f'>
Response (returned via the fetch api) property for?
</div><br/>{{c1::Response.ok}}  <span class="divider">&lt;-&gt;</span> {{c2::whether the status code was ok (200-299)}}
<div class='c2-f'>
Response (returned via the fetch api) property for?
</div><div class='c1-f'>
Response (returned via the fetch api) property for?
</div><br/>{{c1::Response.headers}}  <span class="divider">&lt;-&gt;</span> {{c2::The HTTP headers returned}}
<div class='c2-f'>
Response (returned via the fetch api) property for?
</div><div class='c1-f'>
Response (returned via the fetch api) property for?
</div><br/>{{c1::Response.body}}  <span class="divider">&lt;-&gt;</span> {{c2::body returned}}

the little secondary queue that will (probably) run after the current function finishes? <span class="divider">-></span> {{c1::Promise job/microtask queue}}

the callback provided to http.createServer (that reacts to request events) is provided two objects when called, a {{c1::http.IncomingMessage}} object, and a {{c2::http.ServerResponse}}

the <code>{{c1::install}}</code> and <code>{{c1::activate}}</code> events of service workers are/conform to the interface <code>{{c2::ExtendableEvent}}</code>

setImmediate() is similar to {{c2::process.nextTick()}} but {{c1::runs later (with lower priority)}}

process.nextTick(callback) adds things to be executed when? <span class="divider">-></span> {{c1::at the end of the current message}}

precedence of <b>nodejs</b> queues: {{c1::process.nextTick}} queue &gt; {{c2::promises microtask}} queue &gt; {{c3::setTimeout (with a timeout of 0)}} queue ≈ {{c4::setImmediate}} queue

often, it makes sense to use templates as what? <span class="divider">-></span> {{c1::the shadow dom of custom elements}}
attachShadow takes an argument which is what? <span class="divider">-></span> {{c1::an options object}}<br/><div class="sub">
<div class="sub all-b">
yes, it doesn't take an argument of a shadow tree to directly attach, you have to do that later
</div>
</div>
attachShadow takes an argument which is an options object with the key(s)? <span class="divider">-></span> {{c1::mode}}
You can access the {{c3::shadow root}} of an element via {{c2::the shadowRoot property (of any given element)}}, but only if {{c1::its mode = "open"}}
When rendering, what happens to the shadow tree? <span class="divider">-></span> {{c1::it's attached at the shadow host}}
What kind of elements already use the shadow DOM in the background? <span class="divider">-></span> {{c1::things like &lt;video&gt; (e.g. its controls)}}
To what can you attach a shadow root? <span class="divider">-></span> {{c1::any <code>Element</code>}}
Once you've created a shadow root, how do you add children etc? <span class="divider">-></span> {{c1::just as you would for any normal DOM element}}
Method of any <code>Element</code> to attach a shadow root? <span class="divider">-></span> {{c1::attachShadow}}
<div class='c2-f'>
What would you use?
</div><div class='c1-f'>
Allows us to do what?
</div><br/>{{c1::To encapsulate part of the DOM}}  <span class="divider">&lt;-&gt;</span> {{c2::the shadow DOM}}
<div class='c2-f'>
Is known as what?
</div><div class='c1-f'>
Is what?
</div><br/>{{c1::the root node of the shadow DOM}}  <span class="divider">&lt;-&gt;</span> {{c2::a shadow root}}
<div class='c2-f'>
Is known as what?
</div><div class='c1-f'>
Is what?
</div><br/>{{c1::the point where the regular DOM ends ant the shadow DOM begins}}  <span class="divider">&lt;-&gt;</span> {{c2::shadow boundary}}
<div class='c2-f'>
Is known as what?
</div><div class='c1-f'>
Is what?
</div><br/>{{c1::the dom node that a shadow DOM is attached to}}  <span class="divider">&lt;-&gt;</span> {{c2::a shadow host}}
<div class='c2-f'>
Is known as what?
</div><div class='c1-f'>
Is what?
</div><br/>{{c1::the DOM tree inside the shadow DOM}}  <span class="divider">&lt;-&gt;</span> {{c2::the shadow tree}}
<div class='c2-f'>
Does what?
</div><div class='c1-f'>
How do we do this, for a given shadow root?
</div><br/>{{c1::the mode option&nbsp;}}  <span class="divider">&lt;-&gt;</span> {{c2::specifies if JS written in the main page can access it}}<br/><div class="sub">
<div class='sub f'>
of the options object of attachShadow
</div>
</div>
Why might you want to use web components without the shadow DOM, for example? <span class="divider">-></span> {{c1::e.g. you <i>want</i>&nbsp;styles to propagate}}
The {{c1::normal DOM}}, when {{c2::in contrast to the shadow DOM}}, is sometimes called {{c3::the light DOM}}?
During composition, things with {{c1::slot="foo"}} replace {{c3::slots}} with {{c2::name="foo"}} in the {{c4::shadow DOM}}.
<div class='c2-f'>
go where?
</div><div class='c1-f'>
What things related to slots are here?
</div><br/>{{c1::&lt;slot&gt; elements}}  <span class="divider">&lt;-&gt;</span> {{c2::somewhere within the shadow DOM}}
<div class='c2-f'>
Are problems that what solves?
</div><div class='c1-f'>
What are some exampls of problems that this solves?
</div><br/>{{c1::competing styles, multiple IDs}}  <span class="divider">&lt;-&gt;</span> {{c2::the shadow DOM}}
If there are multiple elements in light DOM {{c1::with the same slot name}}, they are {{c2::appended into the slot, one after another}}.
<div class='c2-f'>
go/are in(to) which DOM?
</div><div class='c1-f'>
What things related to slots are here?
</div><br/>{{c1::elements with slot="something"}}  <span class="divider">&lt;-&gt;</span> {{c2::are in the light DOM}}

no matter what {{c1::optional chaining}} you use, if you {{c2::call}} a thing as {{c2::a method}} that is {{c2::in fact a property}} you will always get {{c3::a TypeError}}

for await of allows you to iterate over an {{c2::async iterable object}}, to use it, insert {{c1::an await between for and the rest of the iteration statement}}

Why will a tab freeze if you run code that takes very long?  because JS is single threaded and thus has to process the message to comopletion
Why is the timeout we give setTimeout only a minimum time?  because its put at the end of the message queue and thus might take longer
Why are we guaranteed that the things we are using from our function will not change 'behind our backs' while the function is running?  because we will always finish processing the curreent message (and thus the current stack contents) before we do anything else
When the event loop processes a message in the message queue, what does it do?  calls the corresponding function
What runs on JS's single thread hosts the event loop.
The event loop processes the message queue
Once the event loop has called the function of a message, when is it done?  when the call stack is empty
Once the event loop has called the function of a message, what will it do with subsequent function calls within?  new stack frame on the stack
In JS, stack frames are called execution contexts. 
Each execution context contains a scope chain, which is a lists of lexical scopes from inner to outer.
A lexical environment is a structure that holds identifiers and the variables/functions they refer to.
What does setTimeout do with its function argument? (JS-internal view)  adds a new message with this function at the end of the message queue
What does each  message in the message queue have associated with it?  a function
Until the stack is empty, what can't we do?  start processing a new message
In browsers generally each tab has  its own heap, stack and message queue
If there's something on the stack, then what are we doing?  processing a message in the message queue
How is JS threaded?  single-theaded
Besides the heap and call stack, what does JS also have, as a core part of the implementation?  the message queue

Why can't you misformat something using prettier? <span class="divider">-&gt;</span> {{c1::since it formats your code automatically}}
Which languages does prettier support? <span class="divider">-&gt;</span> {{c1::a lot of different web-related ones (JS, Angular, Vue, JSX, CSS, SCSS, JSON, YAML etc. etc.)}}
What does prettier do with the stuff you give it? <span class="divider">-&gt;</span> {{c1::formats it according to its rules}}

What should you definitely do when reacting to the activate event in service workers? <span class="divider">-></span> {{c1::remove old caches}}

What do we do with the content templates in JS, so we can use it elswhere (without fucking the template up)? <span class="divider">-></span> {{c1::call cloneNode on it}}

To {{c1::add something to the microtask queue}}, use {{c2::queueMicrotask()}}.

To do stuff in the service worker once {{c2::it's been installed}}, add an event listener for the {{c1::<code>install</code>}} event.<br/><div class="sub">
<div class="sub all-b"><pre><code>self.addEventListener('install', function(event) {
  // Perform install steps
});</code></pre></div>
</div>

The {{c1::first contentful paint}} is when the {{c2::first piece of DOM content}} (which elements are exactly considered is more complicated) loaded, relative to {{c3::when the page first started loading}}

The {{c1::Push}} API&nbsp;allows web apps to get messages {{c2::pushed from a server}}, whether or not the web app is {{c3::in the foreground / even currently loaded}}

JSON Schema:
<pre><code>  ...
  "type": {{c1::"object"}},
  {{c2::"properties"}}: {
    "productId": {
      "description": "The unique identifier for a product",
      "type": "integer"
    }
  },</code></pre>
JSON Schema toplevel: 
<pre><code>{
  {{c1::"$schema"}}: "https://json-schema.org/draft/2020-12/schema",
  {{c2::"$id"}}: "https://example.com/product.schema.json",
  {{c3::"title"}}: "Product",
  {{c4::"description"}}: "A product in the catalog",
  {{c5::"type"}}: ...
}</code></pre>

Internally, a Promise has the properties {{c1::[[PromiseState]]}} and {{c2::[[PromiseResult]]}}

Instead of writing key: function(... for methods, what can you write, in ES6? <span class="divider">-></span> {{c1::key(...}}

If you add a new service worker, what might you do with the <code>Cache</code> used? <span class="divider">-></span> {{c1::use a new <code>Cache</code>}}<br/><div class="sub">
<div class="sub c1-f" >
esp. if they are incompatible
</div>
</div>

If we take a function, e.g. {{c1::a method}} of {{c1::an object}}, and {{c2::assign it to e.g. a variable}} (or {{c2::pass it as a param}}), and then {{c4::call it later}}, it will use {{c3::whatever <code>this</code> is in scope}}, instead of {{c3::the <code>this</code>}}&nbsp;of {{c1::the object}} or similar

Function to set an attribute (e.g. href) on an <code>Element</code>? <span class="divider">-></span> {{c1::setAttribute}}
Function to remove an attribute (e.g. href) from an <code>Element</code>? <span class="divider">-></span> {{c1::removeAttribute}}
Function to get an attribute (e.g. href) from an <code>Element</code>? <span class="divider">-></span> {{c1::getAttribute}}

Function to add things to be executed at the end of the current message? <span class="divider">-&gt;</span> {{c1::process.nextTick(callback)}}

CORS|Cross-Origin Resource Sharing

<div class='c2-f'>
method for?
</div><div class='c1-f'>
does what?
</div><br/>{{c1::Object.entries(someObj)}}  <span class="divider">&lt;-&gt;</span> {{c2::get array of [key, value] pairs}}

<div class='c2-f'>
Function of window.customElements for?
</div><div class='c1-f'>
Function of window.customElements for?
</div><br/>{{c1::whenDefined(foo)}}  <span class="divider">&lt;-&gt;</span> {{c2::get a promise that resolves when foo is defined}}
<div class='c2-f'>
Function of window.customElements for?
</div><div class='c1-f'>
Function of window.customElements for?
</div><br/>{{c1::get(foo)}}  <span class="divider">&lt;-&gt;</span> {{c2::get the constructor of the custom element named foo}}

<div class='c1-f'>
Why do round braces prevent this from being treated as a block statement with no return value?
</div><br/><pre><code>var func = () =&gt; <span class="">({</span> foo: 1 <span class="">})</span>;</code></pre> <span class="divider">-></span> {{c1::Because round braces don't go around block statements, and so the parser concludes it must be an object literal.}}

<div class='c1-f'>
Is an API for what?
</div><br/>{{c1::JS api for form validation}}  <span class="divider">&lt;-&gt;</span> {{c2::Constraint validation API}}

<div class='c1-f'>
How do we react to the service worker being created?
</div><br/><pre><code> navigator.serviceWorker.register('/example/sw.js')</code></pre> <span class="divider">-></span> {{c1::via a then() (or any other way we can respond to a promise)}}

((h:all;::<img src="appshell.png">))An {{c1::app shell}} is a way to build a {{c2::PWA}} and involves {{c4::aggressively caching}}&nbsp; {{c3::the common UI}} and {{c4::dynamically loading}} {{c3::the content}} using JS

((h:all;::<img src="8mkBdT3O0FZLo0PUppvv.png">))within a web app manifest,&nbsp; the <code>{{c1::theme_color}}</code> property manages {{c2::the color of the bars/notification shade, etc.}}

# various

{{c3::&lt;template&gt;}} contains HTML that won't {{c1::be rendered immediately}}, but {{c2::can be used from JS (often multiple times)}}
<div class="c2-f">
pseudo-class that matches what?
</div><div class="c1-f">
Are matched how?
</div><br>{{c1:::part(foo)}}  <span class="divider">&lt;-&gt;</span> {{c2::element within shadow tree that has part="foo"}}
<div class="c2-f">
pseudo-class that matches what?
</div><div class="c1-f">
Are matched how?
</div><br>{{c1:::host}}  <span class="divider">&lt;-&gt;</span> {{c2::selects shadow hosts}}<br><div class="sub">
<div class="sub c2-b c1-f">
(a regular DOM node that the shadow DOM is attached to.)
</div>
</div>
<div class="c2-f">
pseudo-class that matches what?
</div><div class="c1-f">
Are matched how?
</div><br>{{c1:::host-context(some-selector)}}  <span class="divider">&lt;-&gt;</span> {{c2::selects shadow host which has a <b>ancestor!!!!</b> some-selector}}<br><div class="sub">
<div class="sub all-b">
:host-context(.mine) matches
<pre><code>&lt;h1 class="mine"&gt;
  ...
    &lt;some-shadow-host&gt;</code></pre>
</div><div class="sub c2-b c1-f">
(a regular DOM node that the shadow DOM is attached to.)
</div>
</div>
<div class="c2-f">
pseudo-class that matches what?
</div><div class="c1-f">
Are matched how?
</div><br>{{c1:::host(some-selector)}}  <span class="divider">&lt;-&gt;</span> {{c2::selects shadow host which matches some-selector}}<br><div class="sub">
<div class="sub all-b">
:host(.mine) matches &lt;some-shadow-host class="mine"&gt;
</div><div class="sub c2-b c1-f">
(a regular DOM node that the shadow DOM is attached to.)
</div>
</div>
<div class="c2-f">
pseudo-class that matches what?
</div><div class="c1-f">
Are matched how?
</div><br>{{c1:::defined}}  <span class="divider">&lt;-&gt;</span> {{c2::custom elements that are already defined}}<br><div class="sub">
<div class="sub c2-b c1-f">
useful for showing placeholder stuff
</div>
</div>
<div class="c2-f">
is selected how?
</div><div class="c1-f">
selects what?
</div><br>{{c1::part="foo"}}  <span class="divider">&lt;-&gt;</span> {{c2:::part(foo)}}
<div class="c2-f">
Solves what problem?
</div><div class="c1-f">
Is solved by what?
</div><br>{{c1::the part property&nbsp;}}  <span class="divider">&lt;-&gt;</span> {{c2::targeting things within shadow DOMs (mostly components}}
interestingly, what can you do with custom elements before you define them? <span class="divider">-&gt;</span> {{c1::already use them in the html}}
Within a custom element, what can we have, that makes it particularly useful? <span class="divider">-&gt;</span> {{c1::child elements}}
Where are the lifecycle callbacks for custom elements defined? <span class="divider">-&gt;</span> {{c1::in the class that defines the custom elements}}
To what do you most commonly attach a shadow root? <span class="divider">-&gt;</span> {{c1::a custom element}}
In the constructor for a custom element, what should you do, first thing? <span class="divider">-&gt;</span> {{c1::call super(props) (to make sure that the correct prototype chain is established)}}
<div class="c2-f">
are called when?
</div><div class="c1-f">
What is called then?
</div><br>{{c1::lifecycle callbacks}}  <span class="divider">&lt;-&gt;</span> {{c2::when the custom element changes in relation to the DOM (e.g. connected or disconnected from the DOM)}}<br><div class="sub">
<div class="sub f">
Fot custom elements
</div><div class="sub c2-f">
be a little specific
</div>
</div>
<div class="c2-f">
Are called when a custom element is?
</div><div class="c1-f">
Which lifecycle callbacks are called then?
</div><br>{{c1::connected/disconnectedCallback}}  <span class="divider">&lt;-&gt;</span> {{c2::connected to/ disconnected from the DOM}}
<div class="c2-f">
Are called when a custom element is?
</div><div class="c1-f">
Which lifecycle callbacks are called then?
</div><br>{{c1::adoptedCallback}}  <span class="divider">&lt;-&gt;</span> {{c2::moved to a new document}}
<b>custom elements</b> have are four {{c1::lifecycle callbacks}}, {{c2::connectedCallback}}, {{c3::disconnectedCallback}}, {{c4::adoptedCallback}}, {{c5::attributeChangedCallback}}


3.2.2. Selecting Shadow Hosts from within a Shadow Tree
A shadow host is outside of the shadow tree it hosts, and so would ordinarily be untargettable by any selectors evaluated in the context of the shadow tree (as selectors are limited to a single tree), but it is sometimes useful to be able to style it from inside the shadow tree context.

For the purpose of Selectors, a shadow host also appears in its shadow tree, with the contents of the shadow tree treated as its children. (In other words, the shadow host is treated as replacing the shadow root node.)

When considered within its own shadow trees, the shadow host is featureless. Only the :host, :host(), and :host-context() pseudo-classes are allowed to match it.

Why is the shadow host so weird?
The shadow host lives outside the shadow tree, and its markup is in control of the page author, not the component author.

It would not be very good if a component used a particular class name internally in a shadow tree stylesheet, and the page author using the component accidentally also used the same class name and put it on the shadow host. Such a situation would result in accidental styling that is impossible for the component author to predict, and confusing for the page author to debug.

However, there are still some reasonable use-cases for letting a stylesheet in a shadow tree style its shadow host. (For example, the component might want to be laid out as a flexbox, requiring the shadow host to be set to display: flex.) So, to allow this situation but prevent accidental styling, the shadow host appears but is completely featureless and unselectable except through :host and its related functional forms, which make it very explicit when you’re trying to match against markup provided by the page author.
How can you prevent FOUC with custom elements? <span class="divider">-&gt;</span> {{c1:::defined (and specifically :not(:defined))}}
{{c1::custom elements}} are HTML elements that have their own {{c2::name}} and {{c3::custom functionality}}.
The {{c1::Web Components::w...}} suite consists of {{c2::Custom elements}}, {{c3::Shadow DOM}} and {{c4::HTML templates}}
<div class="c2-f">
returns something of the type?
</div><div class="c1-f">
The most common and relevant element of this type is?
</div><br>{{c1::window.customElements}}  <span class="divider">&lt;-&gt;</span> {{c2::CustomElementRegistry}}
<div class="c1-f">
When can you already use this?
</div><br><pre><code>&lt;share-buttons&gt;
  &lt;social-button type="twitter"&gt;&lt;a href="..."&gt;Twitter&lt;/a&gt;&lt;/social-button&gt;
  &lt;social-button type="fb"&gt;&lt;a href="..."&gt;Facebook&lt;/a&gt;&lt;/social-button&gt;
  &lt;social-button type="plus"&gt;&lt;a href="..."&gt;G+&lt;/a&gt;&lt;/social-button&gt;
&lt;/share-buttons&gt;
</code></pre> <span class="divider">-&gt;</span> {{c1::even before these custom elements are defined}}

to {{c1::only allow unique items in arrays (to make it a set, I guess)}} in json schema, specify <code>{{c2::"uniqueItems": true}}</code>
to specify that a JSON Schema value {{c1::has children}}, use {{c2::the <code>properties</code> key}}
the {{c3::top-level}} {{c1::type}} key provides a {{c2::type for the top-level object}}
the {{c2::top-level object}} in a {{c3::JSON schema document}} has a few {{c1::metadata/general description}} keys
the JSON schema keys {{c1::min/maxItems}} say {{c2::how many items an item of type array can have}}
the JSON schema keys <code>{{c2::(exclusive)}}{{c1::m/Minimum}}</code> and <code>{{c2::(exclusive)}}{{c1::m/Maximum}}</code> describe {{c3::the relevant kind of minimum/maximums of the values}}
the JSON schema key {{c2::type}} tells us {{c1::what datatype the value should be}}
the JSON schema key {{c2::<code>required</code>}} is an {{c3::array}} saying {{c1::which children must be present}}
the JSON schema key {{c2::<code>description</code>}} provides {{c1::a short description of the value}}

the {{c1::dependentRequired}} key in json schema takes an {{c2::object}} where for every given {{c2::key}} there is {{c3::an array}} of other propetries which are {{c4::then also required}} if the {{c4::key is specified}}
To express a more detailed conditional relationship in JSON schema, you can use the {{c1::"if"}}, {{c2::"then"}}, and {{c3::"else"}} keywords
If {{c1::credit_card is present}}, {{c1::billing_address is also required}} (JSON Schema):
<pre><code>{
  "properties": {
    "name": { "type": "string" },
    "credit_card": { "type": "number" },
    "billing_address": { "type": "string" }
  },

  "required": ["name"],

  {{c2::"dependentRequired"}}: {
    {{c3::"credit_card"}}: {{c4::["billing_address"]}}
  }
}</code></pre>

since GPL forces you to license software built of this with the same rights, it has what attribute? <span class="divider">-></span> {{c1::copyleft}}
What do you have to do with software using the GPL related to the source code? <span class="divider">-></span> {{c1::include it with it (or otherwise make it publicly available)}}
What can you do related to redistributing GPL software? <span class="divider">-></span> {{c1::you can redistribute it}}
What can you do related to changing GPL software? <span class="divider">-></span> {{c1::modify it however you like}}
I write MyCoolTokenizer with a copyleft-including license. You use MyCoolTokenizer in MyCoolFrequencyAnalyzer. What do you have to do? <span class="divider">-&gt;</span> {{c1::Give the users of MyCoolFrequencyAnalyzer the same freedoms MyCoolTokenizer allows.}}
How can you sell things licensed with the GPL, if you comply with the license terms? <span class="divider">-></span> {{c1::however you want}}
If you modify GPL software, what do you have to do with those changes? <span class="divider">-&gt;</span> {{c1::make them available}}<br><div class="sub">
<div class="sub c1-f">
Unless only you use the changes
</div>
</div>

grep [{{c1::OPTIONS}}] {{c2::PATTERN}} [{{c3::FILE...}}]

for the deterministic finite-state machine's (Σ, S, s0, 𝛿, F), what is 𝛿? <span class="divider">-&gt;</span> {{c1::the state transition function&nbsp;}}<br><div class="sub">
<div class="sub c1-f">
technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM
</div>
</div>
for the deterministic finite-state machine's (Σ, S, s0, 𝛿, F), what is Σ? <span class="divider">-&gt;</span> {{c1::The input alphabet (same as for a formal language)}}<br><div class="sub">
<div class="sub c1-f">
technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM
</div>
</div>
for the deterministic finite-state machine's (Σ, S, s0, 𝛿, F), what is s0? <span class="divider">-&gt;</span> {{c1::the initial state}}<br><div class="sub">
<div class="sub c1-f">
technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM
</div>
</div>
for the deterministic finite-state machine's (Σ, S, s0, 𝛿, F), what is S? <span class="divider">-&gt;</span> {{c1::set of states}}<br><div class="sub">
<div class="sub c1-f">
technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM
</div>
</div>
for the deterministic finite-state machine's (Σ, S, s0, 𝛿, F), what is F? <span class="divider">-&gt;</span> {{c1::the set of final states}}<br><div class="sub">
<div class="sub c1-f">
technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM
</div>
</div>
a finite state machine, if {{c3::it doesn't have a transition for an input}}, is {{c1::either said to fail}}&nbsp; or {{c2::goes to a failure state}}
What kind of storage does a FSA have? <span class="divider">-&gt;</span> {{c1::no storage}}
What is a deterministic FSA in relation to its corresponding non-deterministic FSA most often? <span class="divider">-&gt;</span> {{c1::more complex}}
What can any non-deterministic FSA be transformed into? <span class="divider">-&gt;</span> {{c1::a deterministic FSA}}
Nonterminals ∩ Terminals =  <span class="divider">-&gt;</span> {{c1::ø}}
In a finite state machine, each transition merely depends on the {{c1::current state}} and the {{c2::input}}
In a classic formalization, a formal grammar G consists of the 4-tuple ({{c1::Set of}} {{c2::nonterminals}}, {{c1::set of}} {{c3::terminals}}, {{c1::set of}} {{c4::production rules}}, {{c5::start symbol}})
A transducer is a FSA that accepts input (like an acceptor) and then... <span class="divider">-&gt;</span> {{c1::generates output}}
A FSA that accepts input (like an acceptor) but then generates an output is known as what? <span class="divider">-&gt;</span> {{c1::a transducer}}
<div class="c2-f">
Rough synonym?
</div><div class="c1-f">
Rough synonym?
</div><br>{{c1::Finite state machine}}  <span class="divider">&lt;-&gt;</span> {{c2::Finite state automaton}}
<div class="c1-f">
are the most sophisticated production rules which kind of grammars/languages allow?
</div><br>A -&gt; aB or A -&gt; Ba <span class="divider">-&gt;</span> {{c1::regular grammars / languages}}
<div class="c1-f">
are the most sophisticated production rules which kind of grammars/languages allow?
</div><br>A -&gt; BbcCdCCBaA... <span class="divider">-&gt;</span> {{c1::context-free grammars / languages}}
<div class="c1-f">
Short for?
</div><br>FSM/FSA <span class="divider">-&gt;</span> {{c1::Finite state machine / automaton}}
What does a finite-state machine do in response to some inputs? <span class="divider">-&gt;</span> {{c1::transition}}
The input is a well-formed word if what and the input is over&nbsp;&nbsp;(in a deterministic finite-state machine that is acceptors/detectors/recognizers)? <span class="divider">-&gt;</span> {{c1::we've reached a final state<br>}}
The input is a well-formed word if we've reached a final state and what (in a deterministic finite-state machine that is a acceptors/detectors/recognizers)? <span class="divider">-&gt;</span> {{c1::the input is over&nbsp;<br><br>}}
If we've reached a final state and the input is over in a deterministic finite-state machine that is a acceptors/detectors/recognizers, then what is the case?&nbsp; <span class="divider">-&gt;</span> {{c1::the input is contained in the language}}<br><div class="sub">
<div class="sub c1-b c2-f">
the input is a well-formed word
</div>
</div>
For a deterministic finite-state acceptor machine, what is the relationship between F (set of final states) and S (set of states)? <span class="divider">-&gt;</span> {{c1::F ⊆ S}}
For a deterministic finite-state acceptor machine, the state transition function produces what? <span class="divider">-&gt;</span> {{c1::the transitions}}
Definition of a deterministic finite-state machine = ({{c1::Σ}},  {{c2::S}},  {{c3::s0}},  {{c4::𝛿}},  {{c5::F}}) <sub>technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM</sub>
At any given time, an automaton is what? <span class="divider">-&gt;</span> {{c1::In a given state}}
At any given time, an automaton is in how many states? <span class="divider">-&gt;</span> {{c1::exactly one}}
<div class="c2-f">
If an automaton is this, then what is true about the transition from one state to another?
</div><div class="c1-f">
If for an automaton ___ transition from one state to another, then it is called?
</div><br>{{c1::non-deterministic}}  <span class="divider">&lt;-&gt;</span> {{c2::there is more than one}}<br><div class="sub">
<div class="sub c2-b c1-f">
it is ambiguous
</div>
</div>
<div class="c2-f">
If an automaton is this, then what is true about the transition from one state to another?
</div><div class="c1-f">
If for an automaton ___ transition from one state to another, then it is called?
</div><br>{{c1::deterministic}}  <span class="divider">&lt;-&gt;</span> {{c2::It is unambiguous (the combination of input + state produces exactly one possible transition)}}
<img class="c1-f c2-b" src="sm_Turnstile_state_machine_colored.svg"><br>What are the transitions here (this is a finite-state machine)? <span class="divider">-&gt;</span> {{c1::all the arrows}}
What are the states&nbsp; here (this is a finite-state machine)? <span class="divider">-&gt;</span> {{c1::Locked and unlocked}}
What are the inputs&nbsp; here (this is a finite-state machine)? <span class="divider">-&gt;</span> {{c1::Push and Coin}}
What are the arrows here (this is a finite-state machine)? <span class="divider">-&gt;</span> {{c1::transitions}}
What are Push and Coin here (this is a finite-state machine)? <span class="divider">-&gt;</span> {{c1::Inputs}}
What are Locked and Unlocked here (this is a finite-state machine)? <span class="divider">-&gt;</span> {{c1::states}}
<img class="c1-f c2-b" src="sm_220px-DFAexample.svg.png"><br>What is S1 here probably? <span class="divider">-&gt;</span> {{c1::a final state}}
<div class="c2-f">
Can recognize which languages?
</div><div class="c1-f">
Can be recognized by what?
</div><br>{{c1::Turing machine}}  <span class="divider">&lt;-&gt;</span> {{c2::recursively enumerable languages}}<br><div class="sub">
<div class="sub c2-f c1-b">
needs support in terms of what a turing machine is
</div>
</div>
<div class="c2-f">
Can recognize which languages?
</div><div class="c1-f">
Can be recognized by what?
</div><br>{{c1::Pushdown automaton}}  <span class="divider">&lt;-&gt;</span> {{c2::Context-free languages}}<br><div class="sub">
<div class="sub c2-f c1-b">
needs support in terms of what a pushdown automaton is
</div>
</div>
<div class="c2-f">
Can recognize which languages?
</div><div class="c1-f">
Can be recognized by what?
</div><br>{{c1::Linear bounded automaton}}  <span class="divider">&lt;-&gt;</span> {{c2::Context-sensitive languages}}<br><div class="sub">
<div class="sub c2-f c1-b">
needs support in terms of what a linear bounded automaton is
</div>
</div>
<div class="c2-f">
Can recognize which languages?
</div><div class="c1-f">
Can be recognized by what?
</div><br>{{c1::Finite state machine}}  <span class="divider">&lt;-&gt;</span> {{c2::Regular languages}}
<div class="c1-f">
What does this define?
</div><br>(Σ,  S,  s0,  𝛿,  F) <span class="divider">-&gt;</span> {{c1::a deterministic finite-state machine}}<br><div class="sub">
<div class="sub c1-b c2-f">
technically only for acceptors/detectors/recognizers, although most of it should also hold for other FSM
</div>
</div>
((h:1;::<img src="sm_220px-DFAexample.svg.png">))How are final states in FSM acceptors often designated? <span class="divider">-&gt;</span> {{c1::Double circle}}

foo.{{c3::tagName}} (or .{{c3::nodeName}}) will get the {{c2::name of the html tag}} {{c1::in allcaps}}
foo.{{c1::tagName}} and foo.{{c1::nodeName}} are the same, except that {{c1::nodeName}} will return {{c2::#text for text nodes}}
Why have I never heard of the capturing phase until today (19.07.2021)? <span class="divider">-&gt;</span> {{c1::Because by default, events are registered for the bubbling phase}}
The on&lt;event&gt; prop can't do what, what other methods of adding event handlers can? <span class="divider">-&gt;</span> {{c1::add multiple event handlers}}
Inverse of addEventListener? <span class="divider">-&gt;</span> {{c1::removeEventListener}}
Generally, DOM Events have three phases: The {{c1::capturing phase}}, the {{c2::target phase}}, and the {{c3::bubbling phase}}
Function that allows adding multiple events: element.{{c1::addEventListener}}({{c2::event}}, {{c3::handler}}, {{c4::options}})
Event delegation only works due to what? <span class="divider">-&gt;</span> {{c1::event bubbling}}
By default, which events bubble? <span class="divider">-&gt;</span> {{c1::most but not all (e.g. focus)}}
By default, events become what kind of events? <span class="divider">-&gt;</span> {{c1::events that trigger during the bubbling phase}}
Behavior pattern for {{c5::event delegation}}: Add {{c3::custom attribute}} to element that {{c4::describes behavior}}, add event listener on {{c1::document (or other high elem)}} that {{c2::tests for attribute}} (and then handles the changes)
{{c1::If we pass an object/class as an event handler}}  <span class="divider">&lt;-&gt;</span> {{c2::the handleEvent() function}}
{{c1::stop further event bubbling&nbsp;}}  <span class="divider">&lt;-&gt;</span> {{c2::event.stopPropagation()}}
{{c1::stop default browser actions for event (e.g. going to link when clicking on it)}}  <span class="divider">&lt;-&gt;</span> {{c2::event.preventDefault()}}

{{c1::make an event trigger during the capturing phase}}  <span class="divider">&lt;-&gt;</span> {{c2::3rd arg of addEventListener {capture: true}}}

flip-flops are a type of what? <span class="divider">-&gt;</span> {{c1::circuit}}
What is a very simple ciruit for saving one bit? <span class="divider">-&gt;</span> {{c1::An (SR) flip-flop}}
The most simple type of flip-flop is what flip-flop? <span class="divider">-&gt;</span> {{c1::SR flip-flop}}
SR/<span style="text-decoration-line: overline;">SR</span>&nbsp;flipflops can be created with two of which or which gates? <span class="divider">-&gt;</span> {{c1::NAND or NOR gates}}
SR/<span style="text-decoration-line: overline;">SR</span>&nbsp;flipflops can be created with how many NAND or NOR gates? <span class="divider">-&gt;</span> {{c1::two}}
How much information can a flip-flop store? <span class="divider">-&gt;</span> {{c1::one bit}}
How many stable states does a flip-flop have? <span class="divider">-&gt;</span> {{c1::two}}
<div class="c2-f">
Near-synyonym?
</div><div class="c1-f">
Near-synonym?
</div><br>{{c1::Flip-flop}}  <span class="divider">&lt;-&gt;</span> {{c2::Latch}}<br><div class="sub">
<div class="sub c2-f">
L...
</div>
</div>
SR flip-flop <span class="divider">-&gt;</span> {{c1::Set-Reset Flipflop}}
As what thing is a transistor often used? <span class="divider">-&gt;</span> {{c1::As a switch}}

WebAssembly and JS are meant to... <span class="divider">-></span> {{c1::work together}}
One of main problematic implications of {{c3::WebAssembly}} is that it allows running code on your computer which is {{c2::not easily inspectable}} because {{c1::compiled}}, thus potentially hiding {{c4::malware}}, preventing {{c5::adblockers etc.}} from applying, and in a notable case, being used for {{c6::crypto mining}}
JS can access WebAssembly via... <span class="divider">-></span> {{c1::the WebAssembly JavaScript API}}

The type of waiting that can be stopped by getting a signal is what? <span class="divider">-&gt;</span> {{c1::Interruptible waiting}}
In unix, a process can be {{c1::running/runnable}}, {{c2::waiting}}, {{c3::stopped}}, or {{c4::zombie}}.
A waiting process can either be what or whatß <span class="divider">-&gt;</span> {{c1::uninterruptible or interruptible}}
A running process is either {{c1::the current process}} or {{c2::waiting to be assigned to one of the cpus}}
A process that is either the current process or waiting to be assigned one of the CPUs is known as what? <span class="divider">-&gt;</span> {{c1::running}}

The most common type of {{c5::test doubles}} (arranged alphabetically) are {{c1::dummys}}, {{c2::fakes}}, {{c3::mocks}}, and {{c4::stubs}}
As test doubles, {{c3::stubs}} use {{c4::predefined answers}} to {{c5::simulate what a method would actually do&nbsp;}}<br/><div class="sub">
<div class="sub all-b">dummys are passed but never used (dummys are dummys because they don't do anything), fakes have working implementations but use some shortcut (fakes are fakes because they fake a part of the implementation), stubs use predefined answers (stubs are called stubs because they are method stubs), mocks make sure that the method was called on it properly</div>
</div>
As test doubles, {{c3::mocks}} make sure that {{c2::the method was actually called}} on {{c1::the mock}}&nbsp;in the way {{c4::it shoud}}<br/><div class="sub">
dummys are passed but never used (dummys are dummys because they don't do anything), fakes have working implementations but use some shortcut (fakes are fakes because they fake a part of the implementation), stubs use predefined answers (stubs are called stubs because they are method stubs), mocks make sure that the method was called on it properly
</div>
As test doubles, {{c3::fakes}} have {{c2::working implementations}} but {{c2::use some kind of shortcut}} (e.g. {{c1::database in memory}})<br/><div class="sub">
dummys are passed but never used (dummys are dummys because they don't do anything), fakes have working implementations but use some shortcut (fakes are fakes because they fake a part of the implementation), stubs use predefined answers (stubs are called stubs because they are method stubs), mocks make sure that the method was called on it properly
</div>
As test doubles, {{c3::dummys}} are {{c2::passed}} but {{c2::never used}} (e.g. {{c1::used to fill param lists}})<br/><div class="sub">
dummys are passed but never used (dummys are dummys because they don't do anything), fakes have working implementations but use some shortcut (fakes are fakes because they fake a part of the implementation), stubs use predefined answers (stubs are called stubs because they are method stubs), mocks make sure that the method was called on it properly
</div>

In most contexts, what is the difference between 'program' and 'application'? <span class="divider">-></span> {{c1::They are synonyms}}
If we're differentiating, a program that is directly used by an user is known as what? <span class="divider">-></span> {{c1::an application}}
If we're differentiating between program and application, what is the difference (using set operators)? <span class="divider">-></span> {{c1::application ⊊ program}}
If we're differentiating between program and application, an application is a program that... <span class="divider">-></span> {{c1::is aimed at (interfaced by) an user}}

At its most general, parsing is taking strings and extracting information.
In programming, parsing is often used for extracting a bit of useful data out of a string.
In natural and computer languages, parsing takes a series of tokens and transforms them into some kind of data structure.
In natural and computer languages, parsing is also called syntax/syntactic analysis.
The data structure that parsing results in dependss on the input data.
Parsing a CSV file may result in a list of records.
Parsing natural or programming/markup/whatever languages often results in a tree. This tree is called a parse tree for programming/markup/whatever languages and syntax tree for natural language.
The tokens for parsing/syntactic analysis in the lexical analysis sense are generated by lexical analysis/tokenization.
After parsing/syntactic analysis comes semantic analysis.
a parse tree is the result of {{c1::a derivation}} of a context-free grammar.
{{c1::a syntax tree}} is a form of parse tree most common in linguistics.
AST|Abstract syntax tree
{{c1::}}
more on ASTs, parse trees

<img src="sm_tmp0ejxsp3b.png">
1|Untracked
2|Unmodified
3|Modified
4|staged
5|add the file
6|edit the file 
7|stage the file
8|remove the file
9|commit


## bitwise 

### basic operations

operation|a|b|result
AND|0|0|0
AND|1|1|1
AND|0|1|0
AND|1|0|0
OR|0|0|0
OR|0|1|1
OR|1|0|1
OR|1|1|1
XOR|0|0|0
XOR|0|1|1
XOR|1|0|1
XOR|1|1|0

### bitmasking

a bitmask is using bitwise operations to get the value of certain bits
a bitmask using bitwise AND gets a subset of bits
bitmasking with AND 1⎵2⎵ returns the parity of the number (0 = even, 1 = odd)

###### misc

Ignore files specify things which a given utility should ignore.
Pretty much all VCSs have ignorefiles.
prettierignore.