Week 17 Problem Set
===================

There is a lot to learn when querying data, but you may also need to modify data as well. This is especially true if you develop T-SQL code for an application, not just for reports. To avoid messing up your copy of AdventureWorks, this section starts with creating temporary tables. Temporary tables are stored in a special system database called Tempdb. They last as long as the connection that created them is open or until they are purposefully dropped.
There are three things you can do to manipulate data: insert new rows, modify existing rows, or delete existing rows.

Exercise 1
----------

1. Create a copy of the Sales.SalesOrderHeader table into a temp table called #Sales and populate it with data in one step. Include only the SalesOrderID, OrderDate, TotalDue, and CustomerID columns.
2. Create a temp table called #Customers. It must have a CustomerID. It must also have a FirstName and LastName column. Figure out which data types are needed by looking at the Person.Person and Sales.Customer tables. Make the CustomerID a primary key.

Exercise 2
----------

1. Write a query to populate the #Customers table. You will need to join the Person.Person and Sales.Customer tables. The PersonID will join to the BusinessEntityID. Be sure to run the query to populate the #Customers table.
2. Add three new customers to the #Customers table. They can be any names you wish, but make sure that you do not duplicate the CustomerID column.
3. Add an order for each of the new customers you added in 2.2. Make sure you do not duplicate existing SalesOrderID values. You can choose any date and total due you wish.

Exercise 3
----------

1. Modify the #Sales rows so that every order below $10 is changed to $10.
2. You can also use existing columns to modify data. Write a query that adds one day to every OrderDate in the #Sales table. Use the DATEADD function.
3. Delete any rows where the order was placed in 2011.

Resources
---------

Please use the following resources for assistance with the problem set.

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers12
