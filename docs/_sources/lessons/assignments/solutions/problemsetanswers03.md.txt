# Week 3 Problem Set Solutions

```
USE AdventureWorks2014
GO

 --1
 SELECT DISTINCT JobTitle
 FROM HumanResources.Employee

 --2
 SELECT *
 FROM Person.ContactType
 WHERE Name LIKE '%Manager%'

 --3
 SELECT *
 FROM Person.ContactType
 WHERE Name LIKE '%Market%'
 AND Name LIKE '%Manager%'

 --4
 SELECT *
 FROM Person.ContactType
 WHERE Name NOT LIKE '%Market%'
 AND Name NOT LIKE '%Manager%'

 --5
 SELECT *
 FROM Person.StateProvince
 WHERE Name LIKE 'Al%'
 AND CountryRegionCode NOT LIKE 'FR'

 --6
 SELECT *
 FROM Person.Person
 WHERE (FirstName LIKE 'X%'
 AND LastName LIKE 'W%'
 AND EmailPromotion > 0 )
 OR FirstName LIKE 'Q%'

 --7
 SELECT *
 FROM Person.Person
 WHERE (FirstName LIKE 'Pat%' AND PersonType = 'SC')
 OR BusinessEntityID < 10

 --8
 SELECT *
 FROM Person.Person
 WHERE Suffix IS NOT NULL
 AND Title IS NULL

 --9
 SELECT *
 FROM Sales.SalesPerson
 WHERE (Bonus > 4000 OR SalesYTD > 300000)
 AND CommissionPct >= .015

 --10
 SELECT *
 FROM sales.SalesPerson
 WHERE (SalesQuota < 300000 OR SalesQuota IS NULL)
 AND Bonus < 2500
 
 --11
 SELECT *
 FROM Production.Product
 WHERE (SafetyStockLevel < 10 AND Color IS NULL)
 AND (Name LIKE '%Pump' OR Name LIKE '%cage')
 ```
