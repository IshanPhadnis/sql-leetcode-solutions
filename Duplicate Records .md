# 🧩 LeetCode SQL 50

## 📌 Problem Statement

Given a table containing email addresses, identify all **duplicate email addresses**.

Each email is guaranteed to be non-NULL, and duplicate emails should be returned only once.

---

## Question

**Report all duplicate email addresses.**

### Table: `Person`

| Column  | Description                     |
| ------- | ------------------------------- |
| `id`    | Unique identifier (Primary Key) |
| `email` | Email address                   |

---

## 📖 Business Context

Duplicate customer records are a common data quality issue in CRM and e-commerce systems. Identifying duplicate email addresses helps organizations:

* Remove duplicate customer accounts
* Improve marketing campaign accuracy
* Maintain clean customer databases
* Prevent duplicate communications

---

## ✅ Solution

```sql
SELECT
    email
FROM Person
GROUP BY email
HAVING COUNT(*) > 1;
```

---

## 💡 Explanation

* `GROUP BY email` groups all identical email addresses together.
* `COUNT(*)` counts how many times each email appears.
* `HAVING COUNT(*) > 1` filters only those groups where an email appears more than once.

---

## 🧠 SQL Concepts Covered

* `GROUP BY`
* `HAVING`
* Aggregate Functions
* `COUNT()`

---

## 🎯 Skills Demonstrated

* Data Cleaning
* Duplicate Detection
* SQL Aggregations
* Business Data Validation

---

⭐ **LeetCode Difficulty:** Easy

