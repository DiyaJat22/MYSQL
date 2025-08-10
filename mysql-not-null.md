# MySQL NOT NULL Constraint

The `NOT NULL` constraint ensures that a column cannot have a `NULL` value. This means that when inserting or updating a record, a value **must** be provided for that column; it cannot be left empty.

---

## Purpose

- To enforce that a column always contains meaningful data.
- Prevents accidental omission of required information.
- Helps maintain data integrity by disallowing missing values.

---

## Usage Example

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT
);
```

In this example, the name column cannot be NULL. Every record must include a name.

# MySQL NOT NULL Constraint — Examples

---

## Example 1: Creating a Table with NOT NULL Columns

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    email VARCHAR(100)
);
```

  name and age columns cannot be NULL.

  email column can have NULL values.

## Example 2: Inserting Valid Data

```sql
INSERT INTO employees (id, name, age, email) 
VALUES (1, 'Alice', 30, 'alice@example.com');
```

  name and age columns cannot be NULL.

  email column can have NULL values.

## Example 2: Inserting Valid Data

```sql
INSERT INTO employees (id, name, age, email) 
VALUES (1, 'Alice', 30, 'alice@example.com');
```

This works because all NOT NULL columns have values.

## Example 3: Inserting NULL into NOT NULL Column (Error)

```sql
INSERT INTO employees (id, name, age) 
VALUES (2, NULL, 25);
```

This will cause an error because name is defined as NOT NULL but NULL is provided.

## Example 4: Altering a Table to Add NOT NULL Constraint

```sql
ALTER TABLE employees
MODIFY COLUMN email VARCHAR(100) NOT NULL;
```

This changes the email column to NOT NULL, meaning all future inserts must provide an email.

## Example 5: Inserting Data After Altering Column

```sql
INSERT INTO employees (id, name, age, email) 
VALUES (3, 'Bob', 28, 'bob@example.com');
```

Valid insert with all NOT NULL columns filled.

