# MySQL Comments

Comments are used to add notes or explanations within SQL code. They are ignored by the MySQL server during execution.

---

## Types of Comments in MySQL

### 1. Single-line Comments

- Use `--` (double hyphen) followed by a space
- Use `#` (hash symbol)

**Examples:**

```sql
-- This is a single-line comment using double hyphen

# This is a single-line comment using hash symbol
```

---

### 2. Multi-line (Block) Comments

    Enclosed between /* and */

    Can span multiple lines

### Example:

```sql
/* 
  This is a multi-line comment.
  It can span multiple lines.
*/
```

### Usage Tips

   Single-line comments must have a space or control character after --.

   Use comments to explain complex queries, mark sections, or temporarily disable code.

### Example Usage

```sql
SELECT * FROM employees; -- Select all employees

/*
  Update salary for department 1
  Increase by 10%
*/
UPDATE employees
SET salary = salary * 1.10
WHERE dept_id = 1;
```

