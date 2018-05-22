# Week 12 Problem Set Part 2 Solutions

1. Write a query using the Production.Product table that returns the minimum, maximum, and average ListPrice for each product. Include the ProductID and Name in the results.

        SELECT MIN(ListPrice) AS MinPrice,
        MAX(ListPrice) AS MaxPrice,
        AVG(ListPrice) AS AvgPrice
        FROM Production.Product;

2. Write a query that returns the average freight for each TerritoryID in the Sales.SalesOrderHeader table.

        SELECT TerritoryID, AVG(Freight) AS AvgFreight
        FROM Sales.SalesOrderHeader
        GROUP BY TerritoryID;

3. Write a query that returns a count of detail lines in the Sales.SalesOrderDetail table for each SalesOrderID. Include only orders that have at least three detail lines.

        SELECT SalesOrderID, COUNT(*) CountOfDetails
        FROM Sales.SalesOrderDetail
        GROUP BY SalesOrderID
        HAVING COUNT(*) >= 3;

4. Write a query that groups the products by ProductModelID along with a count. Display the rows that have a count that equals 1.

        SELECT ProductModelID, COUNT(*) CountOfProducts
        FROM Production.Product
        GROUP BY ProductModelID
        HAVING COUNT(*) = 1;

5. Change the previous query so that only the products that are red or blue are included.

        SELECT ProductModelID, COUNT(*) CountOfProducts
        FROM Production.Product
        WHERE Color IN ('Red','Blue')
        GROUP BY ProductModelID
        HAVING COUNT(*) = 1;

6. Write a query joining the Person.Person, Sales.Customer, and Sales.SalesOrderHeader table. Return a list of the customers with their names and the count of orders each one has placed.

        SELECT Cust.CustomerID, Pers.FirstName, Pers.LastName,
        COUNT(*) AS CountOfSales
        FROM Person.Person AS Pers
        INNER JOIN Sales.Customer AS Cust ON Pers.BusinessEntityID = Cust.CustomerID
        INNER JOIN Sales.SalesOrderHeader AS SOH ON Cust.CustomerID = SOH.CustomerID
        GROUP BY Cust.CustomerID, Pers.FirstName, Pers.LastName;
