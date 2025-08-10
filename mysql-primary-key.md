# MySQL PRIMARY KEY Constraint

The `PRIMARY KEY` constraint uniquely identifies each record in a database table. It combines the properties of `NOT NULL` and `UNIQUE`, ensuring that the key column(s) contain unique, non-null values.

---

## Purpose

- Uniquely identify each row in a table.
- Improve data integrity and indexing.
- Enforce uniqueness and prevent null values in the key column(s).

---

## Usage Examples

### Example 1: Create Table with Single Column Primary Key

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```

  id is the primary key and must be unique and not null.

## Example 2: Create Table with Auto-Increment Primary Key

```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT
);
```

  id automatically increments for each new record.

## Example 3: Composite Primary Key (Multiple Columns)

```sql
CREATE TABLE order_items (
    order_id INT,
    product_id INT,
    quantity INT,
    PRIMARY KEY (order_id, product_id)
);
```

  Combination of order_id and product_id uniquely identifies each row.

## Example 4: Add Primary Key to Existing Table

```sql
ALTER TABLE employees
ADD PRIMARY KEY (id);
```

### Notes

  A table can have only one primary key.

  Primary key columns cannot contain NULL.

  Primary keys improve performance with indexing.

