## 🟢 1. Basic SELECT & Filtering

Learn how to retrieve and filter data.

**Tasks**

1. List all customers with their city and country.
2. Show all products with price > 20.
3. Find customers located in Germany.
4. Show the top 10 most expensive products.

**Skills**

* `SELECT`
* `WHERE`
* `LIMIT`
* Comparison operators

---

## 🟢 2. Sorting & Text Search

Control result order and search strings.

**Tasks**

1. List products sorted by price (highest first).
2. Show customers sorted by country, then city.
3. Find products containing “cheese” in the name.
4. Get customers whose company name starts with “A”.

**Skills**

* `ORDER BY`
* `LIKE`
* Multiple sorting columns

---

## 🟢 3. Aggregations (Core SQL Skill 🔥)

Understand summaries and statistics.

**Tasks**

1. Count total number of customers.
2. Find average product price.
3. Get the cheapest and most expensive product.
4. Count how many orders exist.
5. Get total number of products per category.

**Skills**

* `COUNT()`
* `AVG()`
* `MIN()`, `MAX()`
* `GROUP BY`

---

## 🟢 4. GROUP BY + HAVING (Important)

Filter grouped data.

**Tasks**

1. Show categories with more than 5 products.
2. Find customers who made more than 10 orders.
3. Get countries with more than 5 customers.

**Skills**

* `HAVING`
* Group filtering vs `WHERE`

---

## 🟡 5. Joins (Most Important SQL Skill ⭐)

Northwind shines here.

### 5.1 Inner Joins

**Tasks**

1. Show orders with customer names.
2. List products with their category names.
3. Show orders with employee who handled them.

**Skills**

* `INNER JOIN`
* Foreign keys

---

### 5.2 Multiple Joins

**Tasks**

1. Show order details:

   * Customer name
   * Employee name
   * Order date
2. List products with:

   * Category
   * Supplier

---

### 5.3 LEFT JOIN

**Tasks**

1. Show all customers and their orders (including those with none).
2. Find customers who never ordered anything.

**Skills**

* `LEFT JOIN`
* `IS NULL`

---

## 🟡 6. Calculations & Expressions

Learn computed columns.

**Tasks**

1. Show product price with 25% VAT added.
2. Calculate total price per order line (`UnitPrice * Quantity`).
3. Add a column: “expensive” if price > 50.

**Skills**

* Arithmetic
* `AS`
* `CASE WHEN`

---

## 🟡 7. Subqueries (Very Important)

Think in nested queries.

### 7.1 Simple Subqueries

**Tasks**

1. Find products more expensive than the average price.
2. Get customers who made at least one order.

---

### 7.2 Correlated Subqueries

**Tasks**

1. Customers with more orders than average customer.
2. Most expensive product in each category.

---

## 🟡 8. Many-to-Many Relationships

Northwind has a classic: Orders ↔ Products via OrderDetails.

**Tasks**

1. List products in order #10248.
2. Find total price of order #10248.
3. Show top 5 most sold products.

**Skills**

* Bridge tables
* Aggregation across joins

---

## 🟠 9. Window Functions (If SQLite ≥ 3.25)

Modern SQL skill.

**Tasks**

1. Rank products by price within each category.
2. Running total of sales by order date.
3. Top 3 most expensive products per category.

**Skills**

* `ROW_NUMBER()`
* `RANK()`
* `PARTITION BY`

---

## 🟠 10. Date Queries

Real-world essential.

**Tasks**

1. Orders placed in 1997.
2. Orders in the last 30 days (relative query).
3. Count orders per year.

**Skills**

* Date filtering
* SQLite date functions (`strftime`)

---

## 🔴 11. Real Business Questions (Advanced Practice)

Think like an analyst.

**Tasks**

1. Top 5 customers by total spending.
2. Best-selling category.
3. Employee with highest sales.
4. Monthly revenue trend.
5. Products that never sold.

---

## 🧠 12. Data Cleaning Queries (Real-world skill)

Often overlooked but critical.

**Tasks**

1. Find duplicate company names.
2. Customers missing region.
3. Products with null supplier.

**Skills**

* `NULL` handling
* Data quality checks

---

## 🧪 Bonus Challenges (Interview-Level)

Try these when comfortable:

1. Cohort analysis: first order per customer.
2. Customer lifetime value.
3. Most popular product per country.
4. Median product price.
5. Detect seasonal sales patterns.