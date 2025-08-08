# Database Study Notes

## Database Types

### Object-Oriented Database

- Data is stored in the form of objects

### Graph Database

- Data is stored in nodes
- Relationships between nodes are stored as edges

### Document Database

- Data is stored as JSON
- Data is organized into collections (similar to tables)

**Note:** Databases can be stored on-premises or in the cloud.

## Key Terms to Know

### Relational Database

- Store structured data in a tabular format

### NoSQL Database

- Store data in different formats
- Provide flexible structure for storing and scaling data
- **Types of NoSQL databases:**
  - Document databases
  - Graph databases
  - Key-value databases

### Big Data

- Data that can grow exponentially with time
- Sources: social media platforms, e-commerce platforms, etc.

### Cloud Database

- Storing data in the cloud instead of on-premises devices

### Business Intelligence

- Analyzing data and other information to make informed decisions

## Tables

### What is a Table?

- Made of rows and columns
- Also known as an **entity**
- **Column:** fields, attributes
- **Row:** record

## Database Keys

Relationships are established between databases using keys.

### Key Types

#### Super Key

- Any number of columns that create unique rows
- Forces the database to be unique

#### Candidate Key

- Unique column/attribute for each row
- Least number of columns needed to force the row to be unique

#### Primary Key

- **Types:**
  - Surrogate key
  - Natural key

#### Alternate Key

- A candidate key that enforces uniqueness but is not used as a primary key in that table

#### Foreign Key

- Points to the unique key in another table
- References the primary key in a separate table

#### Simple Key

- 1 column

#### Composite Key

- Combination of 2 or more attributes/columns

#### Compound Key

- Similar to composite key

## Database Constraints

- `NOT NULL`
- `DEFAULT`
- `FOREIGN KEY`

## Data Types

### Categories

1. **Numeric**
2. **String**
3. **Binary**
4. **Date and Time**

### String Data Types

- **Fixed Length:** `CHAR`
- **Variable Length:** `VARCHAR`
- **Text Types:**
  - Tiny text
  - Text
  - Medium text
  - Long text

### Numeric Data Types

- Integer
- Decimal

## Database System Languages

### Data Definition Language (DDL)

- `CREATE`
- `ALTER`
- `DROP`

### Data Manipulation Language (DML)

- `INSERT`
- `UPDATE`
- `DELETE`

### Data Query Language (DQL)

- `SELECT`

### Data Transaction Language (DTL)

- Transaction control commands

### Data Control Language (DCL)

- Access control commands

## Database Commands

### Basic Commands

- `SELECT DISTINCT FROM table;`
- `WHERE`
- `CREATE`
- `SHOW`
- `ALTER`
- `ORDER BY`
- `BETWEEN`
- `IN`
- `AS` (ALIAS)
- `JOIN`
- `LIKE` - used for pattern matching
- `CONCAT` - join columns together

## Database Schema

### Definition

Collection of data structures within a database and their relationships.

In SQL Server, a database schema is a collection of different components like tables.

### Types of Database Schema

#### Logical DB Schema

- Uses ER modeling
- Shows relationships between table components

#### Physical DB Schema

- Physical implementation details

## Database Normalization

### Goal

**THE GOAL OF NORMALIZATION IS TO REMOVE DATA DUPLICATION.**

### Normalization Challenges

- **Insert Anomaly:** When insertion of new data requires the addition of another data
- **Update Anomaly**
- **Deletion Anomaly**

### Benefits

- Prevents data duplication
- Optimizes database design by creating single purpose for each table

### Normalization Forms

#### First Normal Form (1NF)

- **Atomicity Rule**
- Table should have one value per column field
- Avoid repeating attributes in tables

#### Second Normal Form (2NF)

- All non-key attributes must depend on the entire primary key value
- Eliminates partial dependency
- Remove all partial dependencies and put them into separate tables

#### Third Normal Form (3NF)

- Eliminates transitive dependency
- A non-key attribute should not depend on another non-key attribute
- Should only depend on unique key attributes

### Key Concepts

- **Functional Dependency:** Explains the relationship between 2 attributes in a table
- **Partial Dependency:** Refers to a table with composite keys

## Logical Operators

Filtering data in SQL involves using logical operators:

- `AND`
- `OR`
- `NOT`
- `BETWEEN` - select values within a given range
- `IN` - include multiple values in WHERE clause (behaves like multiple ORs)
- `LIKE` - filter data based on pattern matching

## Aliases in Database

SQL aliases provide database columns and tables with temporary names.

## Types of Joins

Joins are used to combine tables.

### Inner Join

- Extracts records that have matching values in both tables (left & right tables)

**Code Example:**

```sql
SELECT customer.customerName
FROM customer
INNER JOIN orders ON customer.customerID = orders.customerID;
```

### Left Join

- Extracts all records from the left table and matching records from the right table

**Code Example:**

```sql
SELECT c.customerName, c.lastName, o.orderId, o.orderDate, o.quantity, o.totalAmount
FROM customer AS c
LEFT JOIN orders AS o ON c.customerId = o.customerId;
```

### Right Join

- Extracts all records from the right table and matching records from the left table

**Code Example:**

```sql
SELECT c.customerName, c.lastName, o.orderId, o.orderDate, o.quantity, o.totalAmount
FROM customer AS c
RIGHT JOIN orders AS o ON c.customerId = o.customerId;
```

### Self Join

- A table is joined with itself to retrieve information that exists within the same table

## SQL Operators

### Union

- Combine result sets from multiple statements in the same query
- Join 2 SELECT statements and present as one table

### Group By

- Group similar values into a single record
- Example: `SELECT customerID FROM orders GROUP BY customerID`
- Can be used with SQL aggregate functions like `SUM`, `COUNT`, etc.

### Having

- Specifies a filter condition for groups of rows and aggregates
- Should be used with `GROUP BY` command

## MySQL Constraints

### Types of Constraints

#### Key Constraints

- Primary key should always be unique

#### Domain Constraints

- Restriction on columns using `CHECK`

#### Referential Integrity Constraints

- For both primary key and foreign key in referencing and referenced tables

## Basic SQL Syntax

### ALTER

- Modify, add, and drop table structures

### Copy Table

```sql
CREATE TABLE new_table_name SELECT * FROM existing_table_name;
```

### Subquery

- A query within another query
- Inner query placed within an outer query
- **Commands used with subqueries:**
  - `ANY`
  - `ALL`
  - `SOME`
  - `EXISTS`
  - `NOT EXISTS`

## Virtual Tables in MySQL

### Views

- Virtual tables created from one or multiple tables
- **Uses:**
  - Create subset of a table's data
  - Combine data from multiple tables

## Functions and Types in MySQL

### Function Categories

1. **Numeric Functions**
2. **String Functions**
3. **Control Flow Functions**

### Stored Procedures

- A block of code that can be stored in your database and re-invoked when needed
- **Key Difference between Functions and Stored Procedures:**
  - **Function:** Only has input parameters
  - **Stored Procedure:** Can have both input and output parameters
