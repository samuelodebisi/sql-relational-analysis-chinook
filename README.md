# Chinook Music Store SQL Analysis 🎵📊

This project analyzes the Chinook music store database using SQL to uncover insights about sales trends, customer behavior, artist inventory, and employee performance. The goal is to demonstrate relational database querying skills and communicate findings through data visualizations.

## 📁 Project Overview

The Chinook database represents a digital media store, including information about:
- Music tracks, genres, albums, and artists
- Customers, invoices, and invoice items
- Employees and their customer support assignments

Using SQL, I explored key business questions and visualized the results to aid strategic decisions.

## 🔍 Key Questions Answered

1. **What are the top 5 selling genres by number of tracks sold?**
2. **Who are the top 5 customers by total spending?**
3. **Which artists have the most tracks in the store?**
4. **Which employees have sold the most tracks?**

Each of these questions is backed by SQL queries and visualizations to support data-driven storytelling.

## 🛠️ Tools Used

- SQL (SQLite/PostgreSQL)
- DB Browser for SQLite
- Google Slides (for presentation)
- Google Sheets (for basic visualizations)

## 🧾 SQL Highlights

```sql
-- Top 5 selling genres
SELECT g.Name AS Genre, SUM(il.Quantity) AS Tracks_Sold
FROM InvoiceLine il
JOIN Track t ON il.TrackId = t.TrackId
JOIN Genre g ON t.GenreId = g.GenreId
GROUP BY g.Name
ORDER BY Tracks_Sold DESC
LIMIT 5;

