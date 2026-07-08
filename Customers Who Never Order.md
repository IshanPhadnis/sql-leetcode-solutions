# 🧩 LeetCode SQL 50

## 📌 Problem Statement

Given two tables, **Customers** and **Orders**, identify all customers who have **never placed an order**.

This problem demonstrates the use of **LEFT JOIN** to find records that exist in one table but have no matching records in another table.

---

## Question

**Find all customers who never ordered anything.**

### Tables

#### Customers

| Column | Description               |
| ------ | ------------------------- |
| `id`   | Customer ID (Primary Key) |
| `name` | Customer Name             |

#### Orders

| Column       | Description                                          |
| ------------ | ---------------------------------------------------- |
| `id`         | Order ID (Primary Key)                               |
| `customerId` | Customer ID (Foreign Key referencing `Customers.id`) |

---

## 📖 Business Context

An e-commerce company wants to identify registered customers who have **never placed an order**. These customers can be targeted with onboarding campaigns, discount coupons, or personalized promotions to encourage their first purchase.

---

## ✅ Solution

```sql
SELECT
    c.name AS Customers
FROM Customers c
LEFT JOIN Orders o
    ON c.id = o.customerId
WHERE o.customerId IS NULL;
```

---

## 💡 Explanation

* `LEFT JOIN` returns **all customers** from the `Customers` table.
* Matching orders are retrieved from the `Orders` table.
* Customers with **no matching orders** have `NULL` values for the order columns.
* Filtering with `WHERE o.customerId IS NULL` returns only those customers who have **never placed an order**.

---

## 🧠 SQL Concepts Covered

* `LEFT JOIN`
* Foreign Keys
* Filtering with `NULL`
* Finding unmatched records

---

## 🎯 Skills Demonstrated

* SQL Joins
* Data Filtering
* Relational Database Concepts
* Business Problem Solving

---

⭐ **LeetCode Difficulty:** Easy
