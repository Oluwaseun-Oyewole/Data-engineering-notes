Database notes

Object oriented database - data is stored in form of objects
Graph database - data is stored in node and relationship between them is stored as edges
Document database - data is stored as JSON. Data is organized into collections like tables

Note: Database can be stored on-prem or in the cloud.

TERMS TO KNOW
Relational database store structured data in a tabular format
noSQL database store database in different format. It provides a flexible structure for storing and scaling data.
types of noSQL db includes document, graph database, key-value database
Big data - data that can grow exponentially with time. It comes from social media platforms, e-commerce platform, etc.
Cloud database - storing data in the cloud instead of on-prem devices
Business intelligence - analyzing data and other information to make informed decisions

WHAT IS A TABLE
Table is made of rows and columns. A table is also know as an entity.
Column - fields, attributes
Row - record,

KEYS IN TABLE
Relationship are established between database with the use of keys
A candidate key is unique column|attribute to each row
Composite key is a combination of 2 or more attributes
Alternate key is a candidate key
Foreign key points to the unique in another table

KEYS
Super key - any number of columns that creates unique rows. A row that forces the database to be unique.
Candidate-key - least number of columns needed to force the row to be unique
Primary key — Surrogate key, natural key
Alternate key - enforces uniqueness but they are not used as a primary key in that table
Foreign keys - references the primary key in a separate table
Simple key - 1 column
Composite key - 2 or more columns
Compound key

Database constraints — NOT NULL, DEFAULT, FOREIGN KEY

DATA TYPES
Data types — Numeric, string, binary, date and time
String data types - tiny text, text, medium text, long text categorized into CHAR(fixed length ) and VARCHAR(variable length)
Numeric data types — Integer, decimal

DATABASE SYSTEM 0. Data definition language - CREATE, ALTER, DROP 0. Data manipulation language - INSERT, UPDATE, DELETE 0. Data query language - SELECT 0. Data transactions language 0. Data control language -

DATABASE COMMANDS
SELECT DISTINCT from table;
WHERE
CREATE
SHOW
ALTER
ORDER BY
BETWEEN
IN
ALIAS - AS
JOIN
LIKE - this is used for pattern matching..
CONCAT - join columns together

DATABASE SCHEMA
Definition: collection of data structures within a database and their relationships
In a SQL server, a database schema is a collection of different component like table,
Types of database schema 0. Logical DB schema - uses ER modeling. It involves showing relationship between table components 0. Physical DB schema

DATABASE NORMALIZATION

THE GOAL OF NORMALIZATION IS TO REMOVE DATA DUPLICATION.

Database normalization challenges -
insert anomaly, update an deletion anomaly.
insert anomaly - when an insertion of new data requires the addition of another data.

Database normalization helps to prevent data duplication. It optimizes the database design by creating a single purpose for each table.
Database normalization forms include 1NF, 2NF, 3NF.

Functional dependency explains the relationship between 2 attributes in a table.
Partial dependency refer to a table with composite keys

1NF — atomicity rule. Your table should have one value per column field. Avoid repeating attribute in tables.
2NF — all non keys attributes must depend on the entire primary key value. This also deals with eliminating partial dependency,
this is when a column only depends on parts of the primary key.
Ideally for 2NF, remove all partial dependency and put it into it’s own separate table.
3NF — This deals with eliminating transitive dependency. A non key attribute should not depend on another non-key attribute. It should only depend on unique key attribute.

LOGICAL OPERATORS
Filtering data in SQL involves using logical operators like AND, OR, NOT, BETWEEN, IN, LIKE
BETWEEN — lets you select value within a given range
LIKE — to filter data based on pattern matching
IN — let’s you include multiple values in the WHERE clause, This behaves like multiple OR’s

ALIASES IN DATABASE
SQL aliases provides database columns and tables with temporary name

Types of join
Joins are used to combine tables
inner join - extracts or select records of data that has matching values between both tables (left & right tables)
Left join - extracts or select records of data from the left and all matching record from the right table
Right join - extracts or select records of data from the right and matching record from the left table
Self join - a table is joined with itself to retrieve info that exists within the same table

INNER JOIN

INNER JOIN CODE SNIPPET
Question: Let say I have 2 tables, one for customers, orders. Combine a table with inner for both customer and order
Answer: select customer.customerName from customer inner join orders on customer.customerID = orders.customerID;

LEFT JOIN

select c.customerName, c.lastName, o.orderId, o.orderDate, o.quantity, o.totalAmount from customer as c left join orders as o on c.customerId=o.customerId;
LEFT JOIN EXECUTION

RIGHT JOIN

RIGHT JOIN CODE SNIPPET
select c.customerName, c.lastName, o.orderId, o.orderDate, o.quantity, o.totalAmount from customer as c right join orders as o on c.customerId=o.customerId;

OPERATORS
Union - to combine result set from multiple statements in the same query. You can join 2 select statements in order to join their result and present as one table
Group by - group similar values into a single record (select customerID from orders group by customerID). You can also use it with SQL aggregate functions like sum, count, etc…
Having - it specifies a filter condition for the groups of rows and aggregate. It should be used with group by command

MYSQL Constraints
Types of constraints
Key constraints - like primary key which should always be unique.
Domain constraints - restriction on column using check
Referential integrity constraints - for both primary key and foreign key in a referencing table and referenced table

BASIC SQL SYNTAX
Alter - modify, add and drop.
Copy table in mysql - create table new_table-name select \* from exiting_table_name.
subQuery - this is a query within another query. An inner query placed within an outer query.
Commands to use with sub query includes ANY, ALL, SOME, EXIST, NOT EXISTS

VIRTUAL TABLES IN MYSQL
Views are virtual tables created from one or multiple tables depending on the requirements.
Views can be used to create subset of a table’s data
Views can also be used to combine data from multiple table.

FUNCTIONS AND TYPE IN MYSQL
Numeric
String
Control flow

What is stored procedures - a block that code that can stored in your database and re-invoke when needed.the key difference between a function and a stored procedure is parameter. A function only have input parameter while stored procedure can have both input and output parameter.
