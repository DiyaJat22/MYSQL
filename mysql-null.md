# 🗄 MySQL — NULL Values

## 📌 What is a NULL Value?
- A **NULL value** represents **missing** or **unknown data**.
- A NULL is **NOT** the same as:
  - **Zero (0)**
  - **Empty string ('')**
  - **A field with spaces ('   ')**

If a field is optional, it can be left blank when inserting or updating records.  
In that case, MySQL will store it as `NULL`.

---

## 🚫 Why can't we use `=` for NULL?
NULL means "unknown", so you **cannot** compare it directly:

```sql
-- ❌ This will NOT work
SELECT * FROM Customers WHERE Address = NULL;
```

Instead, use:

  IS NULL → Finds rows where the value is NULL.

  IS NOT NULL → Finds rows where the value is not NULL.
  

🛠 Syntax

```sql
-- Find rows where a column has no value
SELECT column_names
FROM table_name
WHERE column_name IS NULL;

-- Find rows where a column has a value
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

📊 Demo Table — Customers
CustomerID	CustomerName	ContactName	Address	City	PostalCode	Country
89	White Clover Markets	Karl Jablonski	305 - 14th Ave. S. Suite 3B	Seattle	98128	USA
90	Wilman Kala	Matti Karttunen	Keskuskatu 45	Helsinki	21240	Finland
91	Wolski	Zbyszek	ul. Filtrowa 68	Walla	01-012	Poland
92	Cardinal	NULL	NULL	Stavanger	NULL	Norway

---

## 📌 Example 1 — Find all customers with no ContactName

```sql
SELECT CustomerName, City
FROM Customers
WHERE ContactName IS NULL;
```

Description:
Returns only customers whose ContactName is missing.

---

## 📌 Example 2 — Find all customers that have a PostalCode

```sql
SELECT CustomerName, PostalCode
FROM Customers
WHERE PostalCode IS NOT NULL;
```

Description:
Filters out rows where PostalCode is NULL.

---

## 📌 Example 3 — Insert a row with NULL values

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Oceanic Foods', NULL, NULL, 'Lisbon', NULL, 'Portugal');
```

Description:
Inserts a new record where some fields are intentionally left NULL.

---

## 📌 Example 4 — Update a column to NULL

```sql
UPDATE Customers
SET Address = NULL
WHERE CustomerID = 90;
```

Description:
Removes the Address for the customer with ID 90.

---

## 📌 Example 5 — Count how many NULL values exist in a column

```sql
SELECT COUNT(*) AS NullCount
FROM Customers
WHERE Address IS NULL;
```

Description:
Counts how many customers have no address stored.

---

## 🔹 Key Points

  NULL means "no data" — not zero, not empty string.

  Use IS NULL / IS NOT NULL to filter.

  NULL values can be inserted or updated explicitly.

  Be careful when using functions — many functions ignore NULL values unless handled.

