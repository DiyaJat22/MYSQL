# What is MySQL Alias?

An alias in MySQL is a temporary name given to a table or a column in a query. It makes the result set easier to read or the query easier to write, especially when using complex expressions or joins.

  Column alias: Renames a column in the output.

  Table alias: Renames a table temporarily for the duration of the query.

### Syntax

  Column alias:

```sql
SELECT column_name AS alias_name FROM table_name;
```

  Table alias:

```sql
SELECT t.column_name FROM table_name AS t;
```

Note: The AS keyword is optional; you can also write aliases without AS.

Simple Examples of MySQL Alias

| id | name  | age | salary |
|----|-------|-----|--------|
| 1  | Alice | 25  | 50000  |
| 2  | Bob   | 30  | 70000  |

---

## Example 1: Column alias to rename a column in output

```sql
SELECT name AS employee_name, salary AS monthly_salary FROM employees;
```

Output columns will be employee_name and monthly_salary.

---

## Example 2: Table alias for a shorter table name

```sql
SELECT e.name, e.salary FROM employees AS e WHERE e.age > 25;
```

Here, employees is aliased as e.

---

## Example 3: Alias without AS keyword

```sql
SELECT name employee_name, salary monthly_salary FROM employees;
```

Works the same as example 1.

---

## Example 4: Alias with expressions

```sql
SELECT name, salary * 12 AS yearly_salary FROM employees;
```
Calculates yearly salary and names the column yearly_salary.

---

## Example 5: Using table aliases in JOINs

Assuming another table departments:

| dept_id | dept_name |
|---------|-----------|
| 1       | HR        |
| 2       | IT        |

And employees has dept_id column:

```sql
SELECT e.name, d.dept_name 
FROM employees AS e
JOIN departments AS d ON e.dept_id = d.dept_id;
```

---

## More Advanced Examples

## Example 6: Multiple table aliases with complex joins

```sql
SELECT e.name AS employee, m.name AS manager
FROM employees AS e
LEFT JOIN employees AS m ON e.manager_id = m.id;
```

Here, the table employees is aliased twice as e and m for employee and manager.

---

## Example 7: Alias with subquery
l
```sq
SELECT avg_salary.department, avg_salary.avg_sal
FROM (
  SELECT dept_id AS department, AVG(salary) AS avg_sal
  FROM employees
  GROUP BY dept_id
) AS avg_salary;
```

---


