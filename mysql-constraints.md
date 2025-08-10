# MySQL Constraints — Theory

In MySQL, **constraints** are rules applied to table columns to enforce data integrity, accuracy, and reliability. Constraints restrict the kind of data that can be inserted or updated in a database table to ensure the correctness and consistency of the data.

---

## Purpose of Constraints

- **Data Integrity:** Ensure that data entered into the database is valid, consistent, and reliable.
- **Prevent Invalid Data:** Avoid insertion of incorrect or inconsistent data.
- **Enforce Relationships:** Maintain logical connections between tables.
- **Automatic Data Management:** Apply default values or restrict modifications according to rules.

---

## Types of Constraints in MySQL

1. **NOT NULL**  
   Requires that a column must have a value; NULL values are not allowed.

2. **UNIQUE**  
   Ensures that all values in a column (or a set of columns) are unique across the table.

3. **PRIMARY KEY**  
   A combination of `NOT NULL` and `UNIQUE`. Uniquely identifies each row in a table.

4. **FOREIGN KEY**  
   Establishes a link between columns in two tables, enforcing referential integrity.

5. **CHECK**  
   Enforces a condition that data must satisfy before being accepted (supported from MySQL 8.0 onwards).

6. **DEFAULT**  
   Provides a default value for a column when no value is specified during insert.

---

## Why Are Constraints Important?

- They **ensure data validity** by restricting invalid entries.
- They **prevent duplication** of unique data.
- They **maintain relationships** between tables, preventing orphan records.
- They **simplify data management** by enforcing automatic rules and defaults.

---

## Summary

Constraints are essential in designing robust, reliable databases. They act as safeguards that maintain the quality and consistency of the data stored in MySQL tables.

