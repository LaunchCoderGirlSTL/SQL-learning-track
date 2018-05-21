# Week 10 Problem Set Part 1 Solutions

```
 -- Combine ID and FruitName with ID and FoodName via Union.  How many records are
 returned?
 SELECT ID, FruitName AS Name
 FROM Fruit
 UNION
 SELECT ID, FoodName
 FROM Food
 -- Combine ID and FruitName with ID and FoodName via Union ALL.  How many records are
 returned?
 SELECT ID, FruitName AS Name
 FROM Fruit
 UNION ALL
 SELECT ID, FoodName
 FROM Food
 ORDER BY ID, Name
 -- Return results from the Food table Except the records that are also in the Fruit
 table.
 SELECT ID, FoodName
 FROM Food
 EXCEPT
 SELECT ID, FruitName
 FROM FRUIT
 -- Return ID and FoodName where the food is also in the FruitName column in the Fruit
 table.
 SELECT ID, FoodName
 FROM Food
 WHERE FoodName IN (SELECT FruitName FROM Fruit)
 ```
