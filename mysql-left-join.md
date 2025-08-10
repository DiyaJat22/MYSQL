# What is LEFT JOIN in MySQL?

LEFT JOIN returns all rows from the left table (the first table in the join), and the matched rows from the right table (the second table).

If there is no match, the result will contain NULL for columns from the right table.

### Syntax:

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.common_column = table2.common_column;
```

# Example Tables

## employees

| id | name    | dept_id |
|----|---------|---------|
| 1  | Alice   | 1       |
| 2  | Bob     | 2       |
| 3  | Charlie | 3       |
| 4  | David   | NULL    |

## departments

| dept_id | dept_name |
|---------|-----------|
| 1       | HR        |
| 2       | IT        |
| 3       | Marketing |
| 4       | Finance   |


# Examples of LEFT JOIN

## Example 1: Get all employees and their department names (including employees with no department).

```sql
SELECT employees.name, departments.dept_name
FROM employees
LEFT JOIN departments
ON employees.dept_id = departments.dept_id;
```

Result:

| name    | dept_name  |
|---------|------------|
| Alice   | HR         |
| Bob     | IT         |
| Charlie | Marketing  |
| David   | NULL       |

---

## Example 2: List all departments and employees in them (including departments with no employees).

```sql
SELECT departments.dept_name, employees.name
FROM departments
LEFT JOIN employees
ON departments.dept_id = employees.dept_id;
```

Result:

| dept_name | name    |
|-----------|---------|
| HR        | Alice   |
| IT        | Bob     |
| Marketing | Charlie |
| Finance   | NULL    |

---

## Example 3: Get employees with their departments, but show ‘No Department’ where dept_id is NULL.

```sql
SELECT employees.name, 
       COALESCE(departments.dept_name, 'No Department') AS dept_name
FROM employees
LEFT JOIN departments
ON employees.dept_id = departments.dept_id;
```

---

## Example 4: Get all employees and departments, filtering to only show employees without departments.

```sql
SELECT employees.name
FROM employees
LEFT JOIN departments
ON employees.dept_id = departments.dept_id
WHERE departments.dept_id IS NULL;
```

Result:

| name  |
|-------|
| David |

---

## Example 5: Count employees per department, including departments with zero employees.

```sql
SELECT departments.dept_name, COUNT(employees.id) AS employee_count
FROM departments
LEFT JOIN employees
ON departments.dept_id = employees.dept_id
GROUP BY departments.dept_name;
```

Result:

| dept_name | employee_count |
|-----------|----------------|
| HR        | 1              |
| IT        | 1              |
| Marketing | 1              |
| Finance   | 0              |

---

