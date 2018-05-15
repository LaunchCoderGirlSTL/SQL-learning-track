Week 3 Problem Set
==================

If you need the ORDERBY and WHERE SQl files, the two files live in this `folder <https://github.com/LaunchCoderGirlSTL/SQL-Materials/tree/master/Week%203/>`_ and can be downloaded.
Unless otherwise specified, use the AdventureWorks2014 database for these questions.

1. Show a list of unique job titles from the Employee table.
2. Show a list of contact types that contain the word “manager” anywhere in the value.
3. Show a list of contact types that contain the word “market” and the word “manager” anywhere in the value. Order of the words within the value is not important... Manager can come before or after Market.
4. Show a list of contact types that do not contain the words “market” or “manager”. Neither word should appear in the title.
5. Show StateProvinceCode, Name and CountryRegionCode from the StateProvince table. Show only the rows where the Name begins with “AL” and the CountryRegionCode is not “FR”.
6. Show FirstName, LastName and EmailPromotion for people who have first names that start with “Q” or for people that meet these three criteria: First name starts with “X” and last name starts with “W” and EmailPromotion greater than 0.
7. Show FirstName, LastName, PersonType and BusinessEntityID for people who have a BusinessEntityID less than 10 or people who have a first name that starts with “Pat” and have a PersonType of “SC”.
8. Show FirstName, LastName, Suffix and Title for people who have some value for Suffix but nothing (null) for a Title.
9. From the SalesPerson table, show BusinessEntityID, SalesQuota, SalesYTD, SalesLastYear, Bonus and CommissionPct for people that have a CommisionPct of .015 or higher and one of either a bonus greater than 4,000 or SalesYTD greater than 300,000.
10. From the SalesPerson table, show BusinessEntityID, SalesQuota, SalesYTD, SalesLastYear, Bonus and CommissionPct for people that have a bonus under 2,500 and their quota is under 300,000 or null.
11. From the product table, show ProductID, Name, ProductNumber, SafetyStockLevel and Color where:

  1. SafetyStockLevel is less than 10
  2. Color equals null
  3. Name ends in either “Pump” or “Cage”

Resources
---------

Once you have completed the problem set, you might find the following resources helpful in understanding what you got right and wrong and why!

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers03
