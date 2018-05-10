# Week 2 Problem Set
## Exercise 1
You can write some queries without typing a word. Use SQL Server Management Studio (SSMS) to solve
the problems in this exercise.
1. Run SSMS and connect to your local SQL Server instance. In the Object Explorer window, expand
until you can see the tables in the AdventureWorks2014 database.
2. Just using SSMS without typing, create and run queries that return up to 1000 rows from each of
these tables:<br/>
Person.Person<br/>
Sales.Customer<br/>
Production.Product
3. What are the two important keywords used in the queries you wrote in Question 2? One means a list of
columns to be returned. One tells you which table the data comes from.
4. Here is a T-SQL query. The table name is fully qualified with three parts. What does each part refer
to?<br/>
`SELECT DeptartmentID, Name FROM AdventureWorks2014.HumanResources.Department`

## Exercise 2
The tools in SSMS are great, but most of the time you will need to type out your T-SQL statement. To get
a query window for typing your queries, you will need to click “New Query” in the menu. Make sure that
the database listed in the dropdown box is the AdventureWorks2014 database.
1. What is the difference between these two statements?<br/>
`PRINT ‘Hello world!’;`<br/>
`SELECT ‘Hello world!’;`
2. What are two reasons for using brackets around column and table names?
3. Write a query that returns all of the rows and all of the columns from the Person.Person table. Use
the `*` instead of typing out the columns.
4. It is a bad practice to use the `*` instead of typing out the list of columns for work that you will turn in.
Instead of using the `*`, write a query that returns the BusinessEntityID and the three name columns from
Person.Person.
5. Write a query that returns a list of all the orders in the Sales.SalesOrderHeader table. Return the
SalesOrderID, CustomerID, OrderDate, and TotalDue columns.
6. Starting with the SSMS shortcut you used in Exercise 1, write a query that returns the list of
products (Production.Product table). Remove the columns except for ProductID, Name, Color, and
ListPrice. Run your modified query.

Once you have completed the problem set, you can double check your answers against the [solutions](/lessons/assignments/solutions/problemsetanswers02.html).
