--- 
 
# required metadata 
title: "Class RxForeachDoPar" 
description: "   Class for the RevoScaleR Compute Context using one of the foreach dopar back ends.   " 
keywords: "RevoScaleR, RxForeachDoPar-class, show,RxForeachDoPar-method, classes" 
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
 
 
 
 
 #RxForeachDoPar-class: Class RxForeachDoPar

 Applies to version 9.1.0 of package RevoScaleR.
 
 ##Description
 
Class for the RevoScaleR Compute Context using one of the foreach dopar back ends.  
 
 
 ## Generators 

 
The targeted generator [RxForeachDoPar](rxforeachdopar.md) as well as the general generator
[RxComputeContext](rxcomputecontext.md).
 
 ## Extends 

 
Class RxComputeContext, directly.
 
 ## Methods 

 


###show
`signature(object = "RxForeachDoPar")`: ...



 
 ##Author(s)
 Microsoft Corporation [`Microsoft Technical Support`](https://go.microsoft.com/fwlink/?LinkID=698556&clcid=0x409)
 
 
 ##See Also
 
[RxComputeContext](rxcomputecontext.md),
[RxLocalSeq](rxlocalseq.md),
[RxLocalParallel](rxlocalparallel.md),
[RxSpark](rxspark.md),
[RxHadoopMR](rxhadoopmr.md),
[RxInTeradata](rxinteradata.md).

   
 ##Examples

 ```
   
  ## Not run:
 
myComputeContext <- RxComputeContext("RxForeachDoPar")
is(myComputeContext, "RxComputeContext")
# [1] TRUE
is(myComputeContext, "RxForeachDoPar")
# [1] TRUE
 ## End(Not run) 
  
 
```
 
 
