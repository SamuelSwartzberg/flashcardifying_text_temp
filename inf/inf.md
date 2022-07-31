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

###### query languages 

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

###### other implementations

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

### misc

#### leaving the shell

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



## terminal system

# communication - orphaned things

### ASN.1

ASN.1 is an IDL for data structures that can be serialized and deserialized, mainly used in networking.

#### X.690

X.690 is a standard that specifies the BER, CER and DER encoding formats for ASN.1
Basic/Canonical/Distinguished Encoding Rules =short=> BER/CER/DER
CER and DER are subsets of BER.

### APIs for certain purposes

Data|Name|Interface
⟮DWD open weather data⟯|⟮Bright Sky⟯|⟮JSON⟯


## in programming

To share data between entities, one can use message passing or shared memory.
Shared memory is having a fixed storage location which both entities can access to read/write the data.

### messages

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

# libraries


## web frameworks

A framework is a set of libraries where the framework itself has control by default, and only exposes an API.
A framework: Don't call us, we'll call you.
A web framework is a framework for use in web development.

### commonalities

#### templating

⟮a template engine/processor⟯ is something that ⟮combines⟯ ⟮a template⟯ and ⟮data⟯ ⟮into some kind of result⟯ 
⟮templatees⟯ are written in ⟮template languages⟯ 

###### liquid


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

### python

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

#### data visualization

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

## standard library

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

### modules/objects/namespaces

Filesystem handling
fs|node|Rust

### query for input

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


# software design

## abstraction

abstraction is hiding implementation details in favor of a clear, semantic and elegant interface.
A high-level programming language is a programming language with high levels of abstraction.
A low-level programming language is a programming language with low levels of abstraction.
Often, abstraction has runtime overhead/costs.
Zero-cost abstractions are abstractions that have no runtime, only compile-time overhead.
Rust touts that it has many zero-cost abstractions.

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

### agile

#### lean

##### kanban

Kanban board tools: trello, github projects

### scrum

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

## comments

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

## documentation generators

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

# modelling

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

###### rust

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

###### the runtime

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


#### entry point

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

#### output

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

### latex

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

### mobile development

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

# misc/no place yet

most languages allow an arbitrary amount of spaces and tabs as indentation, YAML however only allows spaces
hot whatever|doing whatever while the system is still running
cold whatever|doing whatever while the system is not running
hot swapping may be of components, or of software


# automation

## misc

The Amazon Mechanical Turk is a service that allows crowdsourcing menial tasks.
The Amazon Mechanical Turk pays way below the minimum wage.
The Amazon Mechanical Turk is sometimes used for study subjects.


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

# project jupyter

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

## document start/end indicators

--- the file ... |YAML (but optional, merely allow multiple documents per file)

## computer ergonomics

Ideally, your ⟮arm (elbow⟯) should have an angle of ⟮90°⟯ while ⟮touch typing⟯ 
Ideally, ⟮your wrist⟯ should be ⟮hovering⟯ while ⟮touch typing⟯ 

# server directory structure

Jekyll ＆ common

./assets|assets
./assets/css|css files
./assets/js|js files

# metacharacters ＆ escapes 

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

### morse

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

### unicode

Unicode is goverened by the unicode consortium.

#### codepoint subdivision 

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


##### percent

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