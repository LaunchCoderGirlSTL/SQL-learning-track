Week 18 Problem Set
===================

Use the AdventureWorks2014 database for these questions.

1. Write a script that saves the count of rows in the SalesOrderHeader table in a variable. Then set up an ``IF`` block that prints “The count of sales is over 50,000” or “The count of sales is under 50,000” based on the count.
2. Write a loop that runs 100 times. If the counter is divisible by 2 (look up the modulo function %) then print “The value is even”. If it is odd, print “The value is odd.”
3. Write a script that contains nested IF blocks. The outer block should check to see whether the month is May or June. If it’s one of those months, then print “The month is “ plus the month. The inner block should check to see if the year is even. Print that information.
4. Save the production.product table into a temp table. Set up a loop to delete one row at a time.
5. Create a table called WordToLetters that has an identity column called ID, an Integer column called WordNumber and a CHAR(1) column called Letter. Create a stored procedure called SplitWord that takes a parameter called @Word varchar(50). This stored procedure should enter one row in the table for each letter in the word. Be sure to review functions that can help you write this proc. Here is an example::

    Exec dbo.SplitWord @word = ‘apple’;
    SELECT * FROM WordToLetters;

Resources
---------

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers13
