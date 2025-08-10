# MySQL Functions - Description and Overview

MySQL provides a rich set of built-in functions categorized into String, Numeric, Date, and Advanced functions. These functions help in manipulating data efficiently in SQL queries.

---

## MySQL String Functions

| Function          | Description                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| `ASCII`           | Returns the ASCII value for the specified character                                          |
| `CHAR_LENGTH`     | Returns the length of a string (in characters)                                               |
| `CHARACTER_LENGTH`| Same as `CHAR_LENGTH`, returns string length (characters)                                    |
| `CONCAT`          | Concatenates two or more expressions                                                         |
| `CONCAT_WS`       | Concatenates with a separator between expressions                                            |
| `FIELD`           | Returns the index position of a value in a list                                             |
| `FIND_IN_SET`     | Returns the position of a string within a list of strings                                   |
| `FORMAT`          | Formats a number with grouped thousands and decimal places                                  |
| `INSERT`          | Inserts a string into another string at a specified position for a given length             |
| `INSTR`           | Returns the position of the first occurrence of a substring                                 |
| `LCASE` / `LOWER` | Converts a string to lowercase                                                              |
| `LEFT`            | Extracts a specified number of characters from the left of a string                         |
| `LENGTH`          | Returns the length of a string (in bytes)                                                   |
| `LOCATE` / `POSITION` | Returns the position of the first occurrence of a substring                              |
| `LPAD`            | Left-pads a string with another string to a specified length                                |
| `LTRIM`           | Removes leading spaces                                                                       |
| `MID` / `SUBSTR` / `SUBSTRING` | Extracts a substring from a string starting at any position                   |
| `REPEAT`          | Repeats a string a specified number of times                                               |
| `REPLACE`         | Replaces all occurrences of a substring within a string with another substring             |
| `REVERSE`         | Reverses a string                                                                           |
| `RIGHT`           | Extracts a specified number of characters from the right of a string                       |
| `RPAD`            | Right-pads a string with another string to a specified length                              |
| `RTRIM`           | Removes trailing spaces                                                                     |
| `SPACE`           | Returns a string consisting of a specified number of space characters                       |
| `STRCMP`          | Compares two strings                                                                       |
| `SUBSTRING_INDEX` | Returns substring before a specified number of occurrences of a delimiter                   |
| `TRIM`            | Removes leading and trailing spaces                                                        |
| `UCASE` / `UPPER` | Converts a string to uppercase                                                             |

---

## MySQL Numeric Functions

| Function          | Description                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| `ABS`             | Returns the absolute value of a number                                                      |
| `ACOS`            | Returns the arc cosine of a number                                                          |
| `ASIN`            | Returns the arc sine of a number                                                            |
| `ATAN` / `ATAN2`  | Returns the arc tangent of one or two numbers                                               |
| `AVG`             | Returns the average value of an expression                                                  |
| `CEIL` / `CEILING`| Returns the smallest integer value greater than or equal to a number                        |
| `COS`             | Returns the cosine of a number                                                              |
| `COT`             | Returns the cotangent of a number                                                           |
| `COUNT`           | Returns the number of rows returned by a select query                                      |
| `DEGREES`         | Converts radians to degrees                                                                 |
| `DIV`             | Performs integer division                                                                   |
| `EXP`             | Returns e raised to the power of a number                                                  |
| `FLOOR`           | Returns the largest integer value less than or equal to a number                           |
| `GREATEST`        | Returns the greatest value from a list                                                     |
| `LEAST`           | Returns the smallest value from a list                                                    |
| `LN`              | Returns the natural logarithm of a number                                                 |
| `LOG`, `LOG10`, `LOG2` | Returns logarithm of a number (natural, base 10, base 2)                             |
| `MAX`             | Returns the maximum value in a set                                                        |
| `MIN`             | Returns the minimum value in a set                                                        |
| `MOD`             | Returns the remainder of a division                                                       |
| `PI`              | Returns the value of π                                                                     |
| `POW` / `POWER`   | Returns a number raised to the power of another number                                    |
| `RADIANS`         | Converts degrees to radians                                                                |
| `RAND`            | Returns a random floating-point value                                                    |
| `ROUND`           | Rounds a number to a specified number of decimal places                                  |
| `SIGN`            | Returns the sign of a number                                                              |
| `SIN`             | Returns the sine of a number                                                              |
| `SQRT`            | Returns the square root of a number                                                      |
| `SUM`             | Calculates the sum of values in a set                                                    |
| `TAN`             | Returns the tangent of a number                                                           |
| `TRUNCATE`        | Truncates a number to a specified number of decimal places                               |

---

## MySQL Date Functions

| Function             | Description                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------|
| `ADDDATE` / `DATE_ADD` | Adds a time/date interval to a date and returns the date                                   |
| `ADDTIME`             | Adds a time interval to a time/datetime and returns the result                              |
| `CURDATE` / `CURRENT_DATE` | Returns the current date                                                                |
| `CURRENT_TIME` / `CURTIME` | Returns the current time                                                                |
| `CURRENT_TIMESTAMP` / `NOW` | Returns the current date and time                                                      |
| `DATE`                | Extracts the date part from a datetime expression                                           |
| `DATEDIFF`            | Returns the number of days between two dates                                               |
| `DATE_FORMAT`         | Formats a date as specified                                                               |
| `DATE_SUB` / `SUBDATE` | Subtracts a time/date interval from a date                                               |
| `DAY`, `DAYOFMONTH`   | Returns the day of the month                                                               |
| `DAYNAME`             | Returns the weekday name                                                                   |
| `DAYOFWEEK`           | Returns the weekday index (1=Sunday, 7=Saturday)                                          |
| `DAYOFYEAR`           | Returns the day of the year                                                                |
| `EXTRACT`             | Extracts part of a date (year, month, day, etc.)                                           |
| `FROM_DAYS`           | Returns a date from a numeric date value                                                   |
| `HOUR`                | Returns the hour part of a time/datetime                                                  |
| `LAST_DAY`            | Returns the last day of the month                                                         |
| `LOCALTIME` / `LOCALTIMESTAMP` | Returns the current date and time                                                    |
| `MAKEDATE`            | Creates a date from year and day-of-year                                                 |
| `MAKETIME`            | Creates a time from hour, minute, and second                                             |
| `MICROSECOND`         | Returns microseconds from a time/datetime                                                |
| `MINUTE`              | Returns the minute part of a time/datetime                                              |
| `MONTH`               | Returns the month part of a date                                                         |
| `MONTHNAME`           | Returns the name of the month                                                            |
| `PERIOD_ADD`          | Adds months to a period                                                                  |
| `PERIOD_DIFF`         | Returns the difference between two periods                                              |
| `QUARTER`             | Returns the quarter of the year                                                          |
| `SECOND`              | Returns the seconds part of a time/datetime                                             |
| `SEC_TO_TIME`         | Converts seconds to time                                                                 |
| `STR_TO_DATE`         | Parses a date from a string using a format                                              |
| `SUBTIME`             | Subtracts a time interval from a time/datetime                                         |
| `SYSDATE`             | Returns the current date and time                                                       |
| `TIME`                | Extracts the time part from a datetime                                                  |
| `TIME_FORMAT`         | Formats time                                                                              |
| `TIME_TO_SEC`         | Converts time to seconds                                                                 |
| `TIMEDIFF`            | Returns difference between two times/datetimes                                         |
| `TIMESTAMP`           | Returns a datetime value                                                                |
| `TO_DAYS`             | Returns the number of days since year 0                                                |
| `WEEK`, `WEEKOFYEAR` | Returns the week number for a date                                                     |
| `WEEKDAY`             | Returns weekday index (0=Monday, 6=Sunday)                                            |
| `YEAR`                | Returns the year part of a date                                                        |
| `YEARWEEK`            | Returns the year and week number                                                       |

---

## MySQL Advanced Functions

| Function          | Description                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| `BIN`             | Returns the binary representation of a number                                               |
| `BINARY`          | Converts a value to a binary string                                                         |
| `CASE`            | Conditional logic: returns value based on conditions                                       |
| `CAST`            | Converts a value from one data type to another                                             |
| `COALESCE`        | Returns the first non-null value from a list                                               |
| `CONNECTION_ID`   | Returns the unique connection ID for the current connection                                |
| `CONV`            | Converts a number between different base systems                                           |
| `CONVERT`         | Converts a value to a specified datatype or character set                                  |
| `CURRENT_USER`    | Returns the authenticated MySQL user and host                                             |
| `DATABASE`        | Returns the name of the current database                                                   |
| `IF`              | Returns one value if a condition is TRUE, another if FALSE                                |
| `IFNULL`          | Returns a specified value if expression is NULL, else returns the expression               |
| `ISNULL`          | Returns 1 if expression is NULL, otherwise 0                                              |
| `LAST_INSERT_ID`  | Returns the AUTO_INCREMENT id of the last inserted row                                    |
| `NULLIF`          | Returns NULL if two expressions are equal, else returns the first expression               |
| `SESSION_USER`    | Returns the current MySQL user and host                                                   |
| `SYSTEM_USER`     | Returns the current MySQL user and host                                                   |
| `USER`            | Returns the current MySQL user and host                                                   |
| `VERSION`         | Returns the MySQL server version                                                          |

---
