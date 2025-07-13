# What is SQL?

**SQL** (Structured Query Language) is the standard language for dealing with **Relational Databases**.

SQL is used to:
- Insert data
- Search data
- Update data
- Delete database records

---

## How to Use SQL

The following SQL statement selects all the records in the `Customers` table:

```sql
SELECT * FROM Customers;
```

---

## Keep in Mind That...

- SQL keywords are **not case-sensitive**: `select` is the same as `SELECT`.
- In this tutorial, we will use **upper-case** for all SQL keywords.

---

## Semicolon After SQL Statements?

- Some database systems **require a semicolon (`;`)** at the end of each SQL statement.
- Semicolons are the **standard way to separate** SQL statements when executing **multiple statements** in the same call to the server.
- We will use semicolons at the end of each SQL statement.

---

## Some of the Most Important SQL Commands

| SQL Command     | Description                                |
|-----------------|--------------------------------------------|
| `SELECT`        | Extracts data from a database              |
| `UPDATE`        | Updates data in a database                 |
| `DELETE`        | Deletes data from a database               |
| `INSERT INTO`   | Inserts new data into a database           |
| `CREATE DATABASE` | Creates a new database                  |
| `ALTER DATABASE`  | Modifies an existing database           |
| `CREATE TABLE`    | Creates a new table                     |
| `ALTER TABLE`     | Modifies an existing table              |
| `DROP TABLE`      | Deletes a table                         |
| `CREATE INDEX`    | Creates an index (search key)           |
| `DROP INDEX`      | Deletes an index                        |

---

📌 *SQL is a powerful tool used in all modern RDBMS systems like MySQL, PostgreSQL, SQL Server, and Oracle.*
