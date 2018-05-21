Lesson 8: Joining Tables
========================

Learning Objectives
-------------------

* Write queries that use ``INNER JOIN`` to join two or more tables in one query
* Write queries that use ``LEFT OUTER JOIN`` to join two or more tables in one query
* Use all query features, such as aliases, expressions, and ordering when joining tables
* Understand why ``INNER`` and ``OUTER`` joins are different

Prep Work
---------

In-class Work
-------------
The following examples of joins can be really helpful with understanding the work we did in class and the homework::

  SELECT Cust.CustomerID, Cust.AccountNumber, Cust.StoreID,
  	Pers.FirstName, Pers.LastName,
  	SOH.SalesOrderID, SOH.OrderDate, SOD.ProductID, SOD.OrderQty,
  	Prod.Name, Prod.Color, Prod.Size
  FROM Sales.Customer AS Cust
  INNER JOIN Sales.SalesOrderHeader AS SOH ON Cust.CustomerID = SOH.CustomerID
  INNER JOIN Sales.SalesOrderDetail AS SOD ON SOD.SalesOrderID = SOH.SalesOrderID
  INNER JOIN Production.Product AS Prod ON Prod.ProductID = SOD.ProductID
  INNER JOIN Person.Person AS Pers ON Pers.BusinessEntityID = Cust.PersonID
  ORDER BY Cust.CustomerID, SOH.SalesOrderID;



  --19820
  SELECT *
  FROM Sales.Customer;

  --19119
  SELECT distinct CustomerID
  FROM Sales.SalesOrderHeader;

  SELECT Cust.CustomerID, Cust.AccountNumber, Cust.StoreID,
  	SOH.SalesOrderID, SOH.OrderDate
  FROM Sales.Customer AS Cust
  LEFT JOIN Sales.SalesOrderHeader AS SOH ON Cust.CustomerID = SOH.CustomerID
  ORDER BY SOH.SalesOrderID;

  SELECT Cust.CustomerID, Cust.AccountNumber, Cust.StoreID,
  	SOH.SalesOrderID, SOH.OrderDate , SOD.ProductID, SOD.OrderQty,
  	PROD.Name, Prod.Color, Prod.Size
  FROM Sales.Customer AS Cust
  LEFT JOIN Sales.SalesOrderHeader AS SOH ON Cust.CustomerID = SOH.CustomerID
  LEFT JOIN Sales.SalesOrderDetail AS SOD ON SOD.SalesOrderID = SOH.SalesOrderID
  LEFT JOIN Production.Product AS Prod ON SOD.ProductID = Prod.ProductID
  ORDER BY SOH.SalesOrderID;

  SELECT Cust.CustomerID, Cust.AccountNumber, Cust.StoreID,
  	SOH.SalesOrderID, SOH.OrderDate , SOD.ProductID, SOD.OrderQty,
  	PROD.Name, Prod.Color, Prod.Size
  FROM Sales.Customer AS Cust
  LEFT JOIN Sales.SalesOrderHeader AS SOH ON Cust.CustomerID = SOH.CustomerID
  LEFT JOIN Sales.SalesOrderDetail AS SOD ON SOD.SalesOrderID = SOH.SalesOrderID
  LEFT JOIN Production.Product AS Prod ON SOD.ProductID = Prod.ProductID AND Prod.Color = 'Silver'
  ORDER BY SOH.SalesOrderID;]]


Assignments
-----------

Read Chapter 6 of Zero to SQL and watch the videos about joining.

Do the problem set if you can.

There are no real problems in this quiz, just a check to see if you have done the things listed.

.. toctree::
   :maxdepth: 1

   assignments/problemset05
