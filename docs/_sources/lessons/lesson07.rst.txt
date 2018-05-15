Lesson 7: Advanced Report Features
==================================

Learning Objectives
-------------------

* Enable click-through (drill through) to another report
* Add headers and footers
* Use expressions in a report
* Sorting
* Calculated columns

Prep Work
---------

In-class Work
-------------

The `presentation <https://github.com/LaunchCoderGirlSTL/SQL-Materials/blob/master/Week%207/Advanced%20reports.pdf>`_ will cover advanced reports.

These example queries will help you during class::

  Sales report query
  SELECT T.[Group], T.Name AS Region, YEAR(OrderDate) AS OrderYear,
      Month(OrderDate) AS OrderMonth, OrderDate, SalesOrderID, TotalDue
  FROM Sales.SalesOrderHeader AS SOH
  JOIN Sales.SalesTerritory AS T ON SOH.TerritoryID = T.TerritoryID
  WHERE YEAR(OrderDate) = @Year;

  SELECT DISTINCT YEAR(OrderDate) AS OrderYear
  FROM Sales.SalesOrderHeader
  ORDER BY OrderYear DESC;

  Alternating color. Add to background property of row
  = IIf(RowNumber(Nothing) Mod 2 = 0, "Silver", "LightBlue")

  Change to italics if Canada. Add to Font --> Style property
  =IIf(Fields!Region.Value = "United Kingdom","Italic","Normal")


  --Product list query
  SELECT  P.ProductID, Name, ProductNumber, StandardCost, ListPrice
  FROM Production.Product AS P
  WHERE ListPrice > 0;

  Expression for Profit
  =Fields!ListPrice.Value-Fields!StandardCost.Value

  Expression for PercentMarkup
  =FormatPercent(Fields!Profit.Value/Fields!ListPrice.Value)

  Sales by Year and Month
  SELECT SUM(TotalDue) AS TotalSales, YEAR(OrderDate) AS OrderYear,
  	MONTH(OrderDate) AS OrderMonth
  FROM Sales.SalesOrderHeader
  GROUP BY YEAR(OrderDate), MONTH(OrderDate);

  Expression for month name
  =MonthName(Fields!OrderMonth.Value)

  Detail report
  SELECT SalesOrderID, OrderDate, TotalDue
  FROM Sales.SalesOrderHeader
  WHERE YEAR(OrderDate) = @Year AND MONTH(OrderDate) = @Month;

  Report title
  ="Sales for " + Parameters!Year.Value + " " + MonthName(Parameters!Month.Value)

  Sales Main query
  SELECT SalesOrderID, OrderDate, TotalDue
  FROM Sales.SalesOrderHeader
  WHERE OrderDate = '5/31/2011';

  Sales Subreport
  SELECT SalesOrderID, SOD.ProductID, Name, Color, Size
  FROM Sales.SalesOrderDetail AS SOD
  JOIN Production.Product AS PROD ON Sod.ProductID = PROD.ProductID
  WHERE SalesOrderID = @SalesOrderID;

Assignments
-----------

Read this `article <https://www.red-gate.com/simple-talk/sql/reporting-services/sql-server-reporting-services-basics-customizing-ssrs-reports/?utm_source=simpletalk&utm_medium=weblink&utm_content=ssrsbasics1>`_ about SSRS. Use the AdventureWorks2014 database for this quiz.
