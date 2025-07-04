# MySQL-Series
Step by Step on MySQL.

Here's a README file structure you can use for your GitHub repository, detailing your journey through SQL, specifically focusing on the "Beginner Series" for now.

-----

# My SQL Learning Journey

Welcome to my repository documenting my journey to master SQL\! This repository will serve as a structured log of my progress, from foundational concepts to advanced techniques, using MySQL as my primary database system.

## Table of Contents

Beginner Series😊(-Alex the Analyst and ALX Kenya Bootcamp-)
      * 1. Installing MySQL and Creating Databases(https://youtu.be/wgRwITQHszU?si=65ewNXk6uQhjbJMd)
      * 2. SELECT Statements in MySQL(https://youtu.be/HYD8KjPB9F8?si=iKyhybPf393_M-pE)
      * 3. WHERE Clause in MySQL(https://youtu.be/MARn_mssG4A?si=yFngQaxMe7Wgd5oy)
      * 4. GROUP BY + ORDER BY in MySQL(https://youtu.be/zgYqUP_PhQo?si=wfvbLzVUH5wQdNKQ)
      * 5. HAVING vs. WHERE in MySQL(https://youtu.be/dCNjUOc1cBY?si=4I9rMiFIHqUT5C0N)
      * 6. LIMIT + Aliasing in MySQL(https://youtu.be/ZnAydTqCtFU?si=8sFlQMeNSpazOWRi)
  * Intermediate Series (-Alex the Analyst and ALX Kenya Bootcamp-)
  * Advanced Series (-Alex the Analyst and ALX Kenya Bootcamp-)

-----

## Beginner Series

This section covers the fundamental concepts of SQL, starting with setting up the environment and progressing through essential query operations. Each subsection will contain code examples, explanations, and any relevant notes from my learning.

### 1\. Installing MySQL and Creating Databases

This initial step covers the setup of the MySQL environment on my local machine. It includes:

  * **Installation Process:** Steps taken to install MySQL Community Server and MySQL Workbench (or command-line client).

  * **Connecting to MySQL:** How to establish a connection to the MySQL server.

  * **Database Creation:** Commands and examples for creating new databases.

    ```sql
    -- Example: Creating a new database
    CREATE DATABASE IF NOT EXISTS my_first_database;

    -- Example: Using a database
    USE my_first_database;
    ```

  * **Table Creation (Basic):** Simple examples of creating tables within the newly created database.

    ```sql
    -- Example: Creating a simple table
    CREATE TABLE IF NOT EXISTS students (
        id INT PRIMARY KEY AUTO_INCREMENT,
        first_name VARCHAR(50),
        last_name VARCHAR(50),
        age INT
    );
    ```

### 2\. SELECT Statements in MySQL

This section delves into the most fundamental SQL command: `SELECT`. It covers retrieving data from tables.

  * **Basic SELECT:** Retrieving all columns or specific columns.

    ```sql
    -- Example: Selecting all columns
    SELECT * FROM students;

    -- Example: Selecting specific columns
    SELECT first_name, last_name FROM students;
    ```

  * **Understanding `FROM` Clause:** Specifying the table from which to retrieve data.

### 3\. WHERE Clause in MySQL

The `WHERE` clause is crucial for filtering data based on specified conditions.

  * **Filtering with Operators:** Using comparison operators (`=`, `!=`, `<`, `>`, `<=`, `>=`).

  * **Logical Operators:** Combining conditions with `AND`, `OR`, `NOT`.

  * **`LIKE` Operator:** Pattern matching with wildcards (`%`, `_`).

  * **`IN` and `BETWEEN`:** Filtering for values within a set or range.

  * **`IS NULL` and `IS NOT NULL`:** Checking for null values.

    ```sql
    -- Example: Selecting students older than 20
    SELECT * FROM students WHERE age > 20;

    -- Example: Selecting students named 'John' OR 'Jane'
    SELECT * FROM students WHERE first_name = 'John' OR first_name = 'Jane';

    -- Example: Selecting students whose last name starts with 'Sm'
    SELECT * FROM students WHERE last_name LIKE 'Sm%';
    ```

### 4\. GROUP BY + ORDER BY in MySQL

This section explores how to group data and order the results.

  * **`GROUP BY`:** Aggregating rows that have the same values in specified columns.

      * **Aggregate Functions:** `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`.

  * **`ORDER BY`:** Sorting the result set in ascending (`ASC`) or descending (`DESC`) order.

    ```sql
    -- Example: Counting students by age
    SELECT age, COUNT(id) AS number_of_students
    FROM students
    GROUP BY age;

    -- Example: Ordering students by last name in ascending order
    SELECT * FROM students ORDER BY last_name ASC;

    -- Example: Ordering by age descending, then first name ascending
    SELECT * FROM students ORDER BY age DESC, first_name ASC;
    ```

### 5\. HAVING vs. WHERE in MySQL

A key distinction in SQL queries is understanding when to use `WHERE` and when to use `HAVING`.

  * **`WHERE` Clause:** Filters *individual rows* *before* grouping.

  * **`HAVING` Clause:** Filters *groups* *after* the `GROUP BY` clause has been applied.

    ```sql
    -- Example: Using WHERE to filter before grouping
    SELECT age, COUNT(id) AS number_of_students
    FROM students
    WHERE age > 18 -- Filters individual students
    GROUP BY age;

    -- Example: Using HAVING to filter groups
    SELECT age, COUNT(id) AS number_of_students
    FROM students
    GROUP BY age
    HAVING COUNT(id) > 2; -- Filters groups where the count is greater than 2
    ```

### 6\. LIMIT + Aliasing in MySQL

These clauses help in controlling the output and making queries more readable.

  * **`LIMIT`:** Restricting the number of rows returned by a query. Useful for pagination or top-N queries.

      * **Offset:** Specifying a starting point for the limit.

  * **Aliasing (`AS`):** Giving temporary names to columns or tables in the query result. Improves readability and can be useful in complex queries.

    ```sql
    -- Example: Limiting to the first 5 students
    SELECT * FROM students LIMIT 5;

    -- Example: Limiting to 3 students, starting from the 6th student (offset 5)
    SELECT * FROM students LIMIT 3 OFFSET 5;

    -- Example: Aliasing a column
    SELECT first_name AS StudentFirstName, last_name AS StudentLastName
    FROM students;

    -- Example: Aliasing a table (useful in joins)
    SELECT s.first_name, s.age
    FROM students AS s;
    ```

-----

## Intermediate Series (Coming Soon\!)

This section will cover more advanced SQL concepts, including:

  * Joins (INNER, LEFT, RIGHT, FULL, SELF)
  * Subqueries
  * UNION, UNION ALL, INTERSECT, EXCEPT
  * Data Manipulation Language (DML): INSERT, UPDATE, DELETE
  * Views

## Advanced Series (Coming Soon\!)

This section will delve into highly advanced topics such as:

  * Window Functions
  * Common Table Expressions (CTEs)
  * Stored Procedures and Functions
  * Triggers
  * Indexes and Performance Optimization
  * Transactions

-----

Feel free to explore the individual folders and files within this repository for detailed examples and my personal notes on each topic. Suggestions and feedback are always welcome as I continue this learning journey\!
