Lesson 13: Deploying SSRS Reports
=================================

Learning Objectives
-------------------

* Understand how to use the SSRS Web Portal
* Deploy reports to the SSRS Web Portal
* Run reports from the portal

Prep Work
---------

In-class Work
-------------
The following code sample will be of assistance in class::

  SELECT YEAR(SOH.OrderDate) AS OrderYear, Cust.CustomerID,
  	SUM(SOH.TotalDue) AS Sales,
  	Ter.TerritoryID, Ter.Name AS TerritoryName, s.Name AS Storename
  FROM Sales.SalesOrderHeader AS SOH
  INNER JOIN Sales.SalesTerritory AS Ter ON SOH.TerritoryID = Ter.TerritoryID
  INNER JOIN Sales.Customer AS Cust ON Cust.CustomerID = SOH.CustomerID
  INNER JOIN Sales.Store AS S ON s.BusinessEntityID = Cust.StoreID
  GROUP BY Cust.CustomerID, Ter.TerritoryID, Ter.Name,
  	YEAR(OrderDate), S.Name;

The presentation will be covering `SSRS and Grouping Reports <https://github.com/LaunchCoderGirlSTL/SQL-Materials/blob/master/Week%2013/SSRS%20Grouping.pdf/>`_.

Assignments
-----------

Take a look at the second `SSRS article <https://www.red-gate.com/simple-talk/sql/reporting-services/sql-server-reporting-services-basics-customizing-ssrs-reports/>`_ starting with the Grouping section.

Create the required reports using the AdventureWorks2014 database. Run the report and export as PDF files. Upload the PDF in Canvas. IMPORTANT: make sure that your report fits on the page!!
The reports can be found in the `Github repository <https://github.com/LaunchCoderGirlSTL/SQL-Materials/tree/master/Week%2013/Report%20Project9/>`_.
