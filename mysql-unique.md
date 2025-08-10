# MySQL UNIQUE Constraint

The `UNIQUE` constraint ensures that all values in a column (or a set of columns) are distinct across the table. It prevents duplicate values in the specified column(s).

---

## Purpose

- To enforce uniqueness of data in a column.
- Helps maintain data integrity by avoiding duplicate entries.
- Multiple UNIQUE constraints can be defined on a table.

---

## Usage Examples

### Example 1: Create Table with UNIQUE Column

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    username VARCHAR(50) UNIQUE,
    email VARCHAR(100) UNIQUE
);
```

  Both username and email must be unique.

## Example 2: Add UNIQUE Constraint to Existing Table

```sql
ALTER TABLE employees
ADD UNIQUE (email);
```

## Example 3: Insert Data with UNIQUE Constraint

```sql
INSERT INTO users (id, username, email) VALUES (1, 'alice', 'alice@example.com');
INSERT INTO users (id, username, email) VALUES (2, 'bob', 'bob@example.com');
```

## Example 4: Attempt to Insert Duplicate (Error)

```sql
INSERT INTO users (id, username, email) VALUES (3, 'alice', 'alice2@example.com');
```

This will cause an error because username 'alice' already exists.

### Notes

  UNIQUE constraint allows multiple NULLs (except in some versions or when combined with other constraints).

  You can create a unique index to enforce uniqueness.

  PRIMARY KEY also enforces uniqueness but only one primary key is allowed per table.

