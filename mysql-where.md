

# MySQL `WHERE` Clause

The `WHERE` clause in MySQL is used to filter records based on specific conditions. It allows you to retrieve only the rows that meet the specified criteria.

---

## 📌 Syntax

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

- **`column1, column2, ...`**: The columns you want to retrieve.
- **`table_name`**: The table from which you want to retrieve data.
- **`condition`**: The condition to filter the rows.

---

## 📌 Example Database

Assume we have a table named `employees`:

| id | name    | department | salary |
|----|---------|------------|--------|
| 1  | Alice   | HR         | 40000  |
| 2  | Bob     | IT         | 55000  |
| 3  | Charlie | Finance    | 60000  |
| 4  | David   | IT         | 45000  |
| 5  | Eva     | HR         | 50000  |

---

## 📌 Basic Example

```sql
SELECT * FROM employees
WHERE department = 'IT';
```

**Result:**

| id | name | department | salary |
|----|------|------------|--------|
| 2  | Bob  | IT         | 55000  |
| 4  | David| IT         | 45000  |

---

## 📌 Using Comparison Operators

| Operator | Description                      | Example                          |
|----------|----------------------------------|-----------------------------------|
| =        | Equal to                         | `salary = 50000`                 |
| <> or != | Not equal to                     | `department <> 'HR'`              |
| >        | Greater than                     | `salary > 40000`                  |
| <        | Less than                        | `salary < 50000`                  |
| >=       | Greater than or equal to         | `salary >= 50000`                 |
| <=       | Less than or equal to            | `salary <= 45000`                 |
| BETWEEN  | Between a range (inclusive)      | `salary BETWEEN 45000 AND 55000`  |
| LIKE     | Pattern matching                 | `name LIKE 'A%'`                  |
| IN       | Matches values in a list         | `department IN ('IT', 'Finance')` |

---

## 📌 Using Logical Operators

- **AND** → Both conditions must be true  
- **OR** → At least one condition must be true  
- **NOT** → Negates a condition

**Example:**

```sql
SELECT * FROM employees
WHERE department = 'IT' AND salary > 50000;
```

**Result:**

| id | name | department | salary |
|----|------|------------|--------|
| 2  | Bob  | IT         | 55000  |

---

## 📌 Pattern Matching with `LIKE`

- `%` → Matches any number of characters
- `_` → Matches a single character

**Example:**

```sql
SELECT * FROM employees
WHERE name LIKE 'A%';
```

Matches any name starting with "A".

---

## 📌 Filtering with `IN`

```sql
SELECT * FROM employees
WHERE department IN ('HR', 'Finance');
```

**Result:**

| id | name    | department | salary |
|----|---------|------------|--------|
| 1  | Alice   | HR         | 40000  |
| 3  | Charlie | Finance    | 60000  |
| 5  | Eva     | HR         | 50000  |

---

## 📌 NULL Checks

- `IS NULL` → Matches NULL values
- `IS NOT NULL` → Matches non-NULL values

**Example:**

```sql
SELECT * FROM employees
WHERE salary IS NOT NULL;
```

---

## 📌 Best Practices

1. Always use proper indexes on columns used in `WHERE` for better performance.# SQL WHERE Clause with Examples

The `WHERE` clause in SQL is used to filter records that meet specific conditions.

## Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

## Examples

### 1. Equality (`=`)
```sql
SELECT * FROM Employees
WHERE Department = 'IT';
```
*Returns all employees in the IT department.*

### 2. Not Equal (`!=` or `<>`)
```sql
SELECT * FROM Employees
WHERE Department != 'HR';
```
*Returns all employees who are not in the HR department.*

### 3. Greater Than (`>`)
```sql
SELECT * FROM Employees
WHERE Salary > 50000;
```
*Returns all employees with a salary greater than 50,000.*

### 4. Less Than (`<`)
```sql
SELECT * FROM Employees
WHERE Age < 30;
```
*Returns all employees younger than 30.*

### 5. Greater Than or Equal To (`>=`)
```sql
SELECT * FROM Employees
WHERE Salary >= 60000;
```
*Returns employees with a salary of at least 60,000.*

### 6. Less Than or Equal To (`<=`)
```sql
SELECT * FROM Employees
WHERE Age <= 25;
```
*Returns employees aged 25 or younger.*

### 7. Between
```sql
SELECT * FROM Employees
WHERE Salary BETWEEN 40000 AND 60000;
```
*Returns employees with salaries between 40,000 and 60,000.*

### 8. IN
```sql
SELECT * FROM Employees
WHERE Department IN ('IT', 'Finance');
```
*Returns employees in either IT or Finance.*

### 9. LIKE (Pattern Matching)
```sql
SELECT * FROM Employees
WHERE Name LIKE 'A%';
```
*Returns employees whose names start with 'A'.*

### 10. IS NULL
```sql
SELECT * FROM Employees
WHERE Manager_ID IS NULL;
```
*Returns employees who do not have a manager assigned.*

---
**Tip:** Always test your `WHERE` clause with a small dataset before applying it to large tables to avoid performance issues.
2. Avoid using `SELECT *` in production; specify only required columns.
3. Be cautious with `OR` conditions, as they can reduce performance.
4. Use prepared statements to prevent SQL injection.

---

✅ **Conclusion:**  
The `WHERE` clause is essential for filtering rows in SQL queries. By combining it with operators and logical conditions, you can extract exactly the data you need.

