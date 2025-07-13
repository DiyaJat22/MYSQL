# 📘 RDBMS and Relational Databases Explained

## 🗄️ What is RDBMS?

**RDBMS** stands for **Relational Database Management System**.

- It is a program used to create, manage, and maintain **relational databases**.
- RDBMS is the foundation for modern database systems such as:
  - **MySQL**
  - **Microsoft SQL Server**
  - **Oracle**
  - **Microsoft Access**
- It uses **SQL (Structured Query Language)** to access and manage data stored in the database.

---

## 📊 What is a Database Table?

A **table** is a collection of related data entries organized into **columns and rows**.

- A **column** defines a specific data type and stores one piece of information for each record (e.g., `CustomerName`, `City`).
- A **row** (also called a **record**) represents a single entry in the table.

### Example: `Customers` Table (from Northwind Database)

| CustomerID | CustomerName                      | ContactName       | Address                    | City        | PostalCode | Country |
|------------|-----------------------------------|-------------------|----------------------------|-------------|------------|---------|
| 1          | Alfreds Futterkiste               | Maria Anders      | Obere Str. 57              | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados| Ana Trujillo      | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería           | Antonio Moreno    | Mataderos 2312             | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                   | Thomas Hardy      | 120 Hanover Sq.            | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                | Christina Berglund| Berguvsvägen 8             | Luleå       | S-958 22   | Sweden  |

> The columns in this table are: `CustomerID`, `CustomerName`, `ContactName`, `Address`, `City`, `PostalCode`, and `Country`.  
> The table contains **5 records (rows)**.

---

## 🔗 What is a Relational Database?

A **relational database** organizes data into **tables** and allows relationships between them using **keys**.

Tables are **linked** based on common fields such as `CustomerID`, `ShipperID`, etc.

---

## 🧩 Example of Table Relationships

### 1. `Customers` Table (simplified)

| CustomerID | CustomerName                      |
|------------|-----------------------------------|
| 1          | Alfreds Futterkiste               |
| 2          | Ana Trujillo Emparedados y helados|
| 3          | Antonio Moreno Taquería           |
| 4          | Around the Horn                   |
| 5          | Berglunds snabbköp                |

---

### 2. `Orders` Table

| OrderID | CustomerID | EmployeeID | OrderDate   | ShipperID |
|---------|------------|------------|-------------|-----------|
| 10278   | 5          | 8          | 1996-08-12  | 2         |
| 10280   | 5          | 2          | 1996-08-14  | 1         |
| 10308   | 2          | 7          | 1996-09-18  | 3         |
| 10355   | 4          | 6          | 1996-11-15  | 1         |
| 10365   | 3          | 3          | 1996-11-27  | 2         |
| 10383   | 4          | 8          | 1996-12-16  | 3         |
| 10384   | 5          | 3          | 1996-12-16  | 3         |

**Relationship:** The `CustomerID` in this table relates to the `Customers` table, creating a **foreign key** relationship.

---

### 3. `Shippers` Table

| ShipperID | ShipperName      | Phone           |
|-----------|------------------|-----------------|
| 1         | Speedy Express   | (503) 555-9831  |
| 2         | United Package   | (503) 555-3199  |
| 3         | Federal Shipping | (503) 555-9931  |

**Relationship:** The `ShipperID` in the `Orders` table relates to the `Shippers` table.

---

## 🔄 Summary

- **RDBMS** manages relational databases using SQL.
- **Tables** store data in rows and columns.
- **Relationships** are created between tables using **primary and foreign keys**.
- This design improves data integrity, reduces redundancy, and enables powerful queries.

---

