# MySQL ORDER BY Keyword
## 📌 Definition

The ORDER BY keyword is used to sort the result set in either ascending or descending order.

    Ascending (ASC) is the default.

    Descending (DESC) must be explicitly specified.

## 📜 Syntax

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC], column2 [ASC|DESC], ...;
```

## 🗄 Demo Table — Customers

| CustomerID | CustomerName                          | ContactName        | City       | Country |
|------------|---------------------------------------|--------------------|------------|---------|
| 1          | Alfreds Futterkiste                   | Maria Anders       | Berlin     | Germany |
| 2          | Ana Trujillo Emparedados y helados    | Ana Trujillo       | México D.F.| Mexico  |
| 3          | Antonio Moreno Taquería               | Antonio Moreno     | México D.F.| Mexico  |
| 4          | Around the Horn                       | Thomas Hardy       | London     | UK      |
| 5          | Berglunds snabbköp                    | Christina Berglund | Luleå      | Sweden  |


## 1️⃣ Sort in Ascending Order (Default)

```sql
SELECT * 
FROM Customers
ORDER BY Country;
```

✅ Explanation: Results are sorted A → Z by the Country column.

## 2️⃣ Sort in Descending Order

```sql
SELECT * 
FROM Customers
ORDER BY Country DESC;
```

✅ Explanation: Results are sorted Z → A by Country.

## 3️⃣ Sort by Multiple Columns

```sql
SELECT * 
FROM Customers
ORDER BY Country, CustomerName;
```

✅ Explanation:

    First sort by Country (A → Z).

    If two rows have the same Country, sort by CustomerName (A → Z).

## 4️⃣ Mixed Sort Orders

```sql
SELECT * 
FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

✅ Explanation:

    Sort Country ascending (A → Z).

    For the same Country, sort CustomerName descending (Z → A).

## 5️⃣ Sort by Numeric Column

```sql
SELECT * 
FROM Orders
ORDER BY OrderAmount DESC;
```

✅ Explanation: Sort orders by the amount, highest first.

## 6️⃣ Sort by Date

```sql
SELECT * 
FROM Orders
ORDER BY OrderDate ASC;
```

✅ Explanation: Sort orders from oldest to newest.

## 7️⃣ Sort with Expressions

```sql
SELECT * 
FROM Products
ORDER BY (price * quantity) DESC;
```

✅ Explanation: Sort by total value of stock, highest first.

## 8️⃣ Sort with LIMIT

```sql
SELECT * 
FROM Customers
ORDER BY Country, CustomerName
LIMIT 5;
```

✅ Explanation: Shows only the first 5 rows after sorting.

## 💡 Key Points to Remember

  ASC is default; you can omit it.

  DESC must be explicitly added.

  Multiple columns can be sorted with different orders.

  Parentheses and expressions can be used in ORDER BY.

  Works with text, numbers, dates, and calculated values.

