# MySQL Dates - Examples and Description

MySQL provides several data types and functions to work with dates and times. Dates are stored in the format `'YYYY-MM-DD'`.

---

## Common Date Data Types in MySQL

| Data Type  | Description                            | Format                  |
|------------|------------------------------------|-------------------------|
| DATE       | Stores date only                    | 'YYYY-MM-DD'            |
| DATETIME   | Stores date and time               | 'YYYY-MM-DD HH:MM:SS'   |
| TIMESTAMP  | Stores date and time (with timezone handling) | 'YYYY-MM-DD HH:MM:SS'   |
| TIME       | Stores time only                   | 'HH:MM:SS'              |
| YEAR       | Stores year only                   | YYYY                    |

---

## Examples

### 1. Create Table with DATE column

```sql
CREATE TABLE events (
    event_id INT AUTO_INCREMENT PRIMARY KEY,
    event_name VARCHAR(100),
    event_date DATE
);
```

  event_date will store dates like '2025-08-10'.

## 2. Insert Date values

```sql
INSERT INTO events (event_name, event_date)
VALUES ('Conference', '2025-09-15'),
       ('Meeting', '2025-08-20');
```

## 3. Query with date comparison

```sql
SELECT * FROM events
WHERE event_date > '2025-08-31';
```

  Selects events after August 31, 2025.

## 4. Use CURDATE() function (current date)

```sql
SELECT * FROM events
WHERE event_date = CURDATE();
```

  Finds events happening today.

## 5. Format date output with DATE_FORMAT()

```sql
SELECT event_name, DATE_FORMAT(event_date, '%M %d, %Y') AS formatted_date
FROM events;
```

  Outputs date as, e.g., "September 15, 2025".


| Function         | Description                         | Example                                          |
|------------------|-----------------------------------|-------------------------------------------------|
| `NOW()`          | Returns current date and time     | `SELECT NOW();`                                  |
| `CURDATE()`      | Returns current date              | `SELECT CURDATE();`                              |
| `DATE_ADD()`     | Adds interval to date             | `SELECT DATE_ADD('2025-08-10', INTERVAL 5 DAY);`|
| `DATEDIFF()`     | Difference between two dates (days) | `SELECT DATEDIFF('2025-09-15', '2025-08-10');`  |
| `YEAR()`, `MONTH()`, `DAY()` | Extract parts of date    | `SELECT YEAR(event_date) FROM events;`           |
