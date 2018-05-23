Week 16 Problem Set
===================

Create and test the objects. Be sure to include drop statements. Use the AdventureWorks2014 database for these questions.

NOTE: There is no one correct answer for these. Answers given are just suggestions.

1. Write a scalar function that returns the result of two integers multiplied together.
2. SQL Server 2016 and earlier has RTRIM and LTRIM functions which remove extra spaces from the right or left of a string respectively. Starting with SQL Server 2017, there is a new TRIM function which removes spaces from both sides. You are using SQL Server 2016, so create a scalar function called dbo.udf_Trim that has the functionality of the new TRIM function. It should be able to remove the spaces on either side of a 1000 character string.
3. Create a view for the following query:

  ``SELECT Cust.StoreID, Store.Name, YEAR(OrderDate) AS OrderYear, SUM(TotalDue) AS TotalSales``
  ``FROM Sales.Store AS Store``
  ``INNER JOIN Sales.Customer AS Cust ON Store.BusinessEntityID = Cust.StoreID``
  ``INNER JOIN Sales.SalesOrderHeader AS SOH ON SOH.CustomerID = Cust.CustomerID``
  ``GROUP BY Cust.StoreID, Store.Name, YEAR(OrderDate);``

4. Add a WHERE clause to the query from question 4 so that it is filtered by StoreID Create an Inline table-valued function using the new query. Make sure that it has the @StoreID parameter.
5. Add a WHERE clause to the query from question 4 so that it is filtered by StoreID Create an Inline table-valued function using the new query. Make sure that it has the @StoreID parameter.
6. Create a stored procedure using the query from question 5.

Resources
---------

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers11
