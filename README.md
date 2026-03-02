# SQL-Project-On-Online-Book-Store

1. Top Selling Books 📚
   SELECT 
    b.Title, 
    SUM(o.Quantity) AS Total_Units_Sold
FROM Books b
JOIN Orders o ON b.Book_ID = o.Book_ID
GROUP BY b.Title
ORDER BY Total_Units_Sold DESC
LIMIT 5;

2. Revenue by Genre 💰
   SELECT 
    b.Genre, 
    SUM(o.Total_Amount) AS Total_Revenue
FROM Books b
JOIN Orders o ON b.Book_ID = o.Book_ID
GROUP BY b.Genre
ORDER BY Total_Revenue DESC;

3. High-Value Customers ⭐
  SELECT 
    c.Name, 
    SUM(o.Total_Amount) AS Total_Spent
FROM Customers c
JOIN Orders o ON c.Customer_ID = o.Customer_ID
GROUP BY c.Name
HAVING SUM(o.Total_Amount) > 100
ORDER BY Total_Spent DESC;

4. Stock Management (Low Stock Alert) ⚠️
   SELECT Title, Stock 
FROM Books 
WHERE Stock < 10;


* Project Goal: "The goal of this project is to manage a relational database for an online bookstore, tracking everything from inventory to customer orders."
* Tool: pgAdmin
* SQL Dialect: PostgreSQL
