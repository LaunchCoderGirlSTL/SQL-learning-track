Week 8 Problem Set
==================

Most of the time when on the job, you will not write queries for just one table; your queries will join two or more tables together. Two tables can be joined together by using the ``INNER JOIN`` or ``OUTER JOIN`` syntax and a join condition. The join condition is an expression that returns true or false, and it’s usually a column from one table equal to a column from the other table. It is often the foreign key column from one table and the primary key column from the other table. SQL Server does not enforce this, however. The join condition can be any expression that returns true or false as long as the data types are compatible.
You may be wondering how you will know which columns to include in the join condition. It depends on the situation. If you are lucky, primary and foreign keys will be defined on the tables. Often, you just have to understand the data to figure it out. Since SQL Server does not keep you from making a mistake, you will probably want to use the TOP keyword to restrict the number of rows returned while you are developing.
To prepare for this problem set, be sure to watch the videos on ``INNER JOIN`` and ``OUTER JOIN``.

Exercise 1
----------

1. Write a query that returns the JobTitle, Birtdate, first and last names. Join the HumanResources.Employee table to the Person.Person table. In this case, you can join on the BusinessEntityID column from both tables.
2. Customers can be joined to the Person table by the PersonID from the Sales.Customer table to the BuisinessEntityID from the Person.Person table. Join the tables and return the CustomerID, TerritoryID, first, last and middle names.
3. Join the Sales.SalesOrderDetail table to the Production.Product table on ProductID. Return a list containing the SalesOrderID, ProductID, OrderQty, and product name.
4. Join the HumanResources.JobCandidate table to the Person.Person table by BusinessEntityID. Return the first, middle and last names along with the JobCandidateID column.

Exercise 2
----------

1. Change the query found in question 1.3 so that it includes the order date. HINT: You will have to join to one more table.
2. Write a query that produces a list of the customer names and their SalesOrderID numbers. You will have to join three tables: Person.Person, Sales.Customer, and Sales.SalesOrderHeader.
3. Write a query that returns the list of employees and their current department. To do this, you will have to join the HumanResources.Employee table to the HumanResources.EmployeeDepartmentHistory table and the HumanResources.Department table. You must also return rows where the EndDate from the history table is NULL to get the latest data. Include BusinessEntityID, job title and department name in the results.

Exercise 3
----------

1. Return a list of the ProductID and name along with the SalesOrderID. Include all products even if they have not been ordered.
2. Write a query that returns a list of the names in the People.People table. If the individual also happens to be a customer, return the CustomerID. Join the PersonID to the BusinessEntityID.
3. Modify the query from 3.2 to include the list of orders placed as well. Include SalesOrderID and OrderDate. Make sure that none of the names drop out of the results.

Resources
---------
Once you have completed the problem set, you may find the following resources helpful to understand everything.

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers05
