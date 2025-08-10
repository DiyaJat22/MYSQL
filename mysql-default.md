# MySQL DEFAULT Constraint

The `DEFAULT` constraint is used to provide a default value for a column when no value is specified during an `INSERT` operation. This ensures that the column will have a predefined value if the user does not explicitly provide one.

---

## Purpose

- Automatically assigns a value to a column if none is provided.
- Helps maintain data consistency.
- Simplifies data insertion by reducing the need to specify every column.

---

## Syntax

```sql
CREATE TABLE table_name (
    column_name datatype DEFAULT default_value
);
```

## Example 1: Create Table with DEFAULT Values

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    status VARCHAR(20) DEFAULT 'active',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

  If status is not specified during insert, it defaults to 'active'.

  created_at defaults to the current timestamp.

## Example 2: Insert Data Using DEFAULT Values

```sql
INSERT INTO users (id, username) VALUES (1, 'Alice');
```

  status will be 'active'.

  created_at will be set to the current timestamp automatically.

## Example 3: Override DEFAULT Values

```sql
INSERT INTO users (id, username, status) VALUES (2, 'Bob', 'inactive');
```

  status is explicitly set to 'inactive', overriding the default.

### Notes

  DEFAULT values can be constants or expressions (like CURRENT_TIMESTAMP).

  DEFAULT applies only when a column is omitted or NULL is explicitly replaced (depending on the SQL mode).

  Not all data types support default expressions.
