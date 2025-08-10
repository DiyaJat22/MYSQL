# MySQL CREATE INDEX - Description and Examples

## What is an Index in MySQL?

  An index is a database structure that improves the speed of data retrieval operations on a table.

  Indexes help MySQL find rows faster, just like an index in a book helps you find information quickly.

  Without indexes, MySQL must perform a full table scan, checking each row.

## Syntax of CREATE INDEX

```sql
CREATE [UNIQUE|FULLTEXT|SPATIAL] INDEX index_name
ON table_name (column1 [(length)] [, column2, ...]);
```

  UNIQUE: Ensures all values in the index are unique.

  FULLTEXT: For full-text searching (only on MyISAM/InnoDB with full-text support).

  SPATIAL: For spatial data types.

  index_name: Name of the index.

  table_name: Table to which the index is added.

  column(s): Column or columns to be indexed.

# Basic Examples

## Example 1: Create a simple index

```sql
CREATE INDEX idx_employee_name
ON employees (name);
```

  This creates an index named idx_employee_name on the name column of the employees table.

  Speeds up searches or queries that filter by name.

## Example 2: Create a unique index

```sql
CREATE UNIQUE INDEX idx_email_unique
ON employees (email);
```

  Ensures no duplicate values exist in the email column.

  Useful for columns like emails or usernames.

## Example 3: Create a multi-column (composite) index

```sql
CREATE INDEX idx_name_age
ON employees (name, age);
```

  Index includes both name and age columns.

  Optimizes queries filtering by both columns together.

## Example 4: Create a FULLTEXT index (for text searching)

```sql
CREATE FULLTEXT INDEX idx_bio_fulltext
ON employees (bio);
```

  Enables full-text search on the bio column (must be TEXT type).

### Additional Notes

  Indexes consume disk space and can slow down INSERT, UPDATE, and DELETE operations because the index must be updated.

  Use indexes wisely on columns that are frequently searched or used in JOINs.

  Use SHOW INDEX FROM table_name; to list indexes on a table.

  You can also create indexes while creating the table with the CREATE TABLE statement.


| Index Type      | Syntax Example                                   | Use Case                                  |
|-----------------|-------------------------------------------------|-------------------------------------------|
| Simple Index    | `CREATE INDEX idx_col ON table(col);`           | Speed up searches on one column           |
| Unique Index    | `CREATE UNIQUE INDEX idx_unique ON table(col);` | Ensure uniqueness of column values        |
| Composite Index | `CREATE INDEX idx_multi ON table(col1, col2);`  | Optimize queries using multiple columns   |
| Fulltext Index  | `CREATE FULLTEXT INDEX idx_fulltext ON table(col);` | Enable text search in large text columns  |
