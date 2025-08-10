# MySQL AUTO_INCREMENT

The `AUTO_INCREMENT` attribute in MySQL is used to generate a unique number automatically when a new record is inserted into a table. It is commonly used for the primary key column.

---

## Key Points:
- Only one `AUTO_INCREMENT` column is allowed per table.
- The column must be indexed (usually a primary key).
- Values start at 1 by default and increase by 1 with each new record.
- You can set the starting point using `AUTO_INCREMENT = value` when creating or altering a table.

---

## Syntax:

```sql
CREATE TABLE table_name (
    id INT NOT NULL AUTO_INCREMENT,
    column_name datatype,
    PRIMARY KEY (id)
);
```

# Examples

## Example 1: Basic AUTO_INCREMENT column

```sql
CREATE TABLE employees (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(50),
    PRIMARY KEY (id)
);
```

## Example 2: Insert without specifying AUTO_INCREMENT column

```sql
INSERT INTO employees (name) VALUES ('Alice'), ('Bob');
```

  The id column values will be assigned automatically (1, 2, ...).

## Example 3: Set AUTO_INCREMENT starting value

```sql
CREATE TABLE products (
    product_id INT NOT NULL AUTO_INCREMENT,
    product_name VARCHAR(100),
    PRIMARY KEY (product_id)
) AUTO_INCREMENT=1000;
```

  The first inserted product will have product_id = 1000.

## Example 4: Alter table to add AUTO_INCREMENT

```sql
ALTER TABLE employees MODIFY COLUMN id INT NOT NULL AUTO_INCREMENT;
```

  Adds AUTO_INCREMENT to an existing column.

## Example 5: Manually insert value into AUTO_INCREMENT column

```sql
INSERT INTO employees (id, name) VALUES (10, 'Charlie');
```

  You can manually specify an id. The next auto-generated value will be greater than the highest existing value.

### Notes:

  If you insert a value higher than the current maximum, the next AUTO_INCREMENT value will continue from there.

  AUTO_INCREMENT works only on integer types like INT, BIGINT, SMALLINT.
