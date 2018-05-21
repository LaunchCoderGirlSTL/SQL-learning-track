# Week 10 Problem Set Part 2 Solutions

```
 -- Combine Product Categories and Subcategories into one list.
 SELECT pc.Name
 FROM Production.ProductCategory pc
 UNION
 SELECT psc.Name
 FROM Production.ProductSubcategory psc
 -- Combine into one list (with no duplicates): ReasonType from SalesReasons and Group
 from ShoppingCartItem
 SELECT ReasonType
 FROM [Sales].[SalesReason]
 UNION
 SELECT [Group]
 FROM [Sales].[SalesTerritory]
 -- Combine into one list (WITH duplicates): ReasonType from SalesReasons and Group from
 ShoppingCartItem
 SELECT ReasonType
 FROM [Sales].[SalesReason]
 UNION ALL
 SELECT [Group]
 FROM [Sales].[SalesTerritory]
 -- How many Product IDs are returned when you UNION together the ProductID from
 SpecialOfferProduct and ShoppingCartItem?
 SELECT ProductID
 FROM sales.SpecialOfferProduct
 UNION
 SELECT ProductID
 FROM sales.ShoppingCartItem
 -- How many Product IDs are returned when you UNION ALL together the ProductID from
 SpecialOfferProduct and ShoppingCartItem?
 SELECT ProductID
 FROM sales.SpecialOfferProduct
 UNION ALL
 SELECT ProductID
 FROM sales.ShoppingCartItem
 -- How many are returned when you select all ProductIDs from SpecialOfferProduct EXCEPT
 the Products in ShoppingCartItem?
 SELECT ProductID
 FROM sales.SpecialOfferProduct
 EXCEPT
 SELECT ProductID
 FROM sales.ShoppingCartItem
 -- How many are returned when you select all ProductIDs from SpecialOfferProduct where
 the ProductID is IN ShoppingCartItem?
 SELECT ProductID
 FROM sales.SpecialOfferProduct
 WHERE ProductID IN (
 SELECT ProductID
 ```
 
