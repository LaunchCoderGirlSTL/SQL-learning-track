# Week 4 Problem Set Solutions

```
--Problem set

--1 A
SELECT ProductID, Name, Color, Size FROM Production.Product
WHERE Color IS NOT NULL;

--1 B
SELECT ProductID, Name, Color, Size
FROM Production.Product
WHERE Color IS NOT NULL AND Size IS NOT NULL;

--Alternate
SELECT ProductID, Name, Color, Size FROM Production.Product
WHERE Color + Size IS NOT NULL;

--1 C
SELECT ProductID, Name, Color, Size FROM Production.Product
WHERE Color IS NULL AND Size IS NULL;

--Alternate
SELECT ProductID, Name, Color, Size FROM Production.Product
WHERE COALESCE(Color,Size) IS NULL;

--1 D
SELECT ProductID, Name, Color, Size FROM Production.Product
WHERE Color IS NOT NULL OR Size IS NOT NULL;

--2 A
--Works since no time recorded
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE OrderDate BETWEEN '1/1/2011' AND '12/31/2011';

--Alternate (better!)
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE OrderDate >= '1/1/2011' AND OrderDate < '1/1/2012';

--Alternate (easy but sometime bad for performance) SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE YEAR(OrderDate) = 2011;

--2 B
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE OrderDate BETWEEN '1/1/2011' AND '12/31/2012';

--Alternate (better!)
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE OrderDate >= '1/1/2011' AND OrderDate < '1/1/2013';

--Alternate (easy but sometime bad for performance) SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE YEAR(OrderDate) IN (2011, 2012);

--2 C
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE CustomerID = 11001 AND
OrderDate BETWEEN '1/1/2014' AND '12/31/2014';

--Alternate (better!)
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE CustomerID = 11001 AND
OrderDate >= '1/1/2014' AND OrderDate < '1/1/2015';

--Alternate (easy but can cause performance problems) SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE CustomerID = 11001 AND YEAR(OrderDate) = 2014;

--2 D
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE CustomerID IN (11001,11002,11003);

--Alternate
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE CustomerID = 11001
OR CustomerID = 11002
OR CustomerID = 11003;

--Alternate, since there are no gaps
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE CustomerID BETWEEN 11001 AND 11003;

--2 E
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE TotalDue > 1000;

--2 F
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
WHERE TotalDue >= 1000;

--2 G
SELECT SalesOrderID, CustomerID, OrderDate,
TotalDue
FROM Sales.SalesOrderHeader
ORDER BY TotalDue DESC;

--3 A
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE FirstName LIKE 'K%';

--Alternate, but we haven't covered this yet SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE LEFT(FirstName,1) = 'K';

--3 B
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE FirstName LIKE '%z%'
OR MiddleName LIKE '%z%'
OR LastName LIKE '%z%';

--Alternate (we haven't covered this yet)
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE CONCAT(FirstName,MiddleName,LastName) LIKE '%z%';

--3 C
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE LastName = 'Morgan'
AND (FirstName = 'Abigail' OR FirstName = 'Alexandra');

--Alternate
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE LastName = 'Morgan'
AND FIRSTNAME IN ('Abigail','Alexandra');

--3 D
SELECT BusinessEntityID, FirstName, MiddleName, LastName,
FirstName + ' ' + ISNULL(MiddleName,'') + ' ' + LastName AS FullName FROM Person.Person;

--Alternate, removes the extra space when Middlename is null SELECT BusinessEntityID, FirstName, MiddleName, LastName,
FirstName + ISNULL(' ' + MiddleName,'') + ' ' + LastName AS FullName FROM Person.Person;

--3 F
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE FirstName > 'T';

--3 G
SELECT BusinessEntityID, FirstName, MiddleName,
LastName FROM Person.Person
WHERE EmailPromotion = 1;
```
