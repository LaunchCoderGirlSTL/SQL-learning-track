Lesson 6: Using Parameters in Reports
=====================================

Learning Objectives
-------------------

* Create reports that use parameters to make the report dynamic
* Use a dataset to create a list for a parameter
* Learn how to create cascading parameters
* Change a property based on a parameter (color)

Prep Work
---------

In-class Work
-------------
Some queries for examples::

  --A list of sales
  SELECT SalesOrderID, CustomerID, OrderDate, TotalDue
  FROM Sales.SalesOrderHeader;

  --Add a parameter
  SELECT SalesOrderID, CustomerID, OrderDate, TotalDue
  FROM Sales.SalesOrderHeader
  WHERE YEAR(OrderDate) = @year;

  --Parameter list
  SELECT DISTINCT YEAR(OrderDate) AS OrderYear
  FROM Sales.SalesOrderHeader
  ORDER BY OrderYear;


  --Products
  SELECT ProductID, Name, ProductSubcategoryID
  FROM Production.Product;

  --Add parameter
  SELECT ProductID, Name, ProductSubcategoryID
  FROM Production.Product
  WHERE ProductSubcategoryID = @ProductSubCategoryID;

  --List of subcategories
  SELECT ProductSubCategoryID, Name
  FROM Production.ProductSubcategory
  ORDER BY Name;

  --List of categories
  SELECT ProductCategoryID, Name
  FROM Production.ProductCategory
  ORDER BY Name;

The `presentation <https://github.com/LaunchCoderGirlSTL/SQL-Materials/blob/master/Week%206/Parameters.pdf>`_ this week is on SSRS Parameters.

Assignments
-----------

Read this `article <https://www.red-gate.com/simple-talk/sql/reporting-services/sql-server-reporting-services-basics-building-ssrs-reports>`_ starting from the "Adding parameters to a report" section.
