# 1. COUNT()

Purpose: Counts the number of rows (or non-NULL values) in a column.

### Syntax:

```sql
SELECT COUNT(column_name) FROM table_name;
```

### Example:

We have a table students:

| id  | name  | marks |
|-----|-------|-------|
| 1   | Aisha | 85    |
| 2   | Rohan | 92    |
| 3   | Priya | 78    |
| 4   | Rahul | NULL  |


### Query:

```sql
SELECT COUNT(marks) AS total_students_with_marks
FROM students;
```

### Result:

```
total_students_with_marks
3
```

💡 Here it counted only non-NULL marks.

---

# 2. AVG()

Purpose: Returns the average value of a numeric column.

### Syntax:

```sql
SELECT AVG(column_name) FROM table_name;
```

### Example:

```sql
SELECT AVG(marks) AS average_marks
FROM students;
```

### Result:

```sql
average_marks
85
```


📌 It calculated (85 + 92 + 78) / 3 = 85.

---

# 3. SUM()

Purpose: Returns the sum of all values in a numeric column.

### Syntax:

```sql
SELECT SUM(column_name) FROM table_name;
```

### Example:

```sql
SELECT SUM(marks) AS total_marks
FROM students;
```

### Result:

```sql
total_marks
255
```

📌 It added up (85 + 92 + 78).

---

## Example with all 3 together

```sql
SELECT 
    COUNT(marks) AS student_count,
    AVG(marks) AS average_marks,
    SUM(marks) AS total_marks
FROM students;
```

### Result:

| student_count | average_marks | total_marks |
|---------------|---------------|-------------|
| 3             | 85            | 255         |

---

## 1️⃣ COUNT() Examples

```sql
-- Count total orders
SELECT COUNT(*) AS total_orders FROM orders;

-- Count distinct customers
SELECT COUNT(DISTINCT customer_id) AS unique_customers FROM orders;

-- Count how many laptops sold
SELECT COUNT(*) AS laptop_orders
FROM orders
WHERE product = 'Laptop';
```

---

## 2️⃣ AVG() Examples

```sql
-- Average price of all items
SELECT AVG(price_per_item) AS avg_price FROM orders;

-- Average quantity per order
SELECT AVG(quantity) AS avg_quantity FROM orders;

-- Average laptop price
SELECT AVG(price_per_item) AS avg_laptop_price
FROM orders
WHERE product = 'Laptop';
```

---

## 3️⃣ SUM() Examples

```sql
-- Total quantity of all products sold
SELECT SUM(quantity) AS total_quantity FROM orders;

-- Total revenue (quantity × price)
SELECT SUM(quantity * price_per_item) AS total_revenue FROM orders;

-- Total revenue from laptops only
SELECT SUM(quantity * price_per_item) AS laptop_revenue
FROM orders
WHERE product = 'Laptop';
```

---

### ✅ Extra Tip:

You can combine these functions for more detailed reports:

```sql
-- Summary report of orders
SELECT 
    COUNT(*) AS total_orders,
    SUM(quantity) AS total_quantity,
    AVG(price_per_item) AS average_price,
    SUM(quantity * price_per_item) AS total_revenue
FROM orders;
```

---



