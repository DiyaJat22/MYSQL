# MySQL Data Types

MySQL supports various data types to store different kinds of data such as numbers, text, dates, and more. Choosing the correct data type is important for efficient storage and performance.

---

## Categories of MySQL Data Types

| Category        | Description                               | Examples                             |
|-----------------|-------------------------------------------|------------------------------------|
| Numeric         | Stores numbers (integers and decimals)    | INT, TINYINT, BIGINT, DECIMAL, FLOAT, DOUBLE |
| Date and Time   | Stores date and time values                 | DATE, DATETIME, TIMESTAMP, TIME, YEAR |
| String (Character) | Stores text and string data               | CHAR, VARCHAR, TEXT, BLOB, ENUM, SET |

---

## Numeric Data Types

| Data Type  | Size (Bytes) | Description                                    | Range (Signed)                              |
|------------|--------------|------------------------------------------------|--------------------------------------------|
| TINYINT    | 1            | Small integer                                  | -128 to 127                                |
| SMALLINT   | 2            | Small integer                                  | -32,768 to 32,767                          |
| MEDIUMINT  | 3            | Medium integer                                 | -8,388,608 to 8,388,607                    |
| INT or INTEGER | 4         | Standard integer                               | -2,147,483,648 to 2,147,483,647            |
| BIGINT     | 8            | Large integer                                  | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| DECIMAL(M,D) | Variable    | Fixed-point number with M digits and D decimals | User-defined precision                     |
| FLOAT      | 4            | Floating-point number                          | Approximate range                          |
| DOUBLE     | 8            | Double-precision floating-point number        | Approximate range                          |

---

## Date and Time Data Types

| Data Type  | Format                 | Description                  |
|------------|------------------------|------------------------------|
| DATE       | 'YYYY-MM-DD'           | Stores date only             |
| DATETIME   | 'YYYY-MM-DD HH:MM:SS'  | Stores date and time        |
| TIMESTAMP  | 'YYYY-MM-DD HH:MM:SS'  | Stores date and time with timezone handling |
| TIME       | 'HH:MM:SS'             | Stores time only             |
| YEAR       | YYYY                   | Stores year only             |

---

## String Data Types

| Data Type  | Description                                    | Max Length                   |
|------------|------------------------------------------------|-----------------------------|
| CHAR(M)    | Fixed-length string                            | 0 to 255 characters          |
| VARCHAR(M) | Variable-length string                         | 0 to 65,535 bytes (depends on row size) |
| TEXT       | Large text data                               | Up to 65,535 characters      |
| TINYTEXT   | Very small text                               | Up to 255 characters         |
| MEDIUMTEXT | Medium-sized text                             | Up to 16,777,215 characters  |
| LONGTEXT   | Very large text                              | Up to 4,294,967,295 characters |
| BLOB       | Binary Large Object, stores binary data      | Up to 65,535 bytes           |
| ENUM       | Enumeration: predefined list of values        | Up to 65,535 distinct values |
| SET        | Set of zero or more predefined values          | Up to 64 distinct members    |

---

## Notes

- Choose the smallest data type that fits your data to optimize performance and storage.
- `VARCHAR` is more flexible than `CHAR`, but `CHAR` can be faster for fixed-size fields.
- Use `DECIMAL` for precise monetary values instead of `FLOAT` or `DOUBLE`.
- Date/time functions help manipulate date/time data efficiently.

---
