# The MySQL CREATE DATABASE Statement

The `CREATE DATABASE` statement is used to create a new SQL database.

---

## Syntax

```sql
CREATE DATABASE databasename;
```

## Basic Example

The following SQL statement creates a database called testDB:

```sql
CREATE DATABASE testDB;
```

## Example 1: Create Database Only If Not Exists

Prevents an error if the database already exists.

```sql
CREATE DATABASE IF NOT EXISTS testDB;
```

## Example 2: Create Database with Character Set

Specify the character set for the database:

```sql
CREATE DATABASE testDB
CHARACTER SET utf8mb4;
```

## Example 3: Create Database with Character Set and Collation

Specify both character set and collation (rules for comparing text):

```sql
CREATE DATABASE testDB
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

## Example 4: Create Multiple Databases (Run separately)

```sql
CREATE DATABASE salesDB;
CREATE DATABASE hrDB;
CREATE DATABASE marketingDB;
```

