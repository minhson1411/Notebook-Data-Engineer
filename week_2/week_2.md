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

Hello, and welcome to ALTER, DROP, and TRUNCATE tables. After watching this video, you will be able to: Describe the ALTER TABLE, DROP TABLE, and TRUNCATE statements. Explain the syntax. Use the statements in queries. You use the ALTER TABLE statement to add or remove columns from a table, to modify the data type of columns, to add or remove keys, and to add or remove constraints. The syntax of the ALTER TABLE statement is shown here. You start with ALTER TABLE followed by the name of the table that you want to alter. Differently to the CREATE TABLE statement though, you do not use parentheses to enclose the parameters for the ALTER TABLE statement. Each row in the ALTER TABLE statement specifies one change that you want to make to the table. For example, to add a telephone number column to the AUTHOR table in the Library database to store the author’s telephone number, use the following statement: ALTER TABLE author ADD COLUMN telephone_number BIGINT; In this example, the data type for the column is BIGINT which can hold a number up to 19 digits long. You also use the ALTER TABLE statement to modify the data type of a column. To do this, use the ALTER COLUMN clause specifying the new data type for the column. For example, using a numeric data type for telephone number means that you cannot include parentheses, plus signs, or dashes as part of the number. You can change the column to use the CHAR data type to overcome this. This code shows how to alter the author table: ALTER TABLE author ALTER COLUMN telephone_number SET DATA TYPE CHAR(20 ); Altering the data type of a column containing existing data can cause problems though if the existing data is not compatible with the new data type. For example, changing a column from the CHAR data type to a numeric data type will not work if the column already contains non-numeric data. If you try to do this, you will see an error message in the notification log and the statement will not run. If your spec changes and you no longer need this extra column, you can again use the ALTER TABLE statement, this time with the DROP COLUMN clause, to remove the column as shown: ALTER TABLE author DROP COLUMN telephone_number; Similar to using DROP COLUMN to delete a column from a table, you use the DROP TABLE statement to delete a table from a database. If you delete a table that contains data, by default the data will be deleted alongside the table. The syntax for the DROP TABLE statement is: DROP TABLE table_name ; So, you use this statement: DROP TABLE author; to remove the table from the database. Sometimes you might want to just delete the data in a table rather than deleting the table itself. While you can use the DELETE statement without a WHERE clause to do this, it is generally quicker and more efficient to truncate the table instead. You use the TRUNCATE TABLE statement to delete all of the rows in a table. The syntax of the statement is: TRUNCATE TABLE table_name IMMEDIATE; The IMMEDIATE specifies to process the statement immediately and that it cannot be undone. So, to truncate the author table, you use this statement: TRUNCATE TABLE author IMMEDIATE; In this video, you learned that: The ALTER TABLE statement changes the structure of an existing table, for example, to add, modify, or drop columns. The DROP TABLE statement deletes an existing table. The TRUNCATE TABLE statement deletes all rows of data in a table.


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