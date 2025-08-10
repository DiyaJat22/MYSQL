# MySQL SHOW DATABASES

The `SHOW DATABASES` statement is used to list all databases present on the MySQL server.

---

## Syntax

```sql
SHOW DATABASES;
```

## Example 1: List All Databases

```sql
SHOW DATABASES;
```

This command displays all databases you have access to.

## Example 2: Filter Databases Using LIKE

To show databases matching a pattern, use LIKE:

```sql
SHOW DATABASES LIKE 'test%';
```

This shows databases with names starting with test.

## Example 3: Filter Databases Using WHERE Clause (MySQL 8.0+)

You can also use a WHERE clause:

```sql
SHOW DATABASES WHERE `Database` LIKE '%db';
```

Shows databases ending with db.

## Notes

  The list includes all databases the current user can access.

  Use this command to confirm creation or deletion of databases.

  It is a read-only command; does not modify data.

