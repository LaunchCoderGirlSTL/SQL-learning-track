Week 4 Problem Set
==================

Use the AdventureWorks2014 database

1. Write a query that returns the ProductID, Name, Color, and Size from the Production.Products table.

  a. Only if there is a color filled in
  b. Only if both the color and size are filled in
  c. Only if color and size are not filled in
  d. If at least one of them (color or size) is filled in

2. Write a query that returns SalesOrderID, CustomerID, OrderDate and TotalDue from the Sales.SalesOrderHeader table.

  a. For orders placed in 2011
  b. For orders placed in 2011 and 2012
  c. For CustomerID 11001 and orders placed in 2014
  d. For CustomerID 11001, 11002, and 11003
  e. For orders that have a TotalDue more than $1000
  f. For orders that have a TotalDue at least $1000
  g. Displaying the highest TotalDue first

3. Write a query that returns the BusinessEntityID, FirstName, MiddleName, LastName from the Person.Person table

  a. With a FirstName starting with K.
  b. With z anywhere in their name (first, middle or last)
  c. With a LastName of Morgan and the FirstName of Abigail or Alexandra
  d. With the FirstName, MiddleName, and LastName combined to make a FullName column.
  e. With all the FirstName values starting with T to the end of the list
  f. Only the rows in the email promotion list

Resources
---------

After you complete the problem set, you may find the following resources helpful to figure out what you got right and wrong and why!

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers04
