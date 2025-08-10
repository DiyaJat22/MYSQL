# MySQL DROP TABLE

The `DROP TABLE` statement is used to delete one or more tables from a database permanently. All the data and structure in the dropped table(s) are lost.

---

## Syntax

```sql
DROP TABLE [IF EXISTS] table_name1, table_name2, ...;
```

 IF EXISTS: Optional. Prevents error if the table does not exist.

 table_name: Name of the table(s) to drop.

## Example 1: Drop a Single Table

```sql
DROP TABLE employees;
```

Drops the employees table.

## Example 2: Drop Multiple Tables

```sql
DROP TABLE employees, departments;
```

Drops both employees and departments tables in one command.

## Example 3: Drop Table Only If It Exists

Prevents error if the table does not exist.

```sql
DROP TABLE IF EXISTS employees;
```

## Example 4: Drop Multiple Tables Only If They Exist

```sql
DROP TABLE IF EXISTS employees, departments;
```

## Example 5: Drop a Table and Check Before Dropping

```sql
SHOW TABLES;
DROP TABLE IF EXISTS temp_data;
SHOW TABLES;
```

Use SHOW TABLES to verify tables before and after dropping.

## Example 6: Drop Temporary Table

```sql
DROP TEMPORARY TABLE IF EXISTS temp_users;
```

Drops a temporary table named temp_users if it exists.

## Important Notes

  Dropping a table deletes all data and cannot be undone.

  Use with caution, especially on production databases.

  You must have appropriate privileges to drop tables.

