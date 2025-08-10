# What is UNION ALL in MySQL?

UNION ALL combines the results of two or more SELECT statements including duplicates.
Unlike UNION, it does not remove duplicate rows.

## Key Points:

   The number of columns and their data types must be the same in all SELECT statements.

   It’s faster than UNION because it skips the duplicate removal step.

## Syntax:

```sql
SELECT columns FROM table1
UNION ALL
SELECT columns FROM table2;
```

Example Tables

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

# Examples of UNION ALL

## Example 1: Combine names from both tables including duplicates

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

## Example 2: Combine id and name from both tables including duplicates

```sql
SELECT id, name FROM table_a
UNION ALL
SELECT id, name FROM table_b;
```

---

## Example 3: Using UNION ALL with additional source column

```sql
SELECT name, 'table_a' AS source FROM table_a
UNION ALL
SELECT name, 'table_b' AS source FROM table_b;
```

Result:

| name    | source  |
|---------|---------|
| Alice   | table_a |
| Bob     | table_a |
| Bob     | table_b |
| Charlie | table_b |

---

## Example 4: Using UNION ALL with ORDER BY

```sql
SELECT name FROM table_a
UNION ALL
SELECT name FROM table_b
ORDER BY name;
```

---


