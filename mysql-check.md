# MySQL CHECK Constraint

The `CHECK` constraint is used to limit the values that can be placed in a column by enforcing a condition. It ensures that all values in a column satisfy a specific Boolean expression.

---

## Purpose

- Enforce domain integrity by restricting allowed values.
- Prevent invalid data from being inserted or updated.
- Help maintain data consistency.

---

## Syntax

```sql
CREATE TABLE table_name (
    column_name datatype CHECK (condition)
);
```

## Example 1: Simple CHECK Constraint

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT CHECK (age >= 18)
);
```

  The age column must have values greater than or equal to 18.

## Example 2: CHECK with Multiple Conditions

```sql
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    price DECIMAL(10,2) CHECK (price > 0),
    quantity INT CHECK (quantity >= 0)
);
```

  price must be positive.

  quantity cannot be negative.

### Notes

  CHECK constraints are supported starting from MySQL 8.0.16.

  Before MySQL 8.0.16, the CHECK clause was parsed but ignored.

  Violating a CHECK constraint during INSERT or UPDATE results in an error.

