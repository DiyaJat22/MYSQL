# MySQL Functions - Description and Examples

MySQL provides a rich set of built-in functions to perform operations on data, including string manipulation, numeric calculations, date/time processing, and more.

---

## Categories of MySQL Functions

| Category        | Description                             | Examples                             |
|-----------------|-----------------------------------------|------------------------------------|
| String Functions | Manipulate string data                  | CONCAT(), SUBSTRING(), LENGTH(), UPPER(), LOWER() |
| Numeric Functions| Perform calculations on numeric values | ROUND(), CEIL(), FLOOR(), ABS(), POWER() |
| Date and Time Functions | Work with date and time values       | NOW(), CURDATE(), DATE_ADD(), DATEDIFF(), DATE_FORMAT() |
| Aggregate Functions | Calculate summary values from sets    | COUNT(), SUM(), AVG(), MAX(), MIN() |
| Control Flow Functions | Conditional logic and flow control     | IF(), CASE, COALESCE(), NULLIF()   |

---

## Common MySQL Functions with Examples

### String Functions

| Function             | Description                             | Example                              |
|----------------------|---------------------------------------|------------------------------------|
| `CONCAT(str1, str2)` | Concatenates two or more strings      | `SELECT CONCAT('Hello', ' ', 'World');` |
| `SUBSTRING(str, pos, len)` | Extracts substring from a string       | `SELECT SUBSTRING('MySQL Tutorial', 1, 5);` |
| `LENGTH(str)`        | Returns length of string in bytes     | `SELECT LENGTH('Hello');`           |
| `UPPER(str)`         | Converts string to uppercase          | `SELECT UPPER('hello');`            |
| `LOWER(str)`         | Converts string to lowercase          | `SELECT LOWER('HELLO');`            |

---

### Numeric Functions

| Function          | Description                            | Example                          |
|-------------------|--------------------------------------|---------------------------------|
| `ROUND(number, decimals)` | Rounds a number to specified decimals | `SELECT ROUND(3.14159, 2);`     |
| `CEIL(number)`    | Returns the smallest integer ≥ number | `SELECT CEIL(4.2);`              |
| `FLOOR(number)`   | Returns the largest integer ≤ number  | `SELECT FLOOR(4.8);`             |
| `ABS(number)`     | Returns the absolute value            | `SELECT ABS(-10);`               |
| `POWER(base, exponent)` | Returns base raised to exponent    | `SELECT POWER(2, 3);`            |

---

### Date and Time Functions

| Function           | Description                         | Example                                |
|--------------------|-----------------------------------|--------------------------------------|
| `NOW()`            | Returns current date and time     | `SELECT NOW();`                       |
| `CURDATE()`        | Returns current date              | `SELECT CURDATE();`                   |
| `DATE_ADD(date, INTERVAL expr unit)` | Adds interval to date                | `SELECT DATE_ADD('2025-08-10', INTERVAL 5 DAY);` |
| `DATEDIFF(date1, date2)` | Returns difference in days         | `SELECT DATEDIFF('2025-09-15', '2025-08-10');` |
| `DATE_FORMAT(date, format)` | Formats date according to format string | `SELECT DATE_FORMAT(NOW(), '%M %d, %Y');` |

---

### Aggregate Functions

| Function      | Description                             | Example                          |
|---------------|---------------------------------------|---------------------------------|
| `COUNT(column)` | Counts rows with non-null values      | `SELECT COUNT(id) FROM employees;` |
| `SUM(column)`   | Sums numeric values                   | `SELECT SUM(salary) FROM employees;` |
| `AVG(column)`   | Calculates average value              | `SELECT AVG(age) FROM employees;` |
| `MAX(column)`   | Finds maximum value                   | `SELECT MAX(salary) FROM employees;` |
| `MIN(column)`   | Finds minimum value                   | `SELECT MIN(age) FROM employees;` |

---

### Control Flow Functions

| Function      | Description                             | Example                          |
|---------------|---------------------------------------|---------------------------------|
| `IF(condition, true_val, false_val)` | Returns true_val if condition is true, else false_val | `SELECT IF(salary > 50000, 'High', 'Low') FROM employees;` |
| `CASE`        | Performs conditional logic             | See SQL CASE syntax              |
| `COALESCE(val1, val2, ...)` | Returns first non-null value         | `SELECT COALESCE(NULL, 'default', 'other');` |
| `NULLIF(val1, val2)` | Returns NULL if val1 = val2, else val1 | `SELECT NULLIF(10, 10);`        |

---

## Notes

- Functions can be nested for complex operations.
- Some functions behave differently with `NULL` values.
- Use aggregate functions with `GROUP BY` clause for grouped summaries.

---
