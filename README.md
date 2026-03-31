# sql-union-clause


##  UNION

This  demonstrates how to combine rows from multiple queries using the **UNION** clause in SQL.

---

## 🔍 Key Concepts

### What is UNION?

* Combines results from two or more `SELECT` statements
* Stacks rows on top of each other (not columns like JOINs)
* Requires the same number of columns and compatible data types

---

## 🔗 Types of UNION

### 1. UNION (Default)

* Removes duplicate rows
* Returns only unique results

```sql id="s3kz1n"
SELECT first_name, last_name
FROM employee_demographics
UNION
SELECT first_name, last_name
FROM employee_salary;
```
<img width="1525" height="824" alt="image" src="https://github.com/user-attachments/assets/1f5eb4d3-f35c-47f8-b827-1dfb22251bd2" />

---

### 2. UNION ALL

* Keeps all rows including duplicates
* Faster than UNION

```sql id="r6ghw1"
SELECT first_name, last_name
FROM employee_demographics
UNION ALL
SELECT first_name, last_name
FROM employee_salary;
```
<img width="1596" height="869" alt="image" src="https://github.com/user-attachments/assets/db90dfec-8022-46ce-9f24-4612b9030102" />

---

## ⚠️ Important Rule

All SELECT statements must:

* Have the same number of columns
* Have similar data types
* Be in the same order

❌ Incorrect example:

```sql id="mj8o1f"
SELECT age, gender
FROM employee_demographics
UNION
SELECT first_name, last_name
FROM employee_salary;
```
<img width="1691" height="966" alt="image" src="https://github.com/user-attachments/assets/8b896e2d-370a-4118-8933-4ec34a044b01" />

---

## 📊 Practical Use Case

### Labeling Employees

```sql id="u2t7fa"
SELECT first_name, last_name, 'old man' AS Label
FROM employee_demographics
WHERE age > 40 AND gender = 'male'

UNION

SELECT first_name, last_name, 'old lady' AS Label
FROM employee_demographics
WHERE age > 40 AND gender = 'female'

UNION

SELECT first_name, last_name, 'Highly paid Employee' AS Label
FROM employee_salary
WHERE salary > 70000

ORDER BY first_name, last_name;
```
<img width="1829" height="886" alt="image" src="https://github.com/user-attachments/assets/3ce30963-dfd7-42c4-81d0-b5ab73e32cbe" />

---

## 🧠 Summary

| Feature     | Description                             |
| ----------- | --------------------------------------- |
| UNION       | Combines results and removes duplicates |
| UNION ALL   | Combines results and keeps duplicates   |
| Requirement | Same columns and compatible data types  |

---

## 🚀 Author

WINNIE NGAMAU
