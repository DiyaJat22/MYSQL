# 📘 MySQL Basics Explained

## 🔍 What is MySQL?

**MySQL** is a popular open-source **Relational Database Management System (RDBMS)** that uses **SQL (Structured Query Language)** to manage and interact with databases.

- Developed by: Oracle Corporation
- Used in: Web apps, cloud services, cybersecurity tools, and more.
- Part of: **LAMP stack** (Linux, Apache, MySQL, PHP/Python)

---

## 🏗️ How MySQL Works

1. **Client** sends a SQL query to the MySQL server.
2. The **server** processes the query.
3. It communicates with the **storage engine** (e.g., InnoDB).
4. The **result** is returned to the client.

---

## 🗂️ Key Concepts

| Term         | Description                                           |
|--------------|-------------------------------------------------------|
| Database     | A collection of related tables                        |
| Table        | A structured format to store data (rows and columns) |
| Row (Record) | A single entry in a table                             |
| Column       | A data field (e.g., username, email)                  |
| Primary Key  | Unique identifier for each record                     |
| Query        | A command written in SQL                              |

---

## 📄 Common SQL Queries

```sql
-- Show all databases
SHOW DATABASES;

-- Use a specific database
USE diya_db;

-- Create a new table
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50),
  password VARCHAR(100)
);

-- Insert data
INSERT INTO users (username, password) VALUES ('admin', 'securepass');

-- Retrieve data
SELECT * FROM users;

-- Update data
UPDATE users SET password = 'newpass' WHERE username = 'admin';

-- Delete data
DELETE FROM users WHERE id = 1;
