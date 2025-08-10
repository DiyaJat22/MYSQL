# MySQL FOREIGN KEY Constraint

A **FOREIGN KEY** constraint is used to link two tables together. It enforces referential integrity by ensuring that a value in one table corresponds to a valid value in another table.

---

## Purpose

- Maintain consistent and valid relationships between tables.
- Prevent orphan records by restricting invalid references.
- Cascade changes (optional) to keep related data synchronized.

---

## Syntax

```sql
FOREIGN KEY (column_name) REFERENCES parent_table(parent_column)
```

## Example 1: Create Tables with Foreign Key

```sql
CREATE TABLE departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50) NOT NULL
);

CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name VARCHAR(100),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);
```

  The dept_id in employees references dept_id in departments.

  Ensures dept_id in employees exists in departments.

## Example 2: Foreign Key with ON DELETE CASCADE

```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name VARCHAR(100),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
    ON DELETE CASCADE
);
```

  If a department is deleted, all employees in that department are deleted automatically.

## Example 3: Add Foreign Key to Existing Table

```sql
ALTER TABLE employees
ADD CONSTRAINT fk_dept
FOREIGN KEY (dept_id) REFERENCES departments(dept_id);
```

### Notes

  Both tables must use the same storage engine (e.g., InnoDB) to support foreign keys.

  Foreign keys improve data integrity but may impact performance.

  You can define actions like ON DELETE SET NULL, ON UPDATE CASCADE for automatic updates or deletes.

