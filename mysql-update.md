# MySQL UPDATE Statement

## 📌 Description

The UPDATE statement in MySQL is used to modify existing records in a table.
You can update one column, multiple columns, or even all rows depending on the conditions provided.

📝 Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

  table_name – The name of the table where you want to update data.

  SET – Defines the column(s) and their new value(s).

  HERE – Specifies which row(s) to update.
  ⚠️ Without WHERE, all rows will be updated.

## ⚙ Examples

### 1️⃣ Update a Single Column

```sql
UPDATE employees
SET salary = 50000
WHERE id = 3;
```

✅ Sets the salary of the employee with id = 3 to 50000.

---

### 2️⃣ Update Multiple Columns

```sql
UPDATE employees
SET salary = 60000, department = 'IT'
WHERE id = 4;
```

✅ Updates both salary and department for the employee with id = 4.

---

### 3️⃣ Update Multiple Rows

```sql
UPDATE employees
SET bonus = 1000
WHERE department = 'Sales';
```

✅ Gives all employees in the Sales department a bonus of 1000.

---

### 4️⃣ Update All Rows (No WHERE)

```sql
UPDATE employees
SET bonus = 500;
```

⚠️ This will update every row in the table — use with caution.

---

### 5️⃣ Update Using an Expression

```sql
UPDATE employees
SET salary = salary * 1.10
WHERE department = 'HR';
```

✅ Increases salary by 10% for all employees in HR.

---

### 6️⃣ Update from Another Table (JOIN)

```sql
UPDATE employees e
JOIN departments d ON e.department_id = d.id
SET e.department_name = d.name
WHERE d.location = 'New York';
```

✅ Updates department_name in employees table based on matching records from departments table.

---

### ⚠ Best Practices

   Always use WHERE unless you intend to update all rows.

  Test your query first with SELECT before running UPDATE.

  Make backups before large updates.
