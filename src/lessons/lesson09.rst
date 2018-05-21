Lesson 9: UNION and IN Subqueries
=================================

Learning Objectives
-------------------

* Write queries that use ``UNION``, ``UNION ALL``, ``EXCEPT`` or ``INTERSECT``
* Write queries that use a subquery in the ``WHERE`` clause using ``IN``
* Understand the difference between ``UNION``, ``UNION ALL``, ``EXCEPT`` and ``INTERSECT``

Prep Work
---------
The join examples from Lesson 8 will be helpful with Lesson 9::

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
  ORDER BY SOH.SalesOrderID;


In-class Work
-------------

Assignments
-----------

Read Chapter 6 of Zero to Hero

Watch videos from Week 8

Use the Northwind database for this quiz.

.. toctree::
   :maxdepth: 1

   assignments/problemset06
