--- 
 
# required metadata 
title: "olapR explore Method" 
description: "Allows for exploration of cube metadata " 
keywords: "olapR, explore" 
author: "richcalaway"
ms.author: "richcala" 
manager: "jhubbard" 
ms.date: "09/23/2017" 
ms.topic: "reference" 
ms.prod: "microsoft-r" 
ms.service: "" 
ms.assetid: "" 
 
# optional metadata 
#ROBOTS: "" 
#audience: "" 
#ms.devlang: "" 
#ms.reviewer: "" 
#ms.suite: "" 
#ms.tgt_pltfrm: "" 
ms.technology: "r-server" 
#ms.custom: "" 
 
--- 

#explore: olapR explore Method

 Applies to version 1.0.0 of package olapR.
 
 
 ##Description
 
Allows for exploration of cube metadata
 
 
 
 ##Usage

```   
  explore(olapCnn, cube = NULL, dimension = NULL, hierarchy = NULL, level = NULL)
```
 
 
 ##Arguments

   
    
 ### olapCnn
 Object of class "OlapConnection" returned by `OlapConnection()` 
  
    
 ### cube
 A string specifying a cube name 
  
    
 ### dimension
 A string specifying a dimension name 
  
    
 ### hierarchy
 A string specifying a hierarchy name 
  
    
 ### level
 A string specifying a level name 
  
 
 
 
 ##Details
 
`explore` 
 
 
 
 ##Value
 
Prints cube metadata. Returns NULL.
An error is thrown if arguements are invalid
 
 
 ##Note
 
Arguements must be specified in order. Eg: In order to explore hierarchies, a dimension and a cube must be specified.
 
 
 
 ##References
  See [execute2D](execute2d.md) or [executeMD](executemd.md) for references.  
 
 
 ##See Also
 
query`, `[OlapConnection](olapconnection.md)`, `[executeMD](executemd.md)`, `[execute2D](execute2d.md)
   
 
 ##Examples

 ```
   
  cnnstr <- "Data Source=localhost; Provider=MSOLAP;"
  ocs <- OlapConnection(cnnstr)
  
  #Exploring Cubes
  explore(ocs)
  #Analysis Services Tutorial
  #Internet Sales
  #Reseller Sales
  #Sales Summary
  #[1] TRUE
  
  #Exploring Dimensions
  explore(ocs, "Analysis Services Tutorial")
  #Customer
  #Date
  #Due Date
  #Employee
  #Internet Sales Order Details
  #Measures
  #Product
  #Promotion
  #Reseller
  #Reseller Geography
  #Sales Reason
  #Sales Territory
  #Ship Date
  #[1] TRUE
  
  #Exploring Hierarchies
  explore(ocs, "Analysis Services Tutorial", "Product")
  #Category
  #Class
  #Color
  #Days To Manufacture
  #Dealer Price
  #End Date
  #List Price
  #Model Name
  #Product Categories
  #Product Line
  #Product Model Lines
  #Product Name
  #Reorder Point
  #Safety Stock Level
  #Size
  #Size Range
  #Standard Cost
  #Start Date
  #Status
  #Style
  #Subcategory
  #Weight
  #[1] TRUE
  
  #Exploring Levels
  explore(ocs, "Analysis Services Tutorial", "Product", "Product Categories")
  #(All)
  #Category
  #Subcategory
  #Product Name
  #[1] TRUE
  
  #Exploring Members
  #NOTE: -> indicates that the following member is a child of the previous member
  explore(ocs, "Analysis Services Tutorial", "Product", "Product Categories", "Category")
  #Accessories
  #Bikes
  #Clothing
  #Components
  #Assembly Components
  #-> Assembly Components
  #--> Assembly Components
 
```
 
