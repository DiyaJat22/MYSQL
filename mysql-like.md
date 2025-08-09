# Wildcards Used in LIKE

  % — Represents zero, one, or many characters.

   _ — Represents exactly one character.

## Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;
```

---

# Examples

## 1️⃣ Match names starting with 'A'

```sql
SELECT * FROM customers
WHERE name LIKE 'A%';
```

Explanation:
Matches: Ankit, Aman, Anshul
Does not match: Manish, Sanket

---

## 2️⃣ Match names ending with 'n'

```sql
SELECT * FROM customers
WHERE name LIKE '%n';
```

Matches: Arun, Karan, John
Does not match: Amit, Raj

---

## 3️⃣ Match names containing 'mit'

```sql
SELECT * FROM customers
WHERE name LIKE '%mit%';
```

Matches: Amit, Smitesh
Does not match: Rajesh

---

## 4️⃣ Match names with exactly 4 letters

```sql
SELECT * FROM customers
WHERE name LIKE '____';
```

Matches: Amit, John
Does not match: Raj, Ankit

---

## 5️⃣ Match second letter as 'a'

```sql
SELECT * FROM customers
WHERE name LIKE '_a%';
```

Matches: Ravi, Karan, Manish
Does not match: Amit, Rohit

---

## 6️⃣ Case-insensitive search (default in MySQL)

```sql
SELECT * FROM customers
WHERE name LIKE 'amit';
```

Matches both Amit and AMIT.

---
