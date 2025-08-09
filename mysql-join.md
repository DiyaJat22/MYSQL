# MySQL JOIN 

JOIN is a powerful SQL operation used to combine rows from two or more tables based on a related column between them. It allows you to retrieve related data stored in multiple tables in a single query.

## Why use JOIN?

   Data in relational databases is normalized and split across multiple tables.

   JOIN helps combine this related data for meaningful results.

   For example, employee details might be in one table and department info in another; JOIN combines them.

   ---

## 1. INNER JOIN

  Returns rows that have matching values in both tables.

  If there is no match, the row is not included.

### Example:

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments ON employees.dept_id = departments.dept_id;
```

---

## 2. LEFT JOIN (LEFT OUTER JOIN)

   Returns all rows from the left table.

   If there is no matching row in the right table, shows NULL for right table columns.

### Example:

```sql
SELECT employees.name, departments.dept_name
FROM employees
LEFT JOIN departments ON employees.dept_id = departments.dept_id;
```

---

## 3. RIGHT JOIN (RIGHT OUTER JOIN)

   Returns all rows from the right table.

   If there is no matching row in the left table, shows NULL for left table columns.

### Example:

```sql
SELECT employees.name, departments.dept_name
FROM employees
RIGHT JOIN departments ON employees.dept_id = departments.dept_id;
```

---

## 4. FULL JOIN (FULL OUTER JOIN)

  Returns rows when there is a match in either table.

  Shows NULLs for unmatched rows from both sides.

  Note: MySQL doesn’t support FULL JOIN directly, but it can be emulated using UNION of LEFT JOIN and RIGHT JOIN.

  ---

## 5. CROSS JOIN

  Returns Cartesian product (all possible combinations) of rows from both tables.

### Example:

```sql
SELECT employees.name, departments.dept_name
FROM employees
CROSS JOIN departments;
```

---

