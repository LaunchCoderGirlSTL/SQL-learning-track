Week 10 Problem Set Part 2
==========================

Use AdventureWorks2014 for the following queries.

1. Combine Product Categories and Subcategories into one list.
2. Combine into one list (with no duplicates): ReasonType from SalesReasons and Group from ShoppingCartItem
3. Combine into one list (WITH duplicates): ReasonType from SalesReasons and Group from ShoppingCartItem
4. How many Product IDs are returned when you ``UNION`` together the ProductID from SpecialOfferProduct and ShoppingCartItem?
5. How many Product IDs are returned when you ``UNION`` ALL together the ProductID from SpecialOfferProduct and ShoppingCartItem?
6. How many are returned when you select all ProductIDs from SpecialOfferProduct EXCEPT the Products in ShoppingCartItem?
7. How many are returned when you select all ProductIDs from SpecialOfferProduct where the ProductID is IN ShoppingCartItem?

Resources
---------

Use the following resources if you need any assistance with the problem set.

.. toctree::
   :maxdepth: 1

   solutions/problemsetanswers08
