# What is MySQL BETWEEN?

The BETWEEN operator in MySQL is used to filter the result set within a certain range. It selects values within a given range, inclusive of the boundary values.

### Syntax:

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

    It returns rows where the column value is greater than or equal to value1 and less than or equal to value2.

    The range values can be numbers, dates, or text.

---

## Example 1: Find employees aged between 25 and 35

```sql
SELECT * FROM employees WHERE age BETWEEN 25 AND 35;
````

Result: Returns Alice, Bob, Cha# Employees Table

| id | name    | age | salary | joining_date |
|----|---------|-----|--------|--------------|
| 1  | Alice   | 25  | 50000  | 2020-01-15   |
| 2  | Bob     | 30  | 70000  | 2018-07-23   |
| 3  | Charlie | 35  | 60000  | 2019-03-10   |
| 4  | Diana   | 28  | 45000  | 2021-06-01   |
| 5  | Evan    | 40  | 80000  | 2017-12-05   |

---

# 5 Examples of MySQL BETWEEN

## Example 1: Find employees aged between 25 and 35

```sql
SELECT * FROM employees WHERE age BETWEEN 25 AND 35;
```

Result: Returns Alice, Bob, Charlie, and Diana (ages 25, 30, 35, and 28).

---

## Example 2: Find employees with salary between 50000 and 70000

```sql
SELECT * FROM employees WHERE salary BETWEEN 50000 AND 70000;
```

Result: Returns Alice, Bob, and Charlie (salaries 50000, 70000, 60000)

---

## Example 3: Find employees who joined between '2018-01-01' and '2020-12-31'

```sql
SELECT * FROM employees WHERE joining_date BETWEEN '2018-01-01' AND '2020-12-31';
```

Result: Returns Alice, Bob, and Charlie

---

## Example 4: Find employees whose names are alphabetically between 'B' and 'D'

```sql
SELECT * FROM employees WHERE name BETWEEN 'B' AND 'D';
```

Result: Returns Bob, Charlie, and Diana

---

## Example 5: Using BETWEEN with NOT operator - Find employees not aged between 30 and 40

```sql
SELECT * FROM employees WHERE age NOT BETWEEN 30 AND 40;
```

Result: Returns Alice and Diana (ages 25 and 28)

---


