# MySQL DROP DATABASE

The `DROP DATABASE` statement deletes an existing database and all its contents permanently.

---

## Syntax

```sql
DROP DATABASE [IF EXISTS] database_name;
```

## Example 1: Basic Drop Database

Delete a database named testDB:

```sql
DROP DATABASE testDB;
```

## Example 2: Drop Database Only If It Exists

Prevents error if the database doesn't exist:

```sql
DROP DATABASE IF EXISTS testDB;
```

## Example 3: Drop Multiple Databases (One by One)

MySQL does not support dropping multiple databases in one command, so run these separately:

```sql
DROP DATABASE IF EXISTS salesDB;
DROP DATABASE IF EXISTS hrDB;
DROP DATABASE IF EXISTS marketingDB;
```

## Example 4: Drop Database and Handle Errors Gracefully

Using IF EXISTS helps avoid errors if the database is missing.

```sql
DROP DATABASE IF EXISTS mydb;
```

