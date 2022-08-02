
# databases

A database is a dataset molded by a data model treated/implemented as a monolith.
A database model is the implementation of a data model in a specific database.

## DBMS

A DBMS (database management system) is the software used to manage a database.

## database operations

### basics

A database operation is an action which can be performed on a database.

### database language

#### basics

A database language is a language that allows you interact with a database.
A database language may be a data control, definition, manipulation or query language as well as a translation control language.

#### mapping

table:database language|does
data control language|authorization control
data definition language|interact with schemas
data manipulation language|write database operation
data query language|read⎵wide⎵ database operation
transaction control language|controls database transactions

### types

A read⎵wide⎵/write database operation is a read⎵wide⎵/write dataset operation performed on a database
A read⎵wide⎵ database operation is sometimes divided into browse and read⎵narrow⎵ database operations.
A write database operation may be a create, update or delete database operation.
A create/update/delete database operation creates/updates/deletes one or more data/database things.


### database transaction

#### basics

A database transaction is a unit of work done against a database, and consists of n database language statements.

#### ACID

##### basics

ACID is a set of properties that a database transaction should ideally have to guarantee data validity.
ACID consists of atomicity, consistency, isolation, durability

##### in detail

Atomicity is that a database transaction will either succeed completely or fail completely.
Consistency is that a database transaction will only result in valid database states (constraints etc.)
Isolation is that concurrent database transactions will leave the database in the same state as sequential database transactions would have.
Durability is that a completed database transaction will remain even after a system failure.


A database type is a database implementing a data model of a certain data model type.



A database schema is a schema for a database.
