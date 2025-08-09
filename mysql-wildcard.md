## 1. % (Percent Sign)

    Represents zero, one, or multiple characters.

    Used when you don’t know the exact length of the text you’re searching for.

### Example:

```sql
SELECT * 
FROM employees
WHERE name LIKE 'A%';
```

Meaning: Find all employees whose name starts with "A".

    Matches: Alex, Alice, Andrew, A, etc.

---

## 2. _ (Underscore)

    Represents exactly one character.

    Useful when you know the character length but not the exact character.

### Example:

```sql
SELECT * 
FROM employees
WHERE name LIKE '_a%';
```

Meaning: Find all employees where the second letter is "a".

    Matches: Jack, Mark, Max, but not Alex.

---

## 3. [] (Character Set) (MySQL REGEXP instead)

⚠ In standard SQL, [] means match any single character inside brackets, but MySQL’s LIKE does not support [].

    Instead, use REGEXP in MySQL.

### Example:

```sql
SELECT * 
FROM employees
WHERE name REGEXP '^[JM]';
```

Meaning: Find employees whose name starts with J or M.

---

## 4. [^ ] or ![] (Negated Character Set)

    Matches any single character not inside the brackets.

    Again, in MySQL, use REGEXP.

### Example:

```sql
SELECT * 
FROM employees
WHERE name REGEXP '^[^A]';
```

Meaning: Find employees whose name does not start with A.

---

## MySQL Wildcards

| Wildcard Pattern | Matches Example        | Does Not Match |
|------------------|------------------------|----------------|
| `A%`             | Alex, Adam, A          | Mark, John     |
| `%son`           | Jackson, Wilson        | Jack, Wil      |
| `_a%`            | Mark, Jack, Max         | Alex           |
| `J%n`            | John, Jason            | Jack, Jane     |
