# What is INNER JOIN in MySQL?

INNER JOIN is used to combine rows from two or more tables based on a related column between them. It returns only the rows where there is a match in both tables.

If a row in Table A has a matching row in Table B based on the join condition, it appears in the result.

If there is no match, that row is excluded.

### Syntax:

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

# MySQL INNER JOIN Examples

## Tables Used:

### employees

| id | name    | dept_id |
|----|---------|---------|
| 1  | Alice   | 1       |
| 2  | Bob     | 2       |
| 3  | Charlie | 3       |
| 4  | David   | NULL    |

### departments

| dept_id | dept_name |
|---------|-----------|
| 1       | HR        |
| 2       | IT        |
| 3       | Marketing |
| 4       | Finance   |

---

## Example 1: Employee names with their department names

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.dept_id;
```

Result:

| name    | dept_name  |
|---------|------------|
| Alice   | HR         |
| Bob     | IT         |
| Charlie | Marketing  |

   Note: David is excluded because his dept_id is NULL (no matching department).

---

## Example 2: Get all employees and their departments for department ID = 2.

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.dept_id
WHERE departments.dept_id = 2;
```

Result:

| name | dept_name |
|------|-----------|
| Bob  | IT        |

---

## Example 3: Join employees and departments but show only employees with names starting with 'A'.

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.dept_id
WHERE employees.name LIKE 'A%';
```

Result:

| name  | dept_name |
|-------|-----------|
| Alice | HR        |

---

## Example 4: Count the number of employees in each department (only departments with employees).

```sql
SELECT departments.dept_name, COUNT(employees.id) AS employee_count
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.dept_id
GROUP BY departments.dept_name;
```

Result:

| dept_name | employee_count |
|-----------|----------------|
| HR        | 1              |
| IT        | 1              |
| Marketing | 1              |

---

## Example 5: Select employees with their department details but only for departments with dept_id less than 3.

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.dept_id
WHERE departments.dept_id < 3;
```

Result:

| name  | dept_name |
|-------|-----------|
| Alice | HR        |
| Bob   | IT        |

---
