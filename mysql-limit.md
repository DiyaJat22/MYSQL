
# What is LIMIT in MySQL?

The LIMIT clause in MySQL is used to restrict the number of rows returned by a SELECT query.
It is also used with OFFSET to skip rows before starting to return the results.

### Syntax:

```sql
SELECT column1, column2, ...
FROM table_name
[WHERE condition]
ORDER BY column_name
LIMIT [offset,] row_count;
```

  row_count → Number of rows you want.

  offset → Number of rows to skip before starting to return results.

### Example Table:

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    marks INT
);ql
```

```s
INSERT INTO students (id, name, marks) VALUES
(1, 'Amit', 85),
(2, 'Neha', 90),
(3, 'Ravi', 78),
(4, 'Priya', 92),
(5, 'Karan', 88),
(6, 'Sneha', 75),
(7, 'Vikram', 80);
```

---

## Example 1 — Basic LIMIT

```sql
SELECT * FROM students LIMIT 3;
```

### Description: 

    Fetches only the first 3 rows from the table.

    Output → Amit, Neha, Ravi. 

---

## Example 2 — LIMIT with OFFSET

```sql
SELECT * FROM students LIMIT 2, 3;
```

### Description:

    Skips first 2 rows (Amit, Neha) and returns next 3 rows → Ravi, Priya, Karan.

---    

## Example 3 — LIMIT with ORDER BY

```sql
SELECT * FROM students ORDER BY marks DESC LIMIT 5;
```

### Description:

    Orders students by marks (highest first) and returns the top 5 scorers.

---

## Example 4 — Getting the Second Highest Marks

```sql
SELECT * FROM students ORDER BY marks DESC LIMIT 1, 1;
```

### Description:

    LIMIT 1, 1 → Skip 1 row (highest marks) and get next 1 row (second highest marks).

---

## Example 5 — Pagination

```sql
-- Page 1 (records 1–3)
SELECT * FROM students LIMIT 0, 3;

-- Page 2 (records 4–6)
SELECT * FROM students LIMIT 3, 3;

-- Page 3 (records 7–9)
SELECT * FROM students LIMIT 6, 3;
```

### Description:

    Useful in applications when displaying results in pages (like Google search results).

---
## 1. Basic LIMIT

Get the first 3 rows from the students table:

```sql
SELECT * 
FROM students 
LIMIT 3;
```

### Description:
   LIMIT 3 means only the first 3 rows will be returned.

---

## 2. LIMIT with OFFSET

Get rows 6 to 10:

```sql
SELECT * 
FROM students 
LIMIT 5 OFFSET 5;
```

### Description:

    OFFSET 5 skips the first 5 rows.

    LIMIT 5 then takes the next 5 rows.

    Useful for pagination.

---

## 3. LIMIT with ORDER BY

Get the top 5 highest scores:

```sql
SELECT name, score 
FROM students 
ORDER BY score DESC 
LIMIT 5;
```

### Description:

    Sorts by score from highest to lowest.

    Picks only the top 5 results.

---

## 4. LIMIT in a Subquery

Get the second highest score:

```sql
SELECT name, score
FROM students
ORDER BY score DESC
LIMIT 1 OFFSET 1;
```

### Description:

    LIMIT 1 OFFSET 1 skips the highest score and shows the next one.

---

## 5. LIMIT for Random Records

Pick 3 random students:

```sql
SELECT * 
FROM students 
ORDER BY RAND() 
LIMIT 3;
```

### Description:

    ORDER BY RAND() shuffles the rows randomly.

    LIMIT 3 gives 3 random results.

---    

## 6. LIMIT with JOIN

Get the top 5 students by score with their class name:

```sql
SELECT s.name, s.score, c.class_name
FROM students s
JOIN classes c ON s.class_id = c.id
ORDER BY s.score DESC
LIMIT 5;
```

### Description:

    Works with joins too — you can sort and limit joined results.

---

## 7. LIMIT with GROUP BY (Top N in Groups)

Get top 2 students from each class (using MySQL 8+ with ROW_NUMBER):

```sql
WITH ranked AS (
    SELECT 
        name, 
        class_id, 
        score,
        ROW_NUMBER() OVER (PARTITION BY class_id ORDER BY score DESC) AS rn
    FROM students
)
SELECT * 
FROM ranked
WHERE rn <= 2;
```

### Description:

    Gives only the first 2 students in each class by score.

 ---   




