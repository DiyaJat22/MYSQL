# What is UNION in MySQL?

UNION combines the result sets of two or more SELECT statements into a single result set. It removes duplicate rows by default.

All SELECT statements must have the same number of columns.

Corresponding columns must have compatible data types.

To include duplicates, use UNION ALL.

## Syntax:

```sql
SELECT column1, column2, ...
FROM table1
UNION
SELECT column1, column2, ...
FROM table2;
```

# Example Tables

## table_a

| id | name  |
|----|-------|
| 1  | Alice |
| 2  | Bob   |

## table_b

| id | name    |
|----|---------|
| 2  | Bob     |
| 3  | Charlie |

---

# Examples of UNION

## Example 1: Combine names from both tables, removing duplicates

```sql
SELECT name FROM table_a
UNION
SELECT name FROM table_b;
```

Result:

| name    |
|---------|
| Alice   |
| Bob     |
| Charlie |

---

## Example 2: Combine names including duplicates (using UNION ALL)

```sql
SELECT name FROM table_a
UNION ALL
SELECT name FROM table_b;
```

Result:

| name    |
|---------|
| Alice   |
| Bob     |
| Bob     |
| Charlie |

---

## Example 3: Combine multiple columns (id and name)

```sql
SELECT id, name FROM table_a
UNION
SELECT id, name FROM table_b;
```

Result:

| id | name    |
|----|---------|
| 1  | Alice   |
| 2  | Bob     |
| 3  | Charlie |

---

## Example 4: Using UNION with conditions

Get all distinct names from both tables where id is less than 3.

```sql
SELECT name FROM table_a WHERE id < 3
UNION
SELECT name FROM table_b WHERE id < 3;
```

Result:

| name  |
|-------|
| Alice |
| Bob   |

---
