# What is CROSS JOIN in MySQL?

CROSS JOIN produces the Cartesian product of the two tables. This means it returns all possible combinations of rows from the first table joined with rows from the second table.

If Table A has m rows and Table B has n rows, the result will have m × n rows.

No join condition is needed.

## Syntax:

```sql
SELECT columns
FROM table1
CROSS JOIN table2;
```

## or simply:

```sql
SELECT columns
FROM table1, table2;
```

# Example Tables

## employees

| id | name  |
|----|-------|
| 1  | Alice |
| 2  | Bob   |

## departments

| dept_id | dept_name |
|---------|-----------|
| 1       | HR        |
| 2       | IT        |

---

# Examples of CROSS JOIN

## Example 1: Get all combinations of employees and departments.

```sql
SELECT employees.name, departments.dept_name
FROM employees
CROSS JOIN departments;
```

Result:

| name  | dept_name |
|-------|-----------|
| Alice | HR        |
| Alice | IT        |
| Bob   | HR        |
| Bob   | IT        |

---

## Example 2: Using comma-separated tables (equivalent to CROSS JOIN)

```sql
SELECT employees.name, departments.dept_name
FROM employees, departments;
```
---

## Example 3: Cross join with filtering (though filtering is less common with cross join)

Get all employee-department pairs where department name is 'HR':

```sql
SELECT employees.name, departments.dept_name
FROM employees
CROSS JOIN departments
WHERE departments.dept_name = 'HR';
```

---

## Example 4: Count total combinations of employees and departments.

```sql
SELECT COUNT(*) AS total_combinations
FROM employees
CROSS JOIN departments;
```

Result:

| total_combinations |
|--------------------|
| 4                  |

---
