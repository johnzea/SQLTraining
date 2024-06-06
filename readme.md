# SQL Training Guide

## Table of Contents

1. [Introduction](#introduction)
2. [Basic SQL Commands](#basic-sql-commands)
    - [Creating Tables](#creating-tables)
    - [Inserting Data](#inserting-data)
    - [Selecting Data](#selecting-data)
    - [Updating Data](#updating-data)
    - [Deleting Data](#deleting-data)
3. [Intermediate SQL Commands](#intermediate-sql-commands)
    - [Joins](#joins)
    - [Group By](#group-by)
    - [Subqueries](#subqueries)

## Introduction

SQL (Structured Query Language) is a standard programming language used to manage and manipulate relational databases. This guide will walk you through the basics of SQL, from creating tables to more advanced topics like transactions and indexing.

## Basic SQL Commands

### Creating Tables

``` sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    birth_date DATE,
    hire_date DATE
);
```

### Inserting Data

``` sql
INSERT INTO employees (id, first_name, last_name, birth_date, hire_date)
VALUES (1, 'John', 'Doe', '1980-01-01', '2005-03-15');
```

### Selecting Data
``` sql
SELECT * FROM employees;
```

### Updating Data
``` sql
UPDATE employees
SET first_name = 'Jane'
WHERE id = 1;
```

### Deleting Data
``` sql
DELETE FROM employees
WHERE id = 1;
```

### Intermediate SQL Commands
#### Joins
##### Inner Join
``` sql
SELECT employees.first_name, departments.name
FROM employees
INNER JOIN departments ON employees.department_id = departments.id;
```

#### Left Join
``` sql
SELECT employees.first_name, departments.name
FROM employees
LEFT JOIN departments ON employees.department_id = departments.id;
```
##### Group By
```sql
SELECT department_id, COUNT(*)
FROM employees
GROUP BY department_id;
```

#### Subqueries
```sql
SELECT first_name, last_name
FROM employees
WHERE department_id = (
    SELECT id
    FROM departments
    WHERE name = 'Sales'
);
```
