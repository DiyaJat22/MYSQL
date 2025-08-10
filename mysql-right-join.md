# What is RIGHT JOIN in MySQL?

RIGHT JOIN returns all rows from the right table (the second table), and the matched rows from the left table (the first table).

If there is no match, the result contains NULL for columns from the left table.

It’s basically the opposite of LEFT JOIN.

## Syntax:

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
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

---

# Examples of RIGHT JOIN

## Example 1: Get all departments and employees assigned to them (including departments with no employees)

```sql
SELECT employees.name, departments.dept_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id;
```

Result:

| name    | dept_name  |
|---------|------------|
| Alice   | HR         |
| Bob     | IT         |
| Charlie | Marketing  |
| NULL    | Finance    |

---

## Example 2: List departments with no employees

```sql
SELECT departments.dept_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id
WHERE employees.id IS NULL;
```

Result:

| dept_name |
|-----------|
| Finance   |

---

## Example 3: Show all departments and employee names, replace NULL employee names with 'No Employee'

```sql
SELECT departments.dept_name,
       COALESCE(employees.name, 'No Employee') AS employee_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id;
```

---

## Example 4: Count employees per department including departments with zero employees

```sql
SELECT departments.dept_name, COUNT(employees.id) AS employee_count
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id
GROUP BY departments.dept_name;
```

---

## Example 5: Get all employees and departments, show departments even if no employees, and sort by department name

```sql
SELECT employees.name, departments.dept_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id
ORDER BY departments.dept_name;
```

---

## Example 6: Find employees who belong to departments with dept_id greater than 2, include departments with no employees

```sql
SELECT employees.name, departments.dept_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id
WHERE departments.dept_id > 2;
```

---

## Example 7: Get department names and employee count but only for departments with zero or more than one employee

```sql
SELECT departments.dept_name, COUNT(employees.id) AS employee_count
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id
GROUP BY departments.dept_name
HAVING employee_count = 0 OR employee_count > 1;
```

---

## Example 8: Show departments and employees, but exclude employees with NULL names (if any)

```sql
SELECT departments.dept_name, employees.name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id
WHERE employees.name IS NOT NULL;
```

---

