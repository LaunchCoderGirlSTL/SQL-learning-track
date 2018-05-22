# Week 12 Problem Set Part 1 Solutions

```
-- What is the most common first letter of a last name in the Person table?  How many people with that letter?
-- How many people have a last name that starts with F?
SELECT LEFT(LastName, 1), COUNT(*)
FROM Person.Person
GROUP BY LEFT(LastName, 1)
ORDER BY COUNT(*) DESC

-- Using the SalesOrderHeader table, what is the total Tax Amount collected on 8/31/2011
SELECT OrderDate, SUM(TaxAmt), COUNT(*)
FROM Sales.SalesOrderHeader soh
GROUP BY OrderDate
ORDER BY OrderDate

-- show the account number, first name, last name and sum of totaldue for any account that has spent more than 900,000
-- ordered from highest sum to lowest sum
-- HINT, use SalesOrderHeader, Customer and Person tables
SELECT c.AccountNumber, FirstName, LastName, SUM(soh.totaldue)
FROM sales.SalesOrderHeader soh
INNER JOIN sales.Customer c on soh.CustomerID = c.CustomerID
INNER JOIN Person.Person p on c.PersonID = p.BusinessEntityID
GROUP BY c.AccountNumber, FirstName, LastName
HAVING SUM(soh.totaldue) > 900000

-- Which First Letter of LastName has spent the most (total due from SalesOrderHeader)?
-- Which First Letter of LastName has spent the least (non-zero total due from SalesOrderHeader)?
SELECT LEFT(LastName,1), SUM(soh.totaldue)
FROM sales.SalesOrderHeader soh
INNER JOIN sales.Customer c on soh.CustomerID = c.CustomerID
INNER JOIN Person.Person p on c.PersonID = p.BusinessEntityID
GROUP BY LEFT(LastName,1)
ORDER BY SUM(soh.totaldue) desc

--Which year has the highest totaldue amount (based on Order Date)?
SELECT YEAR(OrderDate), SUM(soh.totaldue)
FROM sales.SalesOrderHeader soh
GROUP BY YEAR(OrderDate)
ORDER BY SUM(soh.totaldue) desc

--Which month/year has the highest total due amount (based on Order Date)?
SELECT YEAR(OrderDate), MONTH(OrderDate), SUM(soh.totaldue)
FROM sales.SalesOrderHeader soh
GROUP BY YEAR(OrderDate), MONTH(OrderDate)
ORDER BY SUM(soh.totaldue) desc

-- How many customers are there that do not have anything in the SalesOrderHeader table?
SELECT COUNT(*)
FROM sales.Customer c
WHERE c.CustomerID NOT IN (
	SELECT CustomerID
	FROM sales.SalesOrderHeader soh)
```
