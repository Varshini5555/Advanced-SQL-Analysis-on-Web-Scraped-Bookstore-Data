# 📘 Advanced SQL Analysis on Web-Scraped Bookstore Data

This project demonstrates end-to-end data analysis using web scraping, data cleaning, SQL querying, and data visualization. The dataset was scraped from [Books to Scrape](http://books.toscrape.com/) and analyzed using MySQL to derive insights on book prices, ratings, and availability.

---

## 📌 Project Overview

- Scraped real-time book data (title, price, rating, availability) using Python and BeautifulSoup.
- Cleaned and exported the data to CSV.
- Imported structured data into MySQL database.
- Applied advanced SQL queries for exploratory and deep-dive analysis.
- Visualized key insights using Power BI.

---

## 🛠️ Technologies Used

- **Python (BeautifulSoup, Requests, Pandas)** — for scraping & preprocessing
- **MySQL (Workbench)** — for advanced querying and data manipulation
- **Power BI / Excel** — for data visualization

---

## 🧠 SQL Analysis Highlights

- Books with the **lowest price in each rating group**
- **Average book price** per rating
- Identification of **high-rated but low-priced books**
- Rating-wise **price distribution analysis**
- Filtering using **subqueries, aggregation, HAVING clauses, and window functions**

---

## 📈 Sample SQL Queries

```sql
-- Get the cheapest book per rating
SELECT title, price, rating
FROM books_clean b1
WHERE price = (
    SELECT MIN(price)
    FROM books_clean b2
    WHERE b2.rating = b1.rating
);
