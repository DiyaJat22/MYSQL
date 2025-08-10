# MySQL ALTER TABLE

The `ALTER TABLE` statement is used to modify the structure of an existing table, such as adding or dropping columns, changing data types, renaming columns or tables, and adding constraints.

---

## Syntax

```sql
ALTER TABLE table_name
[ADD | DROP | MODIFY | CHANGE | RENAME] column_definition_or_table_name;
```

# Common Operations

## 1. Add a New Column

```sql
ALTER TABLE employees
ADD COLUMN email VARCHAR(100);
```

## 2. Drop a Column

```sql
ALTER TABLE employees
DROP COLUMN email;
```

## 3. Modify Column Data Type

```sql
ALTER TABLE employees
MODIFY COLUMN salary DECIMAL(12,2);
```

## 4. Change Column Name and Data Type

```sql
ALTER TABLE employees
CHANGE COLUMN name full_name VARCHAR(150);
```

## 5. Rename Table

```sql
ALTER TABLE employees
RENAME TO staff;
```

## 6. Add Primary Key

```sql
ALTER TABLE employees
ADD PRIMARY KEY (id);
```

## 7. Drop Primary Key

```sql
ALTER TABLE employees
DROP PRIMARY KEY;
```

## 8. Add Foreign Key Constraint

```sql
ALTER TABLE employees
ADD CONSTRAINT fk_dept
FOREIGN KEY (department_id) REFERENCES departments(id);
```

## 9. Drop Foreign Key Constraint

```sql
ALTER TABLE employees
DROP FOREIGN KEY fk_dept;
```

## Notes

  Some changes might require the table to be locked during operation.

  Be careful while modifying columns with existing data.

  Always back up data before making structural changes.

## Verify Table Structure

Use:

```sql
DESCRIBE employees;
```

or

```sql
SHOW COLUMNS FROM employees;
```
