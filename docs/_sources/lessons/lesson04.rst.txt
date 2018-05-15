Lesson 4: Filtering and Ordering Data
=====================================

Learning Objectives
-------------------

* Write queries the ``WHERE`` clause to filter the results
* Understand how to work with ``NULL`` values in the ``SELECT`` and ``WHERE`` clauses
* Use the ``ISNULL`` and ``COALESCE`` functions
* Use several operators and techniques to filter data

  * ``BETWEEN``
  * ``LIKE``
  * ``<,>,<>,=``
  * ``NOT``
  * ``OR``
  * ``Parentheses``

* Use the ``ORDER BY`` clause to sort the results of a query

  * ``ASC``
  * ``DESC``

* Use aliases for column names when needed

Prep Work
---------

In-class Work
-------------
The `presentation <https://github.com/LaunchCoderGirlSTL/SQL-Materials/blob/master/Week%204/SSRS.pdf>`_ from class on SSRS can be helpful for the assignment this week.

See if you can figure out which rows will be returned from each WHERE clause::

  SELECT [AddressTypeID]
        ,[Name]
        ,[rowguid]
        ,[ModifiedDate]
    FROM [AdventureWorks2014].[Person].[AddressType]

  ORDER BY Name;
     WHERE Name LIKE ‘B%’
     WHERE Name NOT LIKE ‘B%’
     WHERE Name LIKE ‘%B%’
     WHERE Name LIKE ‘%pp%’
     WHERE Name LIKE ‘%g’
     WHERE Name LIKE ‘H%e%’
     WHERE Name >= ‘Ma’
     WHERE Name > ‘B’
     WHERE Name < ‘H’
     WHERE AddressTypeID BETWEEN 1 AND 3
     WHERE Name BETWEEN ‘A’ AND ‘B’
     WHERE Name BETWEEN ‘A’ AND ‘Bi’
     WHERE Name BETWEEN ‘A’ AND ‘Bu’
     WHERE AddressTypeID IN (1,2,3)
     WHERE Name IN (‘Shipping’,’Home’)
     WHERE Name NOT IN (‘Shipping’,’Home’)
     WHERE Name = ‘Shipping’ AND AddressTypeID = 1 WHERE Name = ‘Shipping’ OR AddressTypeID = 1

    USE Northwind;
    GO
    --This is code to create the temp table. Just run it once
    SELECT TOP (10) [OrderID]
                   ,[CustomerID]
                   ,[EmployeeID]
                   ,[OrderDate]
                   ,[Freight]
                   ,[ShipRegion]
                   ,[ShipPostalCode]
                   ,[ShipCountry]
    INTO #Order
        FROM dbo.Orders;
    --Code to select from the temp table
    SELECT * FROM #Order
      WHERE ShipRegion = NULL
      WHERE ShipRegion IS NULL
      WHERE ShipRegion <> ‘RJ’
      WHERE ShipRegion IS NOT NULL OR ShipRegion <> ‘RJ’ WHERE ISNULL(ShipRegion, ‘’) <> ‘RJ’
      WHERE COALESCE(ShipRegion,’’) <> ‘RJ’ WHERE Freight BETWEEN 22 AND 32 WHERE OrderDate = 1996-07-05

Assignments
-----------

No quiz this week, but there will be a written test in class next class.

* STUDY ``SELECT`` ``WHERE`` ``ORDER`` ``BY``
* STUDY database design

We will complete another problem set. If you need to practice using ``WHERE``, refer to the problem set from last week

.. toctree::
   :maxdepth: 1

   assignments/problemset03
   assignments/problemset04

See if you can create the wizard report. Here is query you will need::

  SELECT T.[Group], T.Name AS Region, YEAR(OrderDate) AS OrderYear,
      Month(OrderDate) AS OrderMonth, OrderDate, SalesOrderID, TotalDue
  FROM Sales.SalesOrderHeader AS SOH
  JOIN Sales.SalesTerritory AS T ON SOH.TerritoryID = T.TerritoryID;
