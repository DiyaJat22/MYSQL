# What is the HAVING Clause in MySQL?

  The HAVING clause is used to filter groups created by the GROUP BY clause.

  It works like a WHERE clause but filters on aggregated data.

  You use HAVING to specify conditions on aggregated columns (e.g., count, sum, avg).

## Syntax:

```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1
HAVING condition;
```

# Example Table

## employees

| id | name    | dept_id | salary |
|----|---------|---------|--------|
| 1  | Alice   | 1       | 50000  |
| 2  | Bob     | 2       | 60000  |
| 3  | Charlie | 1       | 55000  |
| 4  | David   | 3       | 70000  |
| 5  | Eva     | 2       | 65000  |

---

# Examples of HAVING Clause

## Example 1: Departments with more than 1 employee

```sql
SELECT dept_id, COUNT(*) AS employee_count
FROM employees
GROUP BY dept_id
HAVING employee_count > 1;
```

---

## Example 2: Departments where average salary is greater than 60000

```sql
SELECT dept_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY dept_id
HAVING avg_salary > 60000;
```

---

## Example 3: Departments with total salary less than or equal to 120000

```sql
SELECT dept_id, SUM(salary) AS total_salary
FROM employees
GROUP BY dept_id
HAVING total_salary <= 120000;
```

---

## Example 4: Using HAVING with multiple conditions

```sql
SELECT dept_id, COUNT(*) AS employee_count, AVG(salary) AS avg_salary
FROM employees
GROUP BY dept_id
HAVING employee_count > 1 AND avg_salary > 60000;
```

---

