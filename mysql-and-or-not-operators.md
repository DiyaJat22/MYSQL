# MySQL AND, OR, and NOT Operators

## 1. AND Operator

The AND operator is used to filter records that satisfy all the specified conditions.

Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2;
```

Example:

```sql
SELECT * FROM employees
WHERE department = 'Sales' AND salary > 50000;
```

✅ This will return employees only in the Sales department and with a salary greater than 50,000.

---

## 2. OR Operator

The OR operator is used to filter records that satisfy at least one of the specified conditions.

Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2;
```

Example:

```sql
SELECT * FROM employees
WHERE department = 'Sales' OR department = 'Marketing';
```

✅ This will return employees either in Sales or Marketing.

---

## 3. NOT Operator

The NOT operator is used to exclude records that match a condition.

Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

Example:

```sql
SELECT * FROM employees
WHERE NOT department = 'Sales';
```

✅ This will return employees not in the Sales department.

---

4. Combined Example (AND, OR, NOT)

You can combine these operators to form complex queries.

Example:

```sql
SELECT * FROM employees
WHERE (department = 'Sales' OR department = 'Marketing')
AND NOT salary < 40000;
```

Example 1:

```sql
-- Customers from India AND (age above 25 OR membership = 'Gold')
SELECT name, country, age, membership
FROM customers
WHERE country = 'India' AND (age > 25 OR membership = 'Gold');
```

Example 2:

```sql
-- Customers NOT from USA AND age below 30
SELECT name, country, age
FROM customers
WHERE NOT country = 'USA' AND age < 30;
```

Example 3:

```sql
-- Employees in department 'IT' OR 'HR', but NOT with salary > 60000
SELECT name, department, salary
FROM employees
WHERE (department = 'IT' OR department = 'HR') AND NOT salary > 60000;
```

## 1. AND Operator

The AND operator returns records where all conditions are true.

```sql
-- Example: Find employees in the 'IT' department with salary > 50000
SELECT * 
FROM employees
WHERE department = 'IT' AND salary > 50000;

-- Example: Products in stock AND price less than 100
SELECT * 
FROM products
WHERE stock_quantity > 0 AND price < 100;
```

## 2. OR Operator

The OR operator returns records where at least one condition is true.

```sql
-- Example: Customers from 'London' OR 'Paris'
SELECT * 
FROM customers
WHERE city = 'London' OR city = 'Paris';

-- Example: Orders placed before 2024 OR with amount over 1000
SELECT * 
FROM orders
WHERE order_date < '2024-01-01' OR total_amount > 1000;
```

## 3. NOT Operator

The NOT operator reverses the result of a condition.

```sql
-- Example: Customers NOT from 'USA'
SELECT * 
FROM customers
WHERE NOT country = 'USA';

-- Example: Products NOT in stock
SELECT * 
FROM products
WHERE NOT stock_quantity > 0;
```

## 4. Combining AND, OR, and NOT

Use parentheses () to control logical precedence.

```sql
-- Example: Employees in 'Sales' with salary > 40000 OR in 'IT'
SELECT * 
FROM employees
WHERE (department = 'Sales' AND salary > 40000) OR department = 'IT';

-- Example: Customers from 'Germany' OR 'France', but NOT in city 'Berlin'
SELECT * 
FROM customers
WHERE (country = 'Germany' OR country = 'France')
  AND NOT city = 'Berlin';

-- Example: Orders from 'USA' AND NOT shipped
SELECT * 
FROM orders
WHERE country = 'USA' AND NOT status = 'Shipped';
```

## 5. AND + OR Practical Examples

```sql
-- Products in category 'Electronics' priced between 100 and 500, OR category 'Books'
SELECT * 
FROM products
WHERE (category = 'Electronics' AND price BETWEEN 100 AND 500)
   OR category = 'Books';

-- Employees hired after 2020 from 'HR' OR 'Finance', but salary < 70000
SELECT * 
FROM employees
WHERE (department IN ('HR', 'Finance') AND hire_date > '2020-01-01')
  AND salary < 70000;
```

## 6. Complex Example with NOT
   
```sql
-- Customers NOT from 'USA' OR 'Canada', AND with orders > 5
SELECT * 
FROM customers
WHERE NOT country IN ('USA', 'Canada')
  AND total_orders > 5;

-- Orders NOT from 2024 AND status = 'Delivered' OR 'Completed'
SELECT * 
FROM orders
WHERE NOT YEAR(order_date) = 2024
  AND (status = 'Delivered' OR status = 'Completed');
```


