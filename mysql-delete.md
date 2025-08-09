# MySQL DELETE Statement

The DELETE statement in MySQL is used to remove one or more rows from a table.
It permanently deletes data unless you have a backup or use transactions with ROLLBACK.

### Syntax

```sql
DELETE FROM table_name
WHERE condition;
```
 table_name → The name of the table from which you want to delete data.

  condition → Specifies which records should be deleted.
  
  If you omit the WHERE clause, all rows from the table will be deleted.

### Example

```sql
Create a Sample Table

CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    department VARCHAR(50),
    salary DECIMAL(10,2)
);

INSERT INTO employees (name, department, salary) VALUES
('Alice', 'HR', 50000.00),
('Bob', 'IT', 60000.00),
('Charlie', 'Finance', 55000.00);
```

### Delete a Specific Record

```sql
DELETE FROM employees
WHERE name = 'Bob';
``` 

This command deletes the row where the name column is "Bob".


Result after deletion:

```
 id	name	department	salary
 1	Alice	HR	50000.00
 3	Charlie	Finance	55000.00
```

```sql
Delete All Records

DELETE * FROM employees;
```

Explanation:

   Removes all rows from the employees table, but the table structure remains.

---

### Example 1 – Delete a Specific Row

```sql
DELETE FROM employees
WHERE employee_id = 5;
```

#### Explanation:
 This removes the row where employee_id is exactly 5.
 
---
 
### Example 2 – Delete Multiple Rows

```sql
DELETE FROM orders
WHERE order_date < '2024-01-01';
```

#### Explanation:
 Deletes all orders placed before January 1, 2024.

---
 
### Example 3 – Delete All Rows from a Table

```sql
DELETE * FROM customers;
```

#### Explanation:

 Removes all records from the customers table but keeps the table structure intact.
 (Use with caution!)

---
 
### Example 4 – Delete with Multiple Conditions

```sql
DELETE FROM products
WHERE category = 'Electronics' AND stock_quantity = 0;
```

#### Explanation:
 Deletes all electronics that are out of stock.

---

### Example 5 – Delete Using a Subquery

```sql
DELETE FROM students
WHERE student_id IN (
    SELECT student_id FROM results WHERE score < 40
);
```

#### Explanation:

 Deletes all students who scored less than 40 in the results table.

---

### Example 6 – Delete Top N Records (With LIMIT)

```sql
DELETE FROM logs
ORDER BY created_at ASC
LIMIT 10;
```

#### Explanation:

Deletes the 10 oldest records from the logs table.

---

### ⚠ Important Notes:

  Always use WHERE to prevent accidental deletion of all records.

  Use LIMIT if you want to delete a specific number of rows.

  You cannot delete from multiple tables directly with DELETE in MySQL unless using a JOIN.



