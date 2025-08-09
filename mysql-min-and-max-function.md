# 1. MIN() Function

   Purpose: Returns the smallest value from the selected column.

### Syntax:
  
```sql
SELECT MIN(column_name) FROM table_name;
```

 Example:

```sql
SELECT MIN(salary) AS lowest_salary
FROM employees;
```

Output: Shows the lowest salary in the employees table.

---

# 2. MAX() Function

  Purpose: Returns the largest value from the selected column.

### Syntax:

```sql
SELECT MAX(column_name) FROM table_name;
```

Example:

```sql
SELECT MAX(salary) AS highest_salary
FROM employees;
```

Output: Shows the highest salary in the employees table.

---

### Using MIN() and MAX() Together

```sql
SELECT 
    MIN(salary) AS lowest_salary,
    MAX(salary) AS highest_salary
FROM employees;
```

Output: Returns both smallest and largest salary in one query.

---

### With GROUP BY

You can use them with GROUP BY to get min/max values for each group.

```sql
SELECT department, 
       MIN(salary) AS min_salary,
       MAX(salary) AS max_salary
FROM employees
GROUP BY department;
```

Output: Smallest and largest salary for each department.

---


## 1. Syntax

```sql
-- Find the smallest value
SELECT MIN(column_name) FROM table_name;

-- Find the largest value
SELECT MAX(column_name) FROM table_name;
```

---

## 2. Examples

## Example 1 – Find the lowest and highest salary

```sql
SELECT MIN(salary) AS lowest_salary, MAX(salary) AS highest_salary
FROM employees;
```

### Description:

    MIN(salary) returns the smallest salary in the employees table.

    MAX(salary) returns the largest salary.

---    

##  Example 2 – Find the oldest and youngest employee

```sql
SELECT MIN(birth_date) AS oldest_birth, MAX(birth_date) AS youngest_birth
FROM employees;
```

### Description:

    Older employees have earlier birth dates (smaller values).

    Younger employees have later birth dates (larger values).

---    

## Example 3 – MIN & MAX with WHERE

```sql
SELECT MIN(price) AS min_price, MAX(price) AS max_price
FROM products
WHERE category = 'Electronics';
```

### Description:

    Filters only the Electronics category, then finds the min and max prices.

---

## Example 4 – MIN & MAX with GROUP BY

```sql
SELECT department, MIN(salary) AS lowest_salary, MAX(salary) AS highest_salary
FROM employees
GROUP BY department;
```

### Description:

    Shows the lowest and highest salary for each department.

---

## Example 5 – MIN & MAX on text values

```sql
SELECT MIN(name) AS alphabetically_first, MAX(name) AS alphabetically_last
FROM students;
```

### Description:

    On strings, MIN() returns the alphabetically first value, and MAX() returns the last.

---    
    
