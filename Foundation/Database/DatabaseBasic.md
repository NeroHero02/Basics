# Started

**In this section will started learn Database**  

## What is Database ?

A database is an organized collection of data so that it can be easily accessed. To mange these databases, Database Management Systems (DBMS) are used.

- Types of DBMS:  
  - Non-Relational (DBMS) : File System, XML..etc.  
  - Relational (RDBMS): enhanced version of DBMS but with relations, examples SQLServer, Oracle, MySQL ..etc.  

In RDBMS Data that is stored in an organized fashion in tables containing rows and columns along with relations between these tables.  

Table/Entity Set Same.  
Row/Entity/Record Same.  
Column/Field/Attribute Same.  

## What is Null?

In a database, "NULL" is a special marker used to indicate that a data value does not exist in the database. It represents a missing or unknown value in a table column.  

When a field or column in a table has a NULL value, it means that the field has no value at all, and it's different from having an empty or zero value.  

Null can be used in several ways, such as indicating missing data, representing optional fields, or as a placeholder for vaules that are not yet known. However, it's essential to use NULL values carefully because they can affect the results of queries and calculations in unexpected ways.  

In summary, NULL is a special vaule in a database that represents the absence of a value in a table column.  

It's used to indicate missing or unknown data and should be used carefully to avoid unexpected results in queries and calculations.  


## Primary Key vs Foreign Key

Primary Key  

- A primary key is a column or set of columns in a relational database table that uniquely identifies each row or record in the table.  

- It is a unique identifier for each record and serves as a reference point for other tables that have a relationship with the table in question.  

- Each table in a relational database must have a primary key, and it should be a non-null value that is unique and stable over time.  

- Primary Key should not be changed.  


Foreign Key  

- A foreign key, on the other hand, is a column or set of columns in a table that refers to the primary key of another table.  

- It establishes a relationship between two tables, allowing data to be shared and linked between them.  

- The foreign key ensures that referential integrity is maintained by ensuring that any value in the foreign key column must exist in the primary key column of the related table.  



