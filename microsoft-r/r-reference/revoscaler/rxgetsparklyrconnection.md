--- 
 
# required metadata 
title: "Get sparklyr connection from Spark compute context" 
description: " Get a Spark compute context with sparklyr interop.  `rxGetSparklyrConnection` get sparklyr spark connection from created Spark compute context. " 
keywords: "RevoScaleR, rxGetSparklyrConnection" 
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
 
 
 #rxGetSparklyrConnection: Get sparklyr connection from Spark compute context

 Applies to version 9.1.0 of package RevoScaleR.
 
 ##Description
  Get a Spark compute context with sparklyr interop.
 `rxGetSparklyrConnection` get sparklyr spark connection from created Spark compute context.
 
 
 ##Usage

```   
  rxGetSparklyrConnection(
      computeContext = rxGetOption("computeContext"))
 
```
 
 
 ##Arguments

   
    
 ### computeContext
 Compute context get created by `rxSparkConnect`. 
  
 
 
 
 ##Value
 
object of sparklyr spark connection
 
 
 ##Author(s)
 Microsoft Corporation [`Microsoft Technical Support`](https://go.microsoft.com/fwlink/?LinkID=698556&clcid=0x409)
 
 
 
 ##Examples

 ```
   
  ## Not run:
 
library("sparklyr")
cc <- rxSparkConnect(interop = "sparklyr")
sc <- rxGetSparklyrConnection(cc)
iris_tbl <- copy_to(sc, iris)
 ## End(Not run) 
  
 
```
 
