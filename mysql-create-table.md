# MySQL CREATE TABLE

The `CREATE TABLE` statement is used to create a new table in a MySQL database.

---

## Syntax

```sql
CREATE TABLE table_name (
    column1 datatype [constraints],
    column2 datatype [constraints],
    ...
);
```

 table_name: Name of the table to create.

 column1, column2, ...: Names of columns.

 datatype: Data type of the column (e.g., INT, VARCHAR, DATE).

 constraints: Optional constraints like PRIMARY KEY, NOT NULL, UNIQUE, etc.

## Example 1: Create a Simple Table

Create a table named employees:

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    salary DECIMAL(10,2)
);
```

## Example 2: Create Table with Auto-Increment Primary Key

```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT,
    salary DECIMAL(10,2)
);
```

## Example 3: Create Table with Multiple Constraints

```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT CHECK (age >= 18),
    email VARCHAR(100) UNIQUE,
    salary DECIMAL(10,2) DEFAULT 0.00,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(id)
);
```

# MySQL CREATE TABLE - More Examples

---

## Example 4: Create Table with Different Data Types

```sql
CREATE TABLE products (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(255) NOT NULL,
    price DECIMAL(8,2) NOT NULL,
    quantity INT DEFAULT 0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

 VARCHAR(255): Text up to 255 characters.

 DECIMAL(8,2): Number with 8 digits total, 2 after decimal.

 TIMESTAMP: Stores date and time.

## Example 5: Create Table with Composite Primary Key

```sql
CREATE TABLE order_items (
    order_id INT,
    product_id INT,
    quantity INT NOT NULL,
    PRIMARY KEY (order_id, product_id)
);
```

  Composite primary key uses two columns (order_id and product_id) together to uniquely identify rows.

## Example 6: Create Table with Foreign Key Constraint

```sql
CREATE TABLE orders (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```
  FOREIGN KEY links customer_id in orders to customer_id in customers table.



