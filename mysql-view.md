# MySQL CREATE VIEW - Examples and Description

A **View** in MySQL is a virtual table based on the result-set of an SQL statement. It behaves like a table but does not store data itself. Views simplify complex queries, enhance security, and present data in a customized way.

---

## Syntax

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

# Examples

## Example 1: Basic View

Create a view to show employees with a salary greater than 50000:

```sql
CREATE VIEW high_salary_employees AS
SELECT id, name, salary
FROM employees
WHERE salary > 50000;
```

  Query the view:

```sql
SELECT * FROM high_salary_employees;
```

## Example 2: View with JOIN

Create a view showing employees along with their department names:

```sql
CREATE VIEW employee_department AS
SELECT e.id, e.name, d.dept_name
FROM employees e
JOIN departments d ON e.dept_id = d.dept_id;
```

## Example 3: View with Aggregation

Create a view showing the total salary paid per department:

```sql
CREATE VIEW total_salary_per_dept AS
SELECT dept_id, SUM(salary) AS total_salary
FROM employees
GROUP BY dept_id;
```

## Example 4: Updating a View

If you need to change a view definition, use:

```sql
CREATE OR REPLACE VIEW view_name AS
SELECT ...
```

### Example:

```sql
CREATE OR REPLACE VIEW high_salary_employees AS
SELECT id, name, salary
FROM employees
WHERE salary > 60000;
```

## Example 5: Dropping a View

To remove a view:

```sql
DROP VIEW view_name;
```

### Example:

```sql
DROP VIEW employee_department;
```

