--- 
 
# required metadata 
title: "Class RxLocalParallel" 
description: "   Class for the RevoScaleR Local Parallel Compute Context.   " 
keywords: "RevoScaleR, RxLocalParallel-class, show,RxLocalParallel-method, classes" 
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
 
 
 
 
 #RxLocalParallel-class: Class RxLocalParallel

 Applies to version 9.1.0 of package RevoScaleR.
 
 ##Description
 
Class for the RevoScaleR Local Parallel Compute Context.  
 
 
 ## Generators 

 
The targeted generator [RxLocalParallel](rxlocalparallel.md) as well as the general generator
[RxComputeContext](rxcomputecontext.md).
 
 ## Extends 

 
Class RxComputeContext, directly.
 
 ## Methods 

 


###show
`signature(object = "RxLocalParallel")`: ...



 
 ##Author(s)
 Microsoft Corporation [`Microsoft Technical Support`](https://go.microsoft.com/fwlink/?LinkID=698556&clcid=0x409)
 
 
 ##See Also
 
[RxHadoopMR](rxhadoopmr.md),
[RxSpark](rxspark.md),
[RxInSqlServer](rxinsqlserver.md),
[RxInTeradata](rxinteradata.md),
[RxLocalSeq](rxlocalseq.md).
   
 ##Examples

 ```
   
  ## Not run:
 
myComputeContext <- RxComputeContext("RxLocalParallel")
is(myComputeContext, "RxComputeContext")
# [1] TRUE
is(myComputeContext, "RxLocalParallel")
# [1] TRUE
 ## End(Not run) 
  
 
```
 
 
