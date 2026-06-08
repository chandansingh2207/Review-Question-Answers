CArdinality,


SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET N-1;

NULL:
======
In MySQL, NULL represents a missing, unknown, or undefined value. It is not the same as:

0 (zero)
'' (empty string)
FALSE

| id | name  | phone      |
| -- | ----- | ---------- |
| 1  | Alice | 9876543210 |
| 2  | Bob   | NULL       |


For Bob, phone = NULL means the phone number is unknown or has not been provided.

## In MySQL, UNION and INNER JOIN are used for different purposes:##
=====================================================================
👉 UNION combines rows from both tables.
Requires same number of columns
Removes duplicate rows by default (UNION ALL keeps duplicates).

employees
| name |
| ---- |
| John |
| Mike |

customers
| name  |
| ----- |
| David |
| Sam   |

SELECT name FROM employees
UNION
SELECT name FROM customers;

INNER JOIN
============
👉 INNER JOIN combines related data from two tables using a matching column.

Combines rows from two tables side by side based on a matching condition.
Returns only rows where the join condition matches in both tables.

INNER JOIN Example

employees

id  name    dept_id
1   John    10
2   Mike    20

departments

id  department
10  IT
20  HR

Query:

SELECT e.name, d.department
FROM employees e
INNER JOIN departments d
ON e.dept_id = d.id;

Result:

name    department
John    IT
Mike    HR


| UNION                          | UNION ALL                   |
| ------------------------------ | --------------------------- |
| Removes duplicate records      | Keeps duplicate records     |
| Slower (checks for duplicates) | Faster (no duplicate check) |
| Returns unique rows only       | Returns all rows            |

Easy Memory Trick
====================
UNION = UNION combines results from multiple queries and removes duplicate records.
Unique records.✅

UNION ALL = UNION ALL combines results from multiple queries and keeps duplicate records.
All records (including duplicates) ✅


Here is a simple explanation with examples.

### Sample Tables

**employees**

| id | name  | dept_id |
| -- | ----- | ------- |
| 1  | John  | 1       |
| 2  | Alice | 2       |
| 3  | Bob   | 3       |
| 4  | Tom   | NULL    |

**departments**

| dept_id | dept_name |
| ------- | --------- |
| 1       | HR        |
| 2       | IT        |
| 4       | Sales     |

---

# 1. INNER JOIN

Returns only matching records from both tables.

### SQL

SELECT e.name, d.dept_name
FROM employees e
INNER JOIN departments d
ON e.dept_id = d.dept_id;


### Result

| name  | dept_name |
| ----- | --------- |
| John  | HR        |
| Alice | IT        |

👉 Bob is not shown because dept_id 3 does not exist in departments.
👉 Tom is not shown because dept_id is NULL.

---

# 2. LEFT JOIN (LEFT OUTER JOIN)

Returns all records from the left table and matching records from the right table.

### SQL


SELECT e.name, d.dept_name
FROM employees e
LEFT JOIN departments d
ON e.dept_id = d.dept_id;


### Result

| name  | dept_name |
| ----- | --------- |
| John  | HR        |
| Alice | IT        |
| Bob   | NULL      |
| Tom   | NULL      |

👉 All employees are returned.
👉 If no department exists, NULL is shown.

---

# 3. RIGHT JOIN (RIGHT OUTER JOIN)

Returns all records from the right table and matching records from the left table.

### SQL


SELECT e.name, d.dept_name
FROM employees e
RIGHT JOIN departments d
ON e.dept_id = d.dept_id;


### Result

| name  | dept_name |
| ----- | --------- |
| John  | HR        |
| Alice | IT        |
| NULL  | Sales     |

👉 Sales department is shown even though no employee belongs to it.

---

# 4. FULL OUTER JOIN

Returns all records from both tables.

### SQL


SELECT e.name, d.dept_name
FROM employees e
FULL OUTER JOIN departments d
ON e.dept_id = d.dept_id;


### Result

| name  | dept_name |
| ----- | --------- |
| John  | HR        |
| Alice | IT        |
| Bob   | NULL      |
| Tom   | NULL      |
| NULL  | Sales     |

👉 Includes:

* Matching rows
* Unmatched employees
* Unmatched departments

**Note:** MySQL does not support `FULL OUTER JOIN` directly. You can achieve it using `UNION`.


SELECT e.name, d.dept_name
FROM employees e
LEFT JOIN departments d
ON e.dept_id = d.dept_id

UNION

SELECT e.name, d.dept_name
FROM employees e
RIGHT JOIN departments d
ON e.dept_id = d.dept_id;


---

# Interview One-Line Answers

### INNER JOIN

Returns only matching rows from both tables.

### LEFT JOIN

Returns all rows from the left table and matching rows from the right table.

### RIGHT JOIN

Returns all rows from the right table and matching rows from the left table.

### FULL OUTER JOIN

Returns all rows from both tables, whether matched or not.

### Easy Memory Trick


LEFT JOIN  -> Keep everything from LEFT table
RIGHT JOIN -> Keep everything from RIGHT table
INNER JOIN -> Keep only matches
FULL JOIN  -> Keep everything from both tables



# Normalization in MySQL
=========================
**Normalization** is the process of organizing database tables to reduce **duplicate (redundant) data** and improve data consistency.

### Why Normalization?
* Avoid duplicate data
* Save storage space
* Make updates easier
* Maintain data integrity


1NF – No multiple values in a column.
2NF – Remove partial dependency.
3NF – Remove transitive dependency.

2NF Example:
=============
Example:, you need a table with a composite primary key (a primary key made of more than one column).

| StudentID | CourseID | StudentName | CourseName |
| --------- | -------- | ----------- | ---------- |
| 1         | 101      | John        | PHP        |
| 1         | 102      | John        | MySQL      |
| 2         | 101      | Alice       | PHP        |


Assume the primary key = (StudentID, CourseID).

Here:
StudentName depends only on StudentID
CourseName depends only on CourseID

They do not depend on the entire composite key (StudentID, CourseID).

This is called a partial dependency, so the table is in 1NF but not 2NF.

3NF Example:
============
Interview Example

Suppose:
| EmpID | EmpName | DeptID | DeptName |
| ----- | ------- | ------ | -------- |
| 1     | John    | 10     | IT       |
| 2     | Alice   | 20     | HR       |


Here:
EmpName depends on EmpID ✔️
DeptName depends on DeptID, not directly on EmpID ❌

This is a transitive dependency, so move department data to a separate table to achieve 3NF.
---
## Example Without Normalization

### Students Table

| StudentID | StudentName | Course | Teacher |
| --------- | ----------- | ------ | ------- |
| 1         | John        | PHP    | Amit    |
| 2         | Alice       | PHP    | Amit    |
| 3         | Bob         | MySQL  | Rahul   |

Problem:
* Teacher name "Amit" is repeated multiple times.
* If Amit's name changes, multiple rows must be updated.

---

# 1NF (First Normal Form)

### Rule

* Each column should contain only one value.
* No multiple values in a single column.

❌ Bad

| StudentID | Courses    |
| --------- | ---------- |
| 1         | PHP, MySQL |

✅ Good

| StudentID | Course |
| --------- | ------ |
| 1         | PHP    |
| 1         | MySQL  |

---

# 2NF (Second Normal Form)

### Rule

* Must already be in 1NF.
* Remove partial dependency.

Split course information into a separate table.

### Students

| StudentID | StudentName |
| --------- | ----------- |
| 1         | John        |
| 2         | Alice       |

### Courses

| CourseID | CourseName |
| -------- | ---------- |
| 1        | PHP        |
| 2        | MySQL      |

### Student_Courses

| StudentID | CourseID |
| --------- | -------- |
| 1         | 1        |
| 1         | 2        |
| 2         | 1        |

Now course details are stored only once.

---

# 3NF (Third Normal Form)

### Rule
* Must already be in 2NF.
* Remove transitive dependency.

❌ Bad
| EmployeeID | EmployeeName | Department | Manager |
| ---------- | ------------ | ---------- | ------- |
| 1          | John         | IT         | Rahul   |
| 2          | Alice        | HR         | Amit    |

Manager depends on Department, not Employee.

✅ Create separate Department table.

### Employees
| EmployeeID | EmployeeName | DepartmentID |
| ---------- | ------------ | ------------ |
| 1          | John         | 1            |
| 2          | Alice        | 2            |

### Departments
| DepartmentID | Department | Manager |
| ------------ | ---------- | ------- |
| 1            | IT         | Rahul   |
| 2            | HR         | Amit    |


MyISAM
======
Older storage engine
Faster for read-heavy operations
Locks the entire table when updating
No support for transactions or relationships

👉 Think: “Fast but not safe for complex operations”

InnoDB
======
Modern and default engine in MySQL
Supports transactions (commit/rollback)
Locks only the row being updated
Supports foreign keys
Better crash recovery

👉 Think: “Slightly heavier but safe and reliable”

Easy Memory Trick
MyISAM = My IS old (simple & fast read)
InnoDB = In New DB (modern, safe, powerful)

| Feature        | MyISAM                  | InnoDB                         |
| -------------- | ----------------------- | ------------------------------ |
| Transactions   | ❌ Not supported         | ✅ Supported (COMMIT, ROLLBACK) |
| Foreign Key    | ❌ Not supported         | ✅ Supported                    |
| Locking        | Table-level locking     | Row-level locking              |
| Performance    | Faster for simple reads | Better for mixed read/write    |
| Crash recovery | Weak                    | Strong (auto recovery)         |
| Data safety    | Less safe               | More reliable                  |
| Default engine | Older default           | Modern default                 |




---------------------------------------------------------

# Interview Answer (Short)

**Normalization is the process of organizing database tables to reduce data redundancy and improve data integrity by dividing data into related tables.**

Common forms:

1. **1NF** – No multiple values in a column.
2. **2NF** – Remove partial dependency.
3. **3NF** – Remove transitive dependency.

---

# Easy Real-Life Example

Imagine an e-commerce website:

❌ Single table:

| OrderID | CustomerName | CustomerAddress | Product |
| ------- | ------------ | --------------- | ------- |
| 1       | John         | Kolkata         | Laptop  |
| 2       | John         | Kolkata         | Mouse   |

Customer information is repeated.

✅ Normalize into:

**Customers**

| CustomerID | Name | Address |
| ---------- | ---- | ------- |

**Orders**

| OrderID | CustomerID |
| ------- | ---------- |

**OrderItems**
| OrderID | ProductID |

This reduces duplication and makes updates easier.

### Interview One-Liner

> "Normalization is a database design technique used to reduce duplicate data and improve data consistency by splitting data into related tables."




SQL:
=====
DDL (Data Definition Language):
-------------------------------
DDL commands are used to define the structure or schema of a database.

CREATE: Used to create objects in the database (e.g., tables, views, indexes).

CREATE TABLE Employees (
    EmployeeID INT,
    LastName VARCHAR(255),
    FirstName VARCHAR(255),
    ...
);

ALTER: Used to alter the structure of an existing database object.

ALTER TABLE Employees ADD COLUMN BirthDate DATE;

DROP: Used to delete objects from the database.

DROP TABLE Employees;


DML (Data Manipulation Language):
-----------------------------------

DML commands are used to manage data within database objects.

Examples:
SELECT: Retrieves data from a database.
SELECT * FROM Employees WHERE LastName = 'Smith';

INSERT: Adds new records to a table.
INSERT INTO Employees (EmployeeID, LastName, FirstName) VALUES (1, 'Smith', 'John');

UPDATE: Modifies existing records in a table.
UPDATE Employees SET FirstName = 'Jane' WHERE EmployeeID = 1;

DELETE: Deletes records from a table.
DELETE FROM Employees WHERE EmployeeID = 1;

DCL (Data Control Language):
-----------------------------

DCL commands are used to control access to data within the database.

Examples:

GRANT: Gives user access privileges to database objects.

GRANT SELECT ON Employees TO user1;
REVOKE: Takes back privileges granted from users.

REVOKE SELECT ON Employees FROM user1;

TCL (Transaction Control Language):
------------------------------------

TCL commands are used to manage the changes made by DML statements.
Examples:
COMMIT: Saves changes permanently.
COMMIT;

ROLLBACK: Reverts the database to its previous state since the last commit.
ROLLBACK;

SAVEPOINT: Sets a point in a transaction to which you can later roll back.
SAVEPOINT sp1;

SET TRANSACTION: Sets the characteristics of the transaction.
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;

To find the nth highest salary in a SQL table,
-------------------------------------------------
SELECT Salary
FROM Employees
ORDER BY Salary DESC
LIMIT 1 OFFSET n-1;


What are index cardinality and selectivity
===========================================

1. Index Cardinality
=====================
Cardinality = number of unique values in a column.

Example
id  country
1 India
2 India
3 USA
4 India
5 UK

For the country column:

Unique values are: India, USA, UK
Cardinality = 3
High Cardinality

2. Selectivity
==============
Selectivity tells how selective an index is — meaning how well it narrows down rows.

Formula:

Selectivity=total rows/unique values

Example
Table has 1000 rows.

country has 5 unique values
5/1000=0.005

Very low selectivity.

In MySQL:
==========

Both PRIMARY KEY and UNIQUE prevent duplicate values, but they are not the same.

| Feature                | PRIMARY KEY                | UNIQUE                            |
| ---------------------- | -------------------------- | --------------------------------- |
| Duplicates allowed?    | ❌ No                      | ❌ No                           |
| NULL allowed?          | ❌ No                      | ✅ Yes (usually one NULL in MySQL)|
| How many per table?    | Only 1                     | Multiple allowed                  |
| Main purpose           | Identify each row uniquely | Ensure column values stay unique  |
| Automatically indexed? | ✅ Yes                     | ✅ Yes                          |


66. What is the difference between NOW() and CURRENT_TIMESTAMP?

In MySQL, NOW() and CURRENT_TIMESTAMP are almost the same.

Both return the current date and time.

Quick Memory Trick
NOW() → regular function
CURRENT_TIMESTAMP → SQL standard timestamp keyword/function

Indexing in MYSQL
===================
An index in MySQL is like the index page of a book.

Instead of reading every page, MySQL can quickly find the required data.

Without Index
================
Imagine a table with 1 million users.

Query:

SELECT * FROM users
WHERE email='a@test.com';

Without index:

MySQL checks every row
Slow process
Called Full Table Scan

With Index
============
-- Create index on email column
CREATE INDEX idx_users_email 
ON users(email);

-- Query using indexed column
SELECT * 
FROM users
WHERE email = 'test@example.com';

Now MySQL can directly find the row quickly.

Much faster.




MYSQL Quick Optimization Checklist
=====================================

✅ Use indexes
✅ Avoid SELECT *
✅ Filter using WHERE
✅ Use LIMIT
✅ Use proper joins
✅ Check queries with EXPLAIN
✅ Index high-selectivity columns

4. Difference between SQL and MySQL?

SQL = language
MySQL = database software that uses SQL


19. How to get records with highest salary?
SELECT * FROM employees
WHERE salary = (
    SELECT MAX(salary) FROM employees
);

General Formula for Nth Highest Salary
======================================
SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET N-1;

1. LIMIT
==========
LIMIT tells MySQL:

“Return only this many rows.”

2. OFFSET
==========
OFFSET tells MySQL:

“Skip some rows first.”

Example
SELECT * FROM users
LIMIT 5 OFFSET 10;

Meaning:
skip first 10 rows
then return next 5 rows

LIMIT → how many rows
OFFSET → how many rows to skip

LIKE in MySQL
==============
LIKE is used for pattern matching in SQL.

It helps search text values.

Find names starting with A
===========================
SELECT * FROM users
WHERE name LIKE 'A%';


Find names ending with n
==========================
SELECT * FROM users
WHERE name LIKE '%n';

Find names containing ar
========================
SELECT * FROM users
WHERE name LIKE '%ar%';

4. Single Character _
=========================
Find names with exactly 4 letters starting with A

SELECT * FROM users
WHERE name LIKE 'A___';


| Pattern | Meaning            |
| ------- | ------------------ |
| `'A%'`  | Starts with A      |
| `'%A%'` | Contains A         |
| `'_A%'` | Second letter is A |



##############################################################################

MySQL Interview Questions & Answers (5 Years Experience)

1. What is MySQL?

MySQL is an open-source relational database management system used to store and manage data using SQL.

2. What is a database?

A database is a collection of organized data that can be easily accessed, managed, and updated.

3. What is SQL?

SQL (Structured Query Language) is used to communicate with databases for storing, retrieving, updating, and deleting data.

4. Difference between SQL and MySQL?
SQL = language
MySQL = database software that uses SQL

5. What are primary keys?

A primary key uniquely identifies each row in a table.

Example:

CREATE TABLE users (
   id INT PRIMARY KEY,
   name VARCHAR(100)
);

6. What is a foreign key?

A foreign key creates a relationship between two tables.

Example:

ALTER TABLE orders
ADD CONSTRAINT fk_user
FOREIGN KEY (user_id) REFERENCES users(id);

7. Difference between DELETE, TRUNCATE, and DROP?

Command       Purpose
DELETE        Removes selected rows
TRUNCATE      Removes all rows quickly
DROP          Deletes entire table

8. What is normalization?

Normalization organizes data to reduce duplication.

Common forms:

1NF
2NF
3NF
9. What is denormalization?

Denormalization adds duplicate data to improve read performance.

10. What is an index?

An index improves query speed.

Example:

CREATE INDEX idx_name ON users(name);

11. Types of indexes in MySQL?

Primary Index : A Primary Index is automatically created when a column is declared as PRIMARY KEY.
Unique Index : A Unique Index ensures no duplicate values are allowed in a column.
Composite Index : A Composite Index is an index created on multiple columns together.
Fulltext Index : A Fulltext Index is used for fast text searching in large text data.


12. What is a unique key?

It prevents duplicate values in a column.
No duplicate values are allowed in a column.

Example: user email


13. What is AUTO_INCREMENT?

Automatically increases numeric values.

Example:

id INT AUTO_INCREMENT PRIMARY KEY

14. Difference between CHAR and VARCHAR?

CHAR always stores fixed-length data.

Example
CHAR(10)

If you store:
'ABC'

MySQL stores:
'ABC       '

(extra spaces added)
Total size = 10 characters.

Best For

Fixed-size values like:
PIN code
Country code
Gender (M/F)

2. VARCHAR

VARCHAR stores only actual data length.
Best For
Variable-length values like:

names
emails
addresses

Example
VARCHAR(10)

If you store:
'ABC'
Only 3 characters are stored.
No extra spaces.

15. What is NOT NULL?

It prevents storing NULL values.

16. What is the default port of MySQL?

3306

17. What is a JOIN?

JOIN combines data from multiple tables.

18. Types of JOINs?

INNER JOIN
LEFT JOIN
RIGHT JOIN
CROSS JOIN

19. Explain INNER JOIN.

Returns matching records from both tables.

Example:

SELECT users.name, orders.amount
FROM users
INNER JOIN orders
ON users.id = orders.user_id;

20. Explain LEFT JOIN.

Returns all records from left table and matching rows from right table.

21. What is GROUP BY?

Used to group rows with same values.
group by state.
group by age.
group by gender

Example:

SELECT department, COUNT(*)
FROM employees
GROUP BY department;

22. What is HAVING?

HAVING filters grouped data.

Example:

SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;


23. Difference between WHERE and HAVING?

WHERE                          HAVING
Filters rows                   Filters groups
Used before GROUP BY           Used after GROUP BY

24. What is ORDER BY?

Sorts result data.

Example:

SELECT * FROM users ORDER BY name ASC;
25. What is LIMIT?

Restricts number of records.

Example:

SELECT * FROM users LIMIT 10;
26. What is DISTINCT?

Removes duplicate values.

Example:

SELECT DISTINCT city FROM users;

27. What is a view?

A virtual table created from SQL query.

Example:

CREATE VIEW active_users AS
SELECT * FROM users WHERE status='active';
28. What is a stored procedure?

A saved SQL program that can be reused.

29. What is a trigger?

A trigger automatically executes when INSERT, UPDATE, or DELETE happens.

30. What is a transaction?

A group of SQL operations executed together.

Commands:

START TRANSACTION
COMMIT
ROLLBACK

31. What is COMMIT?

Saves transaction changes permanently.

32. What is ROLLBACK?

Undo changes before commit.

33. What are ACID properties?

Atomicity
Consistency
Isolation
Durability

These ensure reliable transactions.

34. Difference between MyISAM and InnoDB?

MyISAM               InnoDB
Faster read          Supports transactions
No foreign key       Supports foreign key

35. What is a composite key?

A key made using multiple columns.

Example:

PRIMARY KEY (user_id, product_id)

36. What is a subquery?

A query inside another query.

Example:

SELECT * FROM employees
WHERE salary >
(SELECT AVG(salary) FROM employees);

37. What is a self join?

Joining a table with itself.

38. What is UNION?

Combines results of two queries and removes duplicates.

39. Difference between UNION and UNION ALL?

UNION                UNION ALL
Removes duplicates  Keeps duplicates
Slower              Faster

40. How to find duplicate records?

Example:

SELECT email, COUNT(*)
FROM users
GROUP BY email
HAVING COUNT(*) > 1;

41. How to find second highest salary?

Example:

SELECT MAX(salary)
FROM employees
WHERE salary <
(SELECT MAX(salary) FROM employees);

42. What is EXISTS?

Checks if subquery returns records.

43. What is the difference between IN and EXISTS?

IN  EXISTS
Better for small data Better for large data

44. What is a correlated subquery?

A subquery that depends on outer query values.

45. What is indexing issue?

Too many indexes slow INSERT/UPDATE operations.

46. How to optimize slow queries?
Use indexes
Avoid SELECT *
Use LIMIT
Optimize JOINs
Use EXPLAIN
47. What is EXPLAIN?

Used to analyze query performance.

Example:

EXPLAIN SELECT * FROM users;
48. What is a deadlock?

When two transactions wait for each other and get stuck.

49. What is database backup?

Creating copy of database for recovery.

Command:

mysqldump -u root -p database_name > backup.sql
50. What are your daily tasks as a MySQL developer with 5 years experience?

Example Answer:

Writing optimized SQL queries
Creating tables and indexes
Working with joins and stored procedures
Fixing slow queries
Database backup and monitoring
Supporting APIs and backend applications
Handling data migration and debugging




=====================================================
sql:
-----

DDl,DML,DCL,TCL sql query

Core php:
-----------
Interface,abstract class,abstract method



SQL:
=====
DDL (Data Definition Language):
-------------------------------

DDL commands are used to define the structure or schema of a database.

CREATE: Used to create objects in the database (e.g., tables, views, indexes).

CREATE TABLE Employees (
    EmployeeID INT,
    LastName VARCHAR(255),
    FirstName VARCHAR(255),
    ...
);

ALTER: Used to alter the structure of an existing database object.

ALTER TABLE Employees ADD COLUMN BirthDate DATE;

DROP: Used to delete objects from the database.

DROP TABLE Employees;


DML (Data Manipulation Language):
-----------------------------------

DML commands are used to manage data within database objects.

Examples:
SELECT: Retrieves data from a database.
SELECT * FROM Employees WHERE LastName = 'Smith';

INSERT: Adds new records to a table.
INSERT INTO Employees (EmployeeID, LastName, FirstName) VALUES (1, 'Smith', 'John');

UPDATE: Modifies existing records in a table.
UPDATE Employees SET FirstName = 'Jane' WHERE EmployeeID = 1;

DELETE: Deletes records from a table.
DELETE FROM Employees WHERE EmployeeID = 1;

DCL (Data Control Language):
-----------------------------

DCL commands are used to control access to data within the database.

Examples:

GRANT: Gives user access privileges to database objects.

GRANT SELECT ON Employees TO user1;
REVOKE: Takes back privileges granted from users.

REVOKE SELECT ON Employees FROM user1;

TCL (Transaction Control Language):
------------------------------------

TCL commands are used to manage the changes made by DML statements.
Examples:
COMMIT: Saves changes permanently.
COMMIT;

ROLLBACK: Reverts the database to its previous state since the last commit.
ROLLBACK;

SAVEPOINT: Sets a point in a transaction to which you can later roll back.
SAVEPOINT sp1;

SET TRANSACTION: Sets the characteristics of the transaction.
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;

To find the nth highest salary in a SQL table,
-------------------------------------------------
SELECT Salary
FROM Employees
ORDER BY Salary DESC
LIMIT 1 OFFSET n-1;

MyISAM vs InnoDB – Key Differences

| Feature                          | **InnoDB**                                 | **MyISAM**                               |
| -------------------------------- | ------------------------------------------ | ---------------------------------------- |
| **Transactions**                 | ✅ Supports (`BEGIN`, `COMMIT`, `ROLLBACK`) | ❌ No transaction support                 |
| **Foreign Keys**                 | ✅ Supports                                 | ❌ Not supported                          |
| **Locking**                      | Row-level locking (more concurrent)        | Table-level locking (slower under load)  |
| **Crash Recovery**               | ✅ Automatic recovery (redo logs)           | ❌ Manual repair needed                   |
| **Storage**                      | Data + indexes stored together (clustered) | Data and indexes stored separately       |
| **Full-Text Search**             | ✅ Since MySQL 5.6                          | ✅ Supported earlier                      |
| **Speed**                        | Slower on read-heavy, faster on write-safe | Fast on read-heavy (no integrity checks) |
| **ACID Compliance**              | ✅ Yes                                      | ❌ No                                     |
| **Default Engine (MySQL ≥ 5.5)** | ✅ Yes (InnoDB)                             | ❌ Optional                               |


Primary Key, UNique Key, Foregin Key , candidate Key
=======================================================

Primary Key
✅ Definition:
A Primary Key uniquely identifies each record in a table. It:
Must be unique
Must be NOT NULL
Only one primary key per table

Unique Key (Constraint)
✅ Definition:
A Unique Key ensures that all values in a column (or group of columns) are distinct.

Allows NULLs (but only one per column)
A table can have multiple unique keys

email is a unique key 

Foreign Key
✅ Definition:
A Foreign Key is a field in one table that references the primary key of another table.

Ensures referential integrity
Can prevent deleting referenced records


Candidate Key
✅ Definition:
A Candidate Key is any column or combination of columns that can uniquely identify a row in a table.

A table can have multiple candidate keys.
The primary key is chosen from among the candidate keys


1. CHAR(10)
A CHAR(10) column stores fixed-length strings of exactly 10 characters.

If you store 'Hi', it will pad it with spaces to make it 'Hi________' (total 10 characters).

Always uses 10 bytes of storage (if character set is 1 byte/char, like latin1).


🔷 2. VARCHAR(10)
A VARCHAR(10) column stores variable-length strings up to 10 characters.

If you store 'Hi', it stores only 2 characters — no padding.

Uses 1 or 2 extra bytes for length info (depending on total length).


$$a – Variable Variable
============================
$$a is used to create a variable from another variable's value.

$a = "name";
$name = "Chandan";

echo $$a;  // Output: Chandan

&$a – Reference Variable == points to same memory address
===========================
&$a creates a reference, not a copy.
Both variables point to the same memory location.


$x = 10;
$y = &$x;  // $y is a reference to $x

$y = 20;

echo $x;  // Output: 20 (because $x and $y refer to same value)



=================================================================

1. GROUP BY
Q: What is GROUP BY in MySQL?

A: GROUP BY groups rows that have the same values into summary rows, like "total sales by category".

Example:


SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department;

2. HAVING
Q: What is HAVING? How is it different from WHERE?

A: HAVING is used to filter results after grouping, whereas WHERE filters before grouping.

Example:


SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;


3. LIKE
Q: What does LIKE do?

A: LIKE is used in WHERE to search for a specified pattern in a column.

xamples Using LIKE
1. Starts With

SELECT * FROM employees
WHERE name LIKE 'A%';   -- names starting with A
✔ Matches: Anil, Ajay, Alice

2. Ends With

SELECT * FROM employees
WHERE name LIKE '%n';   -- names ending with 'n'
✔ Matches: Arun, Kiran

3. Contains

SELECT * FROM employees
WHERE name LIKE '%li%';  -- names containing 'li'
✔ Matches: Alice, Alina, Malik

4. Exactly 3-letter Names

SELECT * FROM employees
WHERE name LIKE '___';   -- exactly 3 characters
✔ Matches: Raj, Ali, Tom

5. Second Letter is 'a'

SELECT * FROM employees
WHERE name LIKE '_a%';
✔ Matches: Ravi, Ram, Manoj

6. Name starts with A and ends with N

SELECT * FROM employees
WHERE name LIKE 'A%n';
✔ Matches: Arun, Anand




4. Indexing
Q: What is an index? Why is it used?

A: An index improves the speed of data retrieval at the cost of extra space and slower inserts/updates.

Example:


CREATE INDEX idx_name ON employees(name);
5. Primary Key
Q: What is a Primary Key?

A: A column (or set of columns) that uniquely identifies each row in a table.

Example:


CREATE TABLE students (
  student_id INT PRIMARY KEY,
  name VARCHAR(50)
);
6. Foreign Key
Q: What is a Foreign Key?

A: A key used to link two tables together, referencing the primary key of another table.

Example:


CREATE TABLE orders (
  order_id INT PRIMARY KEY,
  student_id INT,
  FOREIGN KEY (student_id) REFERENCES students(student_id)
);
7. Second Highest Salary
Q: How do you find the second highest salary?

Method 1: Using LIMIT


SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;
Method 2: Using Subquery


SELECT MAX(salary) AS SecondHighest
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
8. Find Duplicates
Q: How do you find duplicate records in a table?

Example:


SELECT name, COUNT(*)
FROM employees
GROUP BY name
HAVING COUNT(*) > 1;
9. DELETE vs TRUNCATE vs DROP
Operation   Description Can be Rolled Back (In Transaction)?
DELETE  Removes specific rows   ✅ Yes
TRUNCATE    Removes all rows, faster than DELETE    ❌ No
DROP    Removes entire table (structure + data) ❌ No

Examples:


DELETE FROM employees WHERE id = 1;

TRUNCATE TABLE employees;

DROP TABLE employees;
10. More Common Questions
✅ What is the difference between INNER JOIN, LEFT JOIN, and RIGHT JOIN?

-- INNER JOIN: Only matching rows
SELECT * FROM A INNER JOIN B ON A.id = B.a_id;

-- LEFT JOIN: All rows from A + matched rows from B
SELECT * FROM A LEFT JOIN B ON A.id = B.a_id;

-- RIGHT JOIN: All rows from B + matched rows from A
SELECT * FROM A RIGHT JOIN B ON A.id = B.a_id;
✅ What is AUTO_INCREMENT?

CREATE TABLE items (
  id INT AUTO_INCREMENT,
  name VARCHAR(100),
  PRIMARY KEY (id)
);
✅ What is the difference between CHAR and VARCHAR?
CHAR(n) is fixed length (padded with spaces).

VARCHAR(n) is variable length.

Would you like this content as a downloadable PDF or want more advanced interview questions (joins, normalization, stored procedures, etc.)?



You said:
more question answers 


ChatGPT said:
Here are more MySQL interview questions and answers with practical examples, covering intermediate to advanced topics:

🔁 11. JOINS
Q: What are the types of joins in MySQL?
Join Type   Description
INNER JOIN  Returns only matching rows
LEFT JOIN   All rows from left table + matched rows
RIGHT JOIN  All rows from right table + matched rows
FULL JOIN   Not directly supported in MySQL (simulate with UNION)

Example:


-- INNER JOIN
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id;

-- LEFT JOIN
SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.id;
🧮 12. Aggregate Functions
Q: What are aggregate functions in SQL?

These perform a calculation on a set of values:

COUNT() — total number of rows

SUM() — total sum

AVG() — average

MIN() / MAX() — min/max values

Example:


SELECT department, COUNT(*) AS total_employees, AVG(salary) AS avg_salary
FROM employees
GROUP BY department;
🔍 13. DISTINCT
Q: What is DISTINCT used for?

To remove duplicate records from the result set.

Example:


SELECT DISTINCT city FROM customers;
🧱 14. Constraints in MySQL
Types:

NOT NULL

UNIQUE

PRIMARY KEY

FOREIGN KEY

CHECK

DEFAULT

Example:


CREATE TABLE users (
  id INT PRIMARY KEY,
  email VARCHAR(100) UNIQUE,
  age INT CHECK (age >= 18),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
🧾 15. Subqueries
Q: What is a subquery?

A query nested inside another query.

Example:


SELECT name FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
🔄 16. UNION vs UNION ALL
UNION: Combines results and removes duplicates.

UNION ALL: Includes all duplicates.

Example:


SELECT city FROM customers
UNION
SELECT city FROM suppliers;
🛑 17. EXISTS vs IN
IN: Best for small result sets.

EXISTS: Better for checking existence (faster with large data).

Example:


-- Using IN
SELECT * FROM employees WHERE dept_id IN (SELECT id FROM departments WHERE name = 'Sales');

-- Using EXISTS
SELECT * FROM employees e
WHERE EXISTS (
  SELECT 1 FROM departments d WHERE d.id = e.dept_id AND d.name = 'Sales'
);
🧰 18. Stored Procedures
Q: What is a stored procedure?

A reusable block of SQL logic stored in the database.

Example:


DELIMITER //
CREATE PROCEDURE GetEmployees()
BEGIN
  SELECT * FROM employees;
END //
DELIMITER ;

CALL GetEmployees();
🏷️ 19. Views
Q: What is a view?

A virtual table based on a SELECT query.

Example:


CREATE VIEW high_earners AS
SELECT name, salary FROM employees WHERE salary > 100000;

SELECT * FROM high_earners;
🕵️ 20. Case Statement
Q: How do you use CASE in SQL?

Example:


SELECT name, salary,
  CASE 
    WHEN salary >= 100000 THEN 'High'
    WHEN salary >= 50000 THEN 'Medium'
    ELSE 'Low'
  END AS salary_grade
FROM employees;
📉 21. Normalization (Theory Question)
Q: What is normalization?

Process of organizing data to reduce redundancy.

Normal Forms:

1NF: Atomic columns (no repeating groups)

2NF: No partial dependency (depends on full primary key)

3NF: No transitive dependency (non-key depends only on key)

🕓 22. Current Date/Time Functions

SELECT NOW();       -- Current datetime
SELECT CURDATE();   -- Current date
SELECT CURTIME();   -- Current time
💾 23. LIMIT with OFFSET
Q: How do you paginate results in MySQL?


SELECT * FROM products
ORDER BY name
LIMIT 10 OFFSET 20; -- Skip first 20, then return 10
🧩 24. ENUM and SET Types

CREATE TABLE shirts (
  size ENUM('S', 'M', 'L', 'XL'),
  color SET('Red', 'Green', 'Blue')
);
📊 25. Explain Query Plan
Q: How do you check how MySQL runs a query?


EXPLAIN SELECT * FROM employees WHERE salary > 50000;
===================================================================
