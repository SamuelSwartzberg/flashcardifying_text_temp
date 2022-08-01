# data structure

## basics

a data structure⎵data model⎵ (my term (in this sense)) is a structure for potential datasets.
^Typically, this is also just referred to as data model, but I think the distinction is worthwile.
A data structure⎵data model⎵ consists of entities, attributes, relationships and constraints.

## construction

### basics

An entity is a fundamental unit of a data structure⎵data model⎵.
An attribute is a characteristic of an entity.
A constraint is a limit on an attribute.
A relationship is a connection between entities. 

### relationships

Relationships may be 1:1, 1:n, or m:n.
1:1, 1:n, m:n =def= one-to-one, one-to-many, many-to many.

## schema

A schema⎵abstract⎵ is a specification for some part of a data structure⎵data model⎵
A schema⎵concrete⎵ is a document specifying a schema⎵abstract⎵.

## entities used

### tables

A table is a sequence of records.
A record⎵table⎵ is a sequence of fields
A field contains some data.
A column is a set of fields with the same index.
A column is sometimes also called field.
A row =syndef= a record.

## data structure⎵data model⎵ type

A data structure⎵data model⎵ type is a basic constraint for the actual data structure⎵data model⎵.

### flat

A flat data structure⎵data model⎵ type is a data structure⎵data model⎵ type which has no relationships.
A table data structure⎵data model⎵ type is a flat data structure⎵data model⎵ type that consists of a table.

### tree-based

#### definition

A tree-based data structure⎵data model⎵ type is a data structure⎵data model⎵ type which consists of n records⎵tree-based structure⎵.
A record⎵tree-based structure⎵ is a compscitree where the nodes have segments⎵tree-based structure⎵ as labels.
A segment⎵tree-based structure⎵ is a set of fields.
^sometimes the terms segment and record are mixed up
The child nodes of a given node of a record⎵tree-based structure⎵ are ordered and all have the same structure.

#### differentiation

The hierarchical data structure⎵data model⎵ type is a tree-based data structure⎵data model⎵ where the compscitree is a basic normal compscitree.
The network data structure⎵data model⎵ type is a tree-based data structure⎵data model⎵ where the compscitree is allows multple parentage with arbitrary nodes, thus turning it into a directed graph with ordered child sets of the same structure.
^so it's not at all as flexible as a graph data structure

### hierarchical

The hierarchical data structure⎵data model⎵ type is a data structure⎵data model⎵ type which consists of n records⎵tree-based structure⎵.


### relational

https://upload.wikimedia.org/wikipedia/commons/7/7c/Relational_database_terms.svg

relational model => RM
relation =def= {heading⎵RM⎵, body⎵RM⎵}

#### heading

A heading⎵RM⎵ is a set of attributes.
Attribute⎵RM⎵ =def= {attribute name, type name} 

#### body

A body⎵RM⎵ is a set of tuples⎵RM⎵.
A tuple⎵RM⎵ is a set of attribute values⎵RM⎵.
^yes, that means a tuple⎵RM⎵ is not a tuple
An attribute value⎵RM⎵ is a value corresponding to a specific attribute⎵RM⎵ and matching its type.

#### further detail

The degree of the heading/tuple/body is the amount of elements within it.
The degree of the heading and tuple must be the same.
An attribute⎵RM⎵ is the set of attribute values of a certain attribute⎵RM⎵.

#### interpretation

A relation may be interpeted as a table.
A tuple⎵RM⎵/attribute value⎵RM⎵/attribute⎵RM⎵ ≙ record⎵table⎵/field/column 




https://en.wikipedia.org/wiki/NoSQL#Types_and_examples