# Creating Tables and Loading Data

## Types of SQL statements (DDL vs. DML)

Welcome to Types of SQL Statements. 

At the end of the video, you will be able to distinguish between data definition language statements and data manipulation language statements. 

SQL Statements are used for interacting with Entities (that is, tables), Attributes (that is, columns) and their tuples (or rows with data values) in relational databases. SQL statements fall into two different categories: Data Definition Language statements and Data Manipulation Language statements.

Data Definition Language (or DDL) statements are used to define, change, or drop database objects such as tables. 

Common DDL statement types include CREATE, ALTER, TRUNCATE, and DROP. CREATE: which is used for creating tables and defining its columns; ALTER: is used for altering tables including adding and dropping columns and modifying their datatypes; TRUNCATE: is used for deleting data in a table but not the table itself; DROP: is used for deleting tables. Data Manipulation Language (or DML) statements are used to read and modify data in tables. 

These are also sometimes referred to as CRUD operations, that is, Create, Read, Update and Delete rows in a table. 

Common DML statement types include INSERT, SELECT, UPDATE, and DELETE. INSERT: is used for inserting a row or several rows of data into a table; SELECT: reads or selects row or rows from a table; UPDATE: edits row or rows in a table; And DELETE: removes a row or rows of data from a table. Now you know that: DDL or Data Definition Language statements are used for defining or changing objects in a database such as tables. 

And DML or Data Manipulation Language statements are used for manipulating or working with data in tables. Thanks for watching this video.

## Creating Tables

Welcome to Creating Tables. After watching this video, you will be able to: List considerations for creating tables Describe how to create a table in a graphical interface like Db2 on Cloud Explain how to alter table structure after creation When creating a table, you will need some information at hand. 

First, where will you create the table? Many relational databases have Schemas, which provide a way of organizing database objects into logical groups. For example, in IBM Db2 on Cloud, you will store tables, views, functions, and other database objects in your own user schema. 

Next, you must ensure you have all the information you need to create the table, including a name for the table, and names and data types for each column. You should also consider whether a column can contain duplicate values, or if a column will allow null values. 

Use the Entity Relationship Diagram you created as part of your database design to guide you. You can create tables in several different ways. Most databases have a visual or graphical interface that you can use to create and modify tables. 

These are great for small, occasional tasks, but they don’t scale well. You can also create tables with the CREATE TABLE SQL statement, which can be included in a script file to help you automate the creation process when you are creating multiple tables. 

Finally, some databases have administrative APIs for creating and managing databases programmatically. The illustrations provided in this video are based on Db2 on Cloud console examples, similar concepts apply to other databases. The first step in creating a table using the Db2 on Cloud console is to choose a schema to hold the table. 

In this case, the user schema, CQC63405 is selected. In Db2 the default schema is the username. In this example, you can see that the username is CQC63405. Each user will have a different username, so you will see a different username in your own Db2 database. You can create new Schemas to hold your tables, views, and other database objects. In this case, the user schema, CQC63405 is selected. Select New table to create a new table. Give your new table a name. 

In this example, the table is named Employee details. Because it exists within the CQC63405 schema, the fully qualified name for this table is CQC63405.Employee Details.

The new table has a single column by default. You can rename this column to fit your needs. Set a data type for your column by selecting one from the list. Use Add column to continue to add columns until you have constructed the entire table. 

Remember to specify the data type for each column. You can also specify whether the column accepts null values, and specify length and scale depending on the data type. Lastly, click Create. There are many actions you can take once you have created the table. You can Drop, or delete, the table. You can Generate SQL code to perform actions such as SELECT, INSERT, UPDATE, and DELETE. 

You can ALTER the table to add a new column, set constraints, or change the structure of the table in some other way. And you can see the database objects that the table depends on. In this video, you learned that: Many Relational Database Management Systems (RDBMS) have schemas which contain tables, views, functions, and other database objects. 

Most RDBMS provide a GUI which you can create tables through. You can also use SQL statements to create tables.
You can alter the structure of the table after it’s created, should you need to add a column, change a data type, or add a primary or foreign key.

## ALTER, DROP, and Truncate tables

Hello, and welcome to ALTER, DROP, and TRUNCATE tables. After watching this video, you will be able to: Describe the ALTER TABLE, DROP TABLE, and TRUNCATE statements. Explain the syntax. Use the statements in queries. You use the ALTER TABLE statement to add or remove columns from a table, to modify the data type of columns, to add or remove keys, and to add or remove constraints. The syntax of the ALTER TABLE statement is shown here. You start with ALTER TABLE followed by the name of the table that you want to alter. 

Differently to the CREATE TABLE statement though, you do not use parentheses to enclose the parameters for the ALTER TABLE statement. Each row in the ALTER TABLE statement specifies one change that you want to make to the table. For example, to add a telephone number column to the AUTHOR table in the Library database to store the author’s telephone number, use the following statement: ALTER TABLE author ADD COLUMN telephone_number BIGINT; In this example, the data type for the column is BIGINT which can hold a number up to 19 digits long. You also use the ALTER TABLE statement to modify the data type of a column. 

To do this, use the ALTER COLUMN clause specifying the new data type for the column. For example, using a numeric data type for telephone number means that you cannot include parentheses, plus signs, or dashes as part of the number. You can change the column to use the CHAR data type to overcome this. This code shows how to alter the author table: ALTER TABLE author ALTER COLUMN telephone_number SET DATA TYPE CHAR(20 ); Altering the data type of a column containing existing data can cause problems though if the existing data is not compatible with the new data type. For example, changing a column from the CHAR data type to a numeric data type will not work if the column already contains non-numeric data. 

If you try to do this, you will see an error message in the notification log and the statement will not run. If your spec changes and you no longer need this extra column, you can again use the ALTER TABLE statement, this time with the DROP COLUMN clause, to remove the column as shown: ALTER TABLE author DROP COLUMN telephone_number; Similar to using DROP COLUMN to delete a column from a table, you use the DROP TABLE statement to delete a table from a database. 

If you delete a table that contains data, by default the data will be deleted alongside the table. The syntax for the DROP TABLE statement is: DROP TABLE table_name ; So, you use this statement: DROP TABLE author; to remove the table from the database. Sometimes you might want to just delete the data in a table rather than deleting the table itself. While you can use the DELETE statement without a WHERE clause to do this, it is generally quicker and more efficient to truncate the table instead. You use the TRUNCATE TABLE statement to delete all of the rows in a table. The syntax of the statement is: TRUNCATE TABLE table_name IMMEDIATE; 

The IMMEDIATE specifies to process the statement immediately and that it cannot be undone. So, to truncate the author table, you use this statement: TRUNCATE TABLE author IMMEDIATE; In this video, you learned that: The ALTER TABLE statement changes the structure of an existing table, for example, to add, modify, or drop columns. The DROP TABLE statement deletes an existing table. The TRUNCATE TABLE statement deletes all rows of data in a table.


## Summary & Highlights

Congratulations! You have completed this lesson. At this point in the course, you know: 

* DDL statements, including CREATE, ALTER, TRUNCATE, and DROP, are used for defining objects like tables in a database.

* DML statements, including INSERT, SELECT, UPDATE, and DELETE, are used for manipulating data in tables.

* Many Relational Database Management Systems (RDBMS) have schemas that contain tables, views, functions, and other database objects.

* Most RDBMS provide a GUI through which you can create and alter the structure of tables. 

You can also create and alter tables by using DDL SQL statements:

* CREATE TABLE. Creates entities (tables) in a relational database and sets the attributes (columns) in a table, including the names of columns, the data types of columns, and constraints (for example, the Primary Key.)

* ALTER TABLE. Changes the structure of a table by adding or removing columns, modifying the data type of columns, and adding or removing keys and constraints.

* DROP TABLE. Deletes a table from a database.

* TRUNCATE TABLE. Removes all rows in a table.

There are utilities that help you to manage the movement of data:

* You use the BACKUP and RESTORE utilities to create and recover copies of entire databases, including all objects like tables, views, constraints, and data.

* You use the IMPORT utility to insert data into a specific table from different formats, such as DEL/CSV, ASC and IXF, and the EXPORT utility to save data from a specific table into various formats, such as CSV.

* You can use the LOAD utilities, instead of INSERT statements, to quickly insert large amounts of data a variety of different data sources into tables.

* The Load Data utility is a simple to use interface in the Db2 Web Console.

# Designing Keys, Indexes, and Constraints

## Database Objects & Hierarchy (Including Schemas)


Welcome to Database Objects and Hierarchy. After watching this video, you will be able to: Recall the hierarchy of database objects Describe an instance of a database Define the term relational database Explain when to create a new database Define the term schema Compare user schemas and system schemas Describe a database partition List commonly used database objects Relational Database Management Systems (RDBMSes) contain many objects that Database Engineers and Database Administrators must organize. Storing tables, constraints, indexes, and other database objects in a hierarchical structure allows database administrators to manage security, maintenance, and accessibility. 

This example hierarchy gives you an overview of how RDBMSes are structured, although slight variations may occur between products. Most RDBMSes begin with an instance, a single way of organizing the database and everything it contains. Many RDBMSes permit more than one database within a single instance. You will generally find at least one schema at some level in the hierarchy. A schema is a logical grouping of objects within a database. 

Schemas define how database objects are named and prevent ambiguous references. Some RDBMSs consider the schema a parent object of a database, and others consider it a database object. Within a schema are the database objects, including tables, constraints, and indexes. An instance is a logical boundary for a database or set of databases where you organize database objects and set configuration parameters. Every database within an instance is assigned a unique name, has its own set of system catalog tables (which keep track of the objects within the database) and has its own configuration files. You can create more than one instance on the same physical server providing a unique database server environment for each instance. 

The databases and other objects within one instance are isolated from those in any other instance. You can use multiple instances when you want to use one instance for a development environment and another instance for a production environment, restrict access to sensitive information, or control high-level administrative access. Not all RDBMSes use the concept of instances, often managing database configuration information in a special database instead. In Cloud-based RDBMSes, the term instance means a specific running copy of a service. A relational database is a set of objects used to store, manage, and access data. These objects include tables, views, indexes, functions, triggers, and packages. 

Database objects can be either defined by the system (built-in objects) or defined by the user (user-defined objects).In a relational database, Database Engineers establish relationships between tables to reduce redundant data and improve data integrity. A distributed relational database shares tables and other objects across different but interconnected computer systems. A schema is a specialized database object that provides a way to group other database objects logically. 

A schema can contain tables, views, nicknames, triggers, functions, packages, and other objects. When you create a database object, you can assign it to a schema. If you want to assign the object to a specific schema, you can explicitly include the schema name. If you don’t include the schema name, the object is implicitly assigned to the current schema. In most RDBMSes, the default schema is the user schema for the currently logged-on user. A schema also provides a naming context. 

Using the schema name as a name qualifier enables you to distinguish between objects with the same name in different schemas. For example, the schema names Internal and External make it easy to distinguish two different SALES tables: INTERNAL.SALES in the internal schema and EXTERNAL.SALES in the External schema. Thus, schemas enable multiple applications to store data in a single database without encountering namespace conflicts. Many RDBMSes use a specialized schema to hold configuration information and metadata about a particular database. 

For example, tables in a system schema can store lists of database users and their access permissions, information about the indexes on tables, details of any database partitions that exist, and user-defined data types. A partitioned relational database is a relational database whose data is managed across multiple database partitions. You can partition tables that need to contain very large quantities of data into multiple logical partitions, with each partition containing a subset of the overall data. Database partitioning is used in scenarios that involve very large volumes of data, such as data warehousing and data analysis for business intelligence. Database objects are the items that exist within the database. 

The process of database design includes defining database objects and their relationships with each other. In most RDBMSes, you can create objects such as: Tables – logical structures consisting of rows and columns which store data. Constraints - Within any business, data is often subject to certain restrictions or rules. For example, an employee number must be unique. Constraints provide a way to enforce such rules. Indexes - An index is a set of pointers used to improve performance and ensure the uniqueness of the data. Views - A view provides a different way of representing the data in one or more tables. A view is not an actual table and requires no permanent storage.

Aliases - An alias is an alternative name for an object such as a table. It can be used to provide a shorter, simpler name to reference an object. You can create and manage database object through graphical database management tools, scripting, or accessing the database through an API. If you are using SQL to create or manage the object, you will use Data Definition language statements like CREATE or ALTER.


In this video, you learned that: An instance is a logical boundary for a database or set of databases where you organize database objects and set configuration parameters. A relational database is a set of objects used to store, manage, and access data. Relationships between tables to reduce redundant data and improve data integrity. 

A schema is a specialized database object that provides a way to logically group tables, views, nicknames, triggers, functions, packages, and other database objects. Schemas provide naming contexts so that you can distinguish between objects with the same name. User schemas contain database objects like tables, views, functions. System schemas contain configuration information and metadata for the database. You can split very large tables across multiple partitions to improve performance.

Database objects are the items that exist within the database, such as tables, constraints, indexes, views, and aliases.


## Primary Keys and Foreign Keys

Welcome to Primary Keys and Foreign Keys. After watching this video, you will be able to: Describe primary and foreign keys Create primary and foreign keys You can use a primary key to uniquely identify every row in a table. In some tables, the choice of primary key is easy because it is a naturally occurring unique attribute of entity. For example, the book id of a book or the employee ID number of a staff member. 

If your table doesn’t have an existing unique attribute, you can add a column to the table to serve as the primary key. Or if a combination of two attributes uniquely identifies each row, you can create a primary key across the two columns. For example, where employees have a unique identifier within their work site, you can use the combination of their site id and employee id. Each table can only have one primary key. You can create a primary key when you create the table by using the PRIMARY KEY clause of the CREATE TABLE statement. 

In the parenthesis for the PRIMARY KEY clause, state the name of the column or columns that will be the primary key. Alternatively, you can create a primary key on an existing table by using the ADD PRIMARY KEY clause of the ALTER TABLE statement. And again in the parenthesis, state the name of the column or columns that will be the primary key. You use primary and foreign keys to define the relationships between your tables. A foreign key is a column in a table which contains the same information as the primary key in another table. For example, the Copy table might list all books that the library owns. 

Therefore, the book_id of a copy of an individual book must exist in the Book table as a valid book. Where the library owns multiple copies of a popular book, the book_id of that particular book will appear multiple times in the Copy table. You can also specify that whenever you add a row to the Copy table, the book_id you use must already exist in the Book table. Similar to primary keys, you can create a foreign key when you create the table by using the CONSTRAINT <constraint_name> FOREIGN KEY clause of the CREATE TABLE statement. In the parenthesis for the FOREIGN KEY clause, state the name of the column or columns that will be the foreign key and then reference the table and primary key column that the foreign key links to. 

You can also use the rule clause to define what action to take if a row in the parent table, that is the table with the primary key, is updated or deleted. For updates and deletes, you can specify to take no action in which case the update or delete operation on the parent table may fail. For deletions, you can also specify to cascade the delete, that is to delete the related child rows in the dependent table, or to set the values in the foreign key column of the child table to null. Alternatively, you can create a primary key on an existing table by using the ADD PRIMARY KEY clause of the ALTER TABLE statement. 

And again in the parenthesis, state the name of the column or columns that will be the primary key. Note to use a comma to separate the column names when using multiple columns for a primary key. In this video, you learned that: You can use primary keys to enforce uniqueness of rows in a table Foreign keys are column in a table which contain the same information as the primary key in another table You can use primary and foreign keys to create relationships between tables

## Overview of Indexes

Welcome to Indexes. After watching this video, you will be able to: Describe indexes, Create indexes, Explain the advantages and disadvantages of using indexes. Usually, when you add data to a table it is appended to the end of the table, however, there is no guarantee of this and there is no inherent order to the data. So when you select a particular row from that table, the processor must check each row in turn until it finds the one that you want. On a large table, this can become a very slow way of locating a row. 

Also when you select multiple rows, unless you specify a sort order in your SELECT statement they may be returned in an unordered state. Because you often want to return the rows in a particular order or select a subset of sequential rows, you can create an index on a table to easily locate the specific row or set of rows you require. An index works by storing pointers to each row in the table so when you request a particular row, the SQL processor can use the index to quickly locate the row. This is similar to how you use the index in a book to quickly find a particular section of the book. The index is ordered by values within the unique key upon which it is based. By default, when you create a primary key on a table an index is automatically created on that key, but you can also create your own indexes on regularly searched columns. 

Use the CREATE INDEX statement to define the index, specifying the index name, its uniqueness, and the table and column on which to base it. Indexes provide the database user with many benefits, including: Improved performance of SELECT queries when searching on an indexed column. Because the index provides a quick route to locate rows matching the search term, the results are returned quicker than when it has to check every row in the table. Reduce need to sort data. If you regularly require rows in a specific order, using an index can eliminate the need for sorting the rows after they are located. Guaranteed uniqueness of rows. 

If you use the UNIQUE clause when you create the index, you can be sure that updates and insertions will not create duplicate entries in that column while not bearing the overhead of having to check this against each row in the table. They do however have a few disadvantages: Each index that you create uses disk space, in the same way that adding indexes increases the number of pages in a book. Decreased performance of INSERT, UPDATE, and DELETE queries. Because the rows in an indexed table are sorted according to the index, adding or removing rows can take longer than in a non-indexed table. 

You should only create an index when you will gain more from the advantages that you lose from the disadvantages. For example, on a table that rarely has rows inserted or updated, but is regularly used in SELECT queries and WHERE clauses. If you create many indexes on a table, you can actually negate the performance benefits in the same way that indexing every word in a book would result in an unhelpful index. In this video, you learned that: Indexes provide ordered pointers to rows in tables, Indexes can improve performance of SELECT queries, Indexes can decrease performance of INSERT, UPDATE, and DELETE queries.