## Save data in a local database using Room   

- save data locally-> The most common use case is to cache relevant pieces of data so that when the device cannot access the network, the user can still browse that content while they are offline.

> The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite. In particular

Room provides the following benefits:
1. Compile-time verification of SQL queries.
2. Convenience annotations that minimize repetitive and error-prone boilerplate code.
3. Streamlined database migration paths.


### Primary components
- There are three major components in Room:
1. The database class that holds the database and serves as the main access point for the underlying connection to your app's persisted data.
2. Data entities that represent tables in your app's database.
3. Data access objects (DAOs) that provide methods that your app can use to query, update, insert, and delete data in the database.

## implementation 

- Data entity:
The following code defines a User data entity. Each instance of User represents a row in a user table in the app's database.

- Data access object (DAO)
The following code defines a DAO called UserDao. UserDao provides the methods that the rest of the app uses to interact with data in the user table.

- DateBase:
-  AppDatabase class to hold the database.
- AppDatabase defines the database configuration and serves as the app's main access point to the persisted data

- The database class must satisfy the following conditions:
1. class must be annotated with a @Database annotation that includes an entities array that lists all of the data entities associated with the database.
2. The class must be an abstract class that extends RoomDatabase.
3. For each DAO class that is associated with the database, the database class must define an abstract method that has zero arguments and returns an instance of the DAO class.


## Defining data using Room entities 

- Anatomy of an entity
1. define each Room entity as a class that is annotated with @Entity.
2. A Room entity includes fields for each column in the corresponding table in the database, including one or more columns that comprise the primary key.
3. By default, Room uses the class name as the database table name
- table to have a different name, set the tableName property of the @Entity annotation
4.  uses the field names as column names in the database by default.
- want a column to have a different name, add the @ColumnInfo annotation to the field and set the name property. 

## Define a primary key
 annotate a single column with @PrimaryKey

 - Define a composite primary key -> define a composite primary key by listing those columns in the primaryKeys property of @Entity:

## Ignore fields
> By default, Room creates a column for each field that's defined in the entity. If an entity has fields that you don't want to persist, you can annotate them using @Ignore

## Provide table search support

If your app requires very quick access to database information through full-text search (FTS), have your entities backed by a virtual table that uses either the FTS3 or FTS4
- add the @Fts3 or @Fts4 annotation

## Include AutoValue-based objects
- using @AutoValue, as entities in your app's database. This support is particularly helpful when two instances of an entity are considered to be equal if their columns contain identical values.

- When using classes annotated with @AutoValue as entities, you can annotate the class's abstract methods using @PrimaryKey, @ColumnInfo, @Embedded, and @Relation

- When using these annotations, however, you must include the @CopyAnnotations annotation each time so that Room can interpret the methods' auto-generated implementations properly.


## Define relationships between objects 

- Create embedded objects :
use the @Embedded annotation to represent an object that you'd like to decompose into its subfields within a table.


### Define one-to-one relationships:
A one-to-one relationship between two entities is a relationship where each instance of the parent entity corresponds to exactly one instance of the child entity, and vice-versa.

- Add the @Relation annotation to the instance of the child entity, with parentColumn set to the name of the primary key column of the parent entity and entityColumn set to the name of the column of the child entity that references the parent entity's primary key.

> add a method to the DAO class that returns all instances of the data class that pairs the parent entity and the child entity. This method requires Room to run two queries, so add the @Transaction annotation to this method to ensure that the whole operation is performed atomically.


### Define one-to-many relationships:
A one-to-many relationship between two entities is a relationship where each instance of the parent entity corresponds to zero or more instances of the child entity, but each instance of the child entity can only correspond to exactly one instance of the parent entity.


### Define many-to-many relationships:
A many-to-many relationship between two entities is a relationship where each instance of the parent entity corresponds to zero or more instances of the child entity, and vice-versa.

## Accessing data using Room DAOs 


- There are two types of DAO methods that define database interactions:

1. Convenience methods that let you insert, update, and delete rows in your database without writing any SQL code.
2. Query methods that let you write your own SQL query to interact with the database.


### Convenience methods

1. Insert ->
The @Insert annotation allows you to define methods that insert their parameters into the appropriate table in the database

2. Update ->
The @Update annotation allows you to define methods that update specific rows in a database table.

3. Delete ->
The @Delete annotation allows you to define methods that delete specific rows from a database table. 


### Query methods
- The @Query annotation allows you to write SQL statements and expose them as DAO methods.

> Room validates SQL queries at compile time. This means that if there's a problem with your query, a compilation error occurs instead of a runtime failure.


- Query multiple tables:  use JOIN clauses in your SQL queries to reference more than one table.

#### Special return types:
- Paginated queries with the Paging library
- Direct cursor access
