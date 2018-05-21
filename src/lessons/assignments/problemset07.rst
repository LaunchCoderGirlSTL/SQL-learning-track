Week 10 Problem Set Part 1
==========================

Use the following CREATE and INSERT statements for the first part of the problem set::

  ---- Run Create and Insert statements first
  )
   CREATE TABLE Fruit (
   ID INT,
   FruitName VARCHAR(25)
    INSERT INTO Fruit
   VALUES (1,'Apple')
   , (2, 'Banana')
   , (3, 'Pear')
   , (4, 'Pineapple')
   , (5, 'Peach')
   CREATE TABLE Food (
   ID INT,
   FoodName VARCHAR(25)
   )
   INSERT INTO Food
   VALUES (1, 'Apple')
   , (2, 'Pizza')
   , (3, 'Pear')
   , (4, 'Spaghetti')
   , (5, 'Chicken')
   , (6, 'Banana')
   , (7, 'Peach')

1. Combine ID and FruitName with ID and FoodName via Union. How many records are returned?
2. Combine ID and FruitName with ID and FoodName via Union ALL. How many records are returned?
3. Return results from the Food table Except the records that are also in the Fruit table.
4. Return ID and FoodName where the food is also in the FruitName column in the Fruit table.

Resources
---------
Use the following resources if you need any help with the problem set!

.. toctree::
  :maxdepth: 1

  solutions/problemsetanswers07
