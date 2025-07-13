# MySQL SELECT Statement

The `SELECT` statement is used to select data from a database.

The data returned is stored in a result table, called the **result-set**.

---

## SELECT Syntax

```sql
SELECT column1, column2, ...
FROM table_name;
```

Here, `column1`, `column2`, ... are the field names of the table you want to select data from.  
If you want to select **all the fields** available in the table, use the following syntax:

```sql
SELECT * FROM table_name;
```

---

## Demo Database

In this tutorial, we use the well-known **Northwind** sample database.

Below is a selection from the `"Customers"` table in the Northwind sample database:

| CustomerID | CustomerName                        | ContactName      | Address                      | City       | PostalCode | Country |
|------------|-------------------------------------|------------------|------------------------------|------------|------------|---------|
| 1          | Alfreds Futterkiste                 | Maria Anders     | Obere Str. 57                | Berlin     | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados  | Ana Trujillo     | Avda. de la Constitución 2222| México D.F.| 05021      | Mexico  |
| 3          | Antonio Moreno Taquería             | Antonio Moreno   | Mataderos 2312              | México D.F.| 05023      | Mexico  |
| 4          | Around the Horn                     | Thomas Hardy     | 120 Hanover Sq.             | London     | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                  | Christina Berglund| Berguvsvägen 8              | Luleå      | S-958 22   | Sweden  |

---

## SELECT Columns Example

The following SQL statement selects the `"CustomerName"`, `"City"`, and `"Country"` columns from the `"Customers"` table:

```sql
SELECT CustomerName, City, Country FROM Customers;
```

---

## SELECT * Example

The following SQL statement selects **all the columns** from the `"Customers"` table:

```sql
SELECT * FROM Customers;
```

---

# MySQL SELECT DISTINCT Statement

The `SELECT DISTINCT` statement is used to return **only distinct (different)** values.

Inside a table, a column often contains many duplicate values. Sometimes you only want to list the different (distinct) values.

---

## SELECT DISTINCT Syntax

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

---

## SELECT Example Without DISTINCT

The following SQL statement selects **all** (including the duplicates) values from the `"Country"` column in the `"Customers"` table:

```sql
SELECT Country FROM Customers;
```

---

## SELECT DISTINCT Examples

The following SQL statement selects only the **distinct** values from the `"Country"` column in the `"Customers"` table:

```sql
SELECT DISTINCT Country FROM Customers;
```

# MySQL SELECT Statement Examples

## 1. Select All Columns from a Table
```sql
SELECT * FROM Customers;
```

## 2. Select Specific Columns
```sql
SELECT CustomerName, City, Country FROM Customers;
```

## 3. Using WHERE Clause
```sql
SELECT * FROM Customers
WHERE Country = 'Germany';
```

## 4. WHERE with AND Condition
```sql
SELECT * FROM Customers
WHERE Country = 'Germany' AND City = 'Berlin';
```

## 5. WHERE with OR Condition
```sql
SELECT * FROM Customers
WHERE City = 'Berlin' OR City = 'London';
```

## 6. Using LIKE for Pattern Matching
```sql
SELECT * FROM Customers
WHERE CustomerName LIKE 'A%';  -- starts with 'A'
```

## 7. Using IN Operator
```sql
SELECT * FROM Customers
WHERE Country IN ('Germany', 'Mexico');
```

## 8. Using BETWEEN for Ranges
```sql
SELECT * FROM Orders
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';
```

## 9. ORDER BY Ascending (Default)
```sql
SELECT * FROM Customers
ORDER BY CustomerName;
```

## 10. ORDER BY Descending
```sql
SELECT * FROM Customers
ORDER BY CustomerName DESC;
```

## 11. LIMIT the Number of Results
```sql
SELECT * FROM Customers
LIMIT 5;
```

## 12. DISTINCT Values
```sql
SELECT DISTINCT Country FROM Customers;
```

## 13. COUNT() with DISTINCT
```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```

## 14. Aliases (AS)
```sql
SELECT CustomerName AS Name, ContactName AS Contact FROM Customers;
```

## 15. Simple JOIN Example
```sql
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

---

**Note:** All examples are based on the Northwind sample database. Replace table and column names as per your database.


The following SQL statement counts and returns the **number of different (distinct)** countries in the `"Customers"` table:

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```
