# Week 9 Problem Set Solutions

## Exercise 1

```
 -- All Products and Categories, ordered by Category then Product
 SELECT c.CategoryName, p.ProductName
 FROM Products p
 INNER JOIN Categories c ON p.CategoryID = c.CategoryID
 ORDER BY c.CategoryName, p.ProductName
 -- All Products and Suppliers, ordered by Company then Product
 SELECT s.CompanyName, p.ProductName
 FROM Products p
 INNER JOIN Suppliers s ON p.SupplierID = s.SupplierID
 ORDER BY s.CompanyName, p.ProductName
-- All Employees by Territory, ordered Employee Last Name then Territory
--   (Hint, use EmployeeTerritories table to get from Employees to Territories)
SELECT e.FirstName, e.LastName, t.TerritoryDescription
FROM Employees e
INNER JOIN EmployeeTerritories et ON e.EmployeeID = et.EmployeeID
INNER JOIN Territories t ON et.TerritoryID = t.TerritoryID
ORDER BY e.LastName, t.TerritoryDescription
 -- All Territories by Region, ordered by Region then Territory
 SELECT r.RegionDescription, t.TerritoryDescription
 FROM Region r
 INNER JOIN Territories t ON r.RegionID = t.RegionID
 ORDER BY r.RegionDescription, t.TerritoryDescription
-- All Employees by Region AND Territory, ordered by Region, then Territory, then Last
Name
SELECT r.RegionDescription, t.TerritoryDescription, e.FirstName, e.LastName
FROM Employees e
INNER JOIN EmployeeTerritories et ON e.EmployeeID = et.EmployeeID
INNER JOIN Territories t ON et.TerritoryID = t.TerritoryID
INNER JOIN Region r ON t.RegionID = r.RegionID
ORDER BY r.RegionDescription, t.TerritoryDescription, e.LastName
 -- Show OrderID, OrderDate and ProductIDs for OrderID 10248
 SELECT o.OrderID, o.OrderDate, od.ProductID
 FROM Orders o
 INNER JOIN [Order Details] od ON o.OrderID = od.OrderID
 WHERE o.OrderID = 10248
-- Show Customer (Company) Name, Order Date, Product Name, Product Category, Unit Price
and Quantity for OrderID 10248
SELECT c.CompanyName, o.OrderDate, p.ProductName, cg.CategoryName, od.UnitPrice,
od.Quantity
FROM Orders o
INNER JOIN [Order Details] od ON o.OrderID = od.OrderID
INNER JOIN Customers c ON o.CustomerID = c.CustomerID
INNER JOIN Products p ON od.ProductID = p.ProductID
INNER JOIN Categories cg ON p.CategoryID = cg.CategoryID
WHERE o.OrderID = 10248
```

## Exercise 2

```
 -- List Products and Product Numbers.  Include Product Reviews where applicable.
 SELECT p.Name, p.ProductNumber, pr.Comments
 FROM Production.Product p
 LEFT JOIN [Production].[ProductReview] pr ON p.ProductID = pr.ProductID
 -- List all Products with Product Numbers.  Include Product Subcategory where applicable.
 SELECT p.Name AS ProductName, p.ProductNumber, psc.Name AS ProductSubCategory
 FROM Production.Product p
 LEFT JOIN Production.ProductSubcategory psc ON p.ProductSubcategoryID =
 psc.ProductSubcategoryID
-- List all Products with Product Numbers.  Include Product Category AND Subcategory
where applicable.
SELECT p.Name AS ProductName, p.ProductNumber, psc.Name AS ProductSubCategory, pc.Name AS
ProductCategory
FROM Production.Product p
LEFT JOIN Production.ProductSubcategory psc ON p.ProductSubcategoryID =
psc.ProductSubcategoryID
LEFT JOIN Production.ProductCategory pc ON psc.ProductCategoryID = pc.ProductCategoryID
 -- List all Products with Product Numbers.  Include Product Model were applicable.
 SELECT p.Name AS ProductName, p.ProductNumber, pm.Name AS ProductModel
 FROM Production.Product p
 LEFT JOIN Production.ProductModel pm ON p.ProductModelID = pm.ProductModelID
-- List all Products with Product Numbers.  Include Product Subcategory, Product Category
AND Product Model where applicable.
SELECT p.Name AS ProductName, p.ProductNumber, psc.Name AS ProductSubCategory, pc.Name AS
ProductCategory
, pm.Name AS ProductModel
FROM Production.Product p
LEFT JOIN Production.ProductSubcategory psc ON p.ProductSubcategoryID =
psc.ProductSubcategoryID
LEFT JOIN Production.ProductCategory pc ON psc.ProductCategoryID = pc.ProductCategoryID
LEFT JOIN Production.ProductModel pm ON p.ProductModelID = pm.ProductModelID
```
