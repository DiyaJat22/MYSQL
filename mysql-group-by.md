# What is GROUP BY in MySQL?

GROUP BY is used to group rows that have the same values in specified columns into summary rows, like aggregating data.
It's often used with aggregate functions such as COUNT(), SUM(), AVG(), MAX(), and MIN().

## Syntax:

```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1;
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

# Examples of GROUP BY

## Example 1: Count employees in each department

```sql
SELECT dept_id, COUNT(*) AS employee_count
FROM employees
GROUP BY dept_id;
```

Result:

| dept_id | employee_count |
|---------|----------------|
| 1       | 2              |
| 2       | 2              |
| 3       | 1              |

---

## Example 2: Calculate average salary per department

```sql
SELECT dept_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY dept_id;
```

Result:

| dept_id | avg_salary |
|---------|------------|
| 1       | 52500      |
| 2       | 62500      |
| 3       | 70000      |

---

## Example 3: Get the maximum salary in each department

```sql
SELECT dept_id, MAX(salary) AS max_salary
FROM employees
GROUP BY dept_id;
```

---

## Example 4: Group employees by department and list the total salary per department

```sql
SELECT dept_id, SUM(salary) AS total_salary
FROM employees
GROUP BY dept_id;
```

---

## Example 5: Group employees by department having more than 1 employee

```sql
SELECT dept_id, COUNT(*) AS employee_count
FROM employees
GROUP BY dept_id
HAVING employee_count > 1;
```

---


