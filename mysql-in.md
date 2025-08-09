# MySQL IN Function Examples

## Example 1 — Basic use of IN with strings

```sql
SELECT name, department
FROM Employees
WHERE department IN ('HR', 'IT');
```

### Description:

Selects employees who work in either the HR or IT department.

---

## Example 2 — Using IN with numbers

```sql
SELECT name, id
FROM Employees
WHERE id IN (1, 3, 5);
```

### Description:

Selects employees whose IDs are 1, 3, or 5.

---

## Example 3 — Using NOT IN

```sql
SELECT name, department
FROM Employees
WHERE department NOT IN ('Finance', 'HR');
```

### Description:

Selects employees who do not belong to the Finance or HR departments.

---

## Example 4 — Using IN with a subquery

```sql
SELECT name, department
FROM Employees
WHERE department IN (
    SELECT department_name
    FROM Departments
    WHERE location = 'New York'
);
```

### Description:

Selects employees working in departments that are located in New York. The list of departments is fetched dynamically from another table.

---

## Example 5 — Using IN with NULL values

```sql
SELECT name, department
FROM Employees
WHERE department IN ('HR', NULL);
```

### Description:

Note: NULL in the IN list doesn't match NULL values in the column. To check for NULL, use IS NULL.

---

## Example 6 — Combining IN with other conditions

```sql
SELECT name, department, salary
FROM Employees
WHERE department IN ('IT', 'Finance') AND salary > 50000;
```

### Description:

Selects employees in IT or Finance departments who have a salary greater than 50,000.

---

## Example 7 — IN with empty list (not recommended)

```sql
SELECT name
FROM Employees
WHERE department IN ();
```

### Description:

This query will cause a syntax error because the list is empty. Always provide at least one value.

---

### Summary

  IN is a concise way to check if a value exists in a list.

  Use NOT IN to exclude values.

   Can be combined with other SQL clauses for complex filtering.

   Use IS NULL to check for NULLs instead of including NULL in IN.
