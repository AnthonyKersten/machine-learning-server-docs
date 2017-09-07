--- 
 
# required metadata 
title: "Conversion of a RevoScaleR rxDTree object to an rpart Object" 
description: " Converts objects containing decision tree results to an rpart object. " 
keywords: "RevoScaleR, as.rpart, as.rpart.rxDTree, category, models" 
author: "HeidiSteen"
ms.author: "heidist" 
manager: "jhubbard" 
ms.date: "04/18/2017" 
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
 
 
 
 #as.rpart: Conversion of a RevoScaleR rxDTree object to an rpart Object

 Applies to version 9.1.0 of package RevoScaleR.
 
 ##Description
 
Converts objects containing decision tree results to an rpart object.
 
 
 ##Usage

```   
 ## S3 method for class `rxDTree':
as.rpart  (x, ...)
 
```
 
 ##Arguments

   
    
 ### x
 object of class rxDTree. 
  
    
 ###  ...
 additional arguments (currently not used). 
  
 
 
 
 ##Details
 
This function converts an existing object of class rxDTree an object of
class `rpart`.
The underlying structure of the output object will be a subset of that produced by an equivalent call to
`rpart`. In many cases, this method can be used to coerce an object
for use with the **pmml** package.  **RevoScaleR** model objects that contain
`transforms` or a `transformFunc` are not supported.
 
 
 
 ##Value
 
an object of class rpart.
 
 
 ##Author(s)
 Microsoft Corporation [`Microsoft Technical Support`](https://go.microsoft.com/fwlink/?LinkID=698556&clcid=0x409)
 
 
 ##See Also
 
[rxDTree](rxdtree.md),
[as.lm](as-lm.md),
[as.kmeans](as-kmeans.md),
[as.glm](as-glm.md),
[as.xtabs](as-xtabs.md).
   
 
 ##Examples

 ```
   
  ## Not run:
 
# If the pmml package is installed 
library(pmml)
infert.nrow <- nrow(infert)
infert.sub <- sample(infert.nrow, infert.nrow / 2)
infert.dtree <- rxDTree(case ~ age + parity + education + spontaneous + induced, 
    data = infert[infert.sub, ], cp = 0.01)
infert.dtree
pmml(as.rpart(infert.dtree))
 ## End(Not run) 
  
 
```
 
 
 
 
