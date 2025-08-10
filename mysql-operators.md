# MySQL Operators

## 1. Arithmetic Operators

| Operator | Description        | Example          |
|----------|--------------------|------------------|
| `+`      | Addition           | `SELECT 5 + 3;`  |
| `-`      | Subtraction        | `SELECT 5 - 3;`  |
| `*`      | Multiplication     | `SELECT 5 * 3;`  |
| `/`      | Division           | `SELECT 5 / 3;`  |
| `%`      | Modulus (remainder)| `SELECT 5 % 3;`  |

## 2. Comparison Operators

| Operator   | Description          | Example             |
|------------|----------------------|---------------------|
| `=`        | Equal                | `WHERE age = 25`    |
| `!=` or `<>` | Not equal           | `WHERE age != 25`   |
| `>`        | Greater than         | `WHERE salary > 50000` |
| `<`        | Less than            | `WHERE salary < 50000` |
| `>=`       | Greater than or equal| `WHERE age >= 18`   |
| `<=`       | Less than or equal   | `WHERE age <= 65`   |

## 3. Logical Operators

| Operator | Description           | Example                        |
|----------|-----------------------|-------------------------------|
| `AND`    | Both conditions true  | `WHERE age > 18 AND salary > 30000` |
| `OR`     | Either condition true | `WHERE age < 18 OR salary > 30000`  |
| `NOT`    | Negates condition     | `WHERE NOT(age = 30)`          |

## 4. Bitwise Operators

| Operator | Description       | Example          |
|----------|-------------------|------------------|
| `&`      | Bitwise AND       | `SELECT 5 & 3;`  |
| `|`      | Bitwise OR        | `SELECT 5 | 3;`  |
| `^`      | Bitwise XOR       | `SELECT 5 ^ 3;`  |
| `~`      | Bitwise NOT       | `SELECT ~5;`     |
| `<<`     | Left shift        | `SELECT 5 << 1;` |
| `>>`     | Right shift       | `SELECT 5 >> 1;` |

## 5. Assignment Operators

| Operator | Description                      | Example          |
|----------|---------------------------------|------------------|
| `=`      | Assign value                    | `SET @a = 10;`   |
| `:=`     | Assign value (in expressions)  | `SET @a := 10;`  |

## 6. Other Operators

| Operator   | Description                    | Example                             |
|------------|--------------------------------|-----------------------------------|
| `BETWEEN`  | Between a range                | `WHERE salary BETWEEN 30000 AND 50000` |
| `LIKE`     | Pattern matching              | `WHERE name LIKE 'A%'`             |
| `IN`       | Value in a list               | `WHERE id IN (1, 2, 3)`            |
| `IS NULL`  | Check for NULL                | `WHERE dept_id IS NULL`            |
| `EXISTS`   | Check if subquery returns rows| `WHERE EXISTS (SELECT * FROM table)` |
