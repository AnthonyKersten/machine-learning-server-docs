--- 
 
# required metadata 
title: " Distribute job across nodes of a cluster " 
description: " Allows distributed execution of a function in parallel across nodes (computers)  of a compute context such as a cluster. A helper functions checks to see if the compute context is appropriate. " 
keywords: "RevoScaleR, rxDistributeJob, rxIsDistributedContext, IO" 
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
 
 
 
 #rxDistributeJob:  Distribute job across nodes of a cluster 

 Applies to version 9.1.0 of package RevoScaleR.
 
 ##Description
 
Allows distributed execution of a function in parallel across nodes (computers) 
of a 'compute context' such as a cluster. A helper functions checks to see
if the 'compute context' is appropriate.
 
 
 
 ##Usage

```   
  rxDistributeJob(matchCallList, matchCall)
  rxIsDistributedContext( computeContext = NULL, data = NULL)
 
```
 
 
 ##Arguments

   
  
 ### matchCallList
  a list containing the function name and arguments, adjusting environments as needed 
  
  
  
 ### matchCall
  a call in which all of the specified arguments are specified by their full names;  typically the result of match.call 
  
  
  
 ### computeContext
 `NULL` or an [RxComputeContext](rxcomputecontext.md) object. 
  
  
  
 ### data
 `NULL` or an [RxDataSource](rxdatasource.md) object.  If specified, compatibility of the data source with the 'dataDistType' in the compute context will be checked. 
  
  
 
 
 
 ##Details
 
An example of usage can be found in the **RevoPemaR** package.
 
 
 
 ##Value
 
The result of the distributed computation.

 
 
 
 ##See Also
 
[rxExec](rxexec.md),
[RxComputeContext](rxcomputecontext.md),
[rxSetComputeContext](rxsetcomputecontext.md),
[rxGetComputeContext](rxsetcomputecontext.md)
   
 ##Examples

 ```
   
  ## Not run:
 

# Example is provided in the RevoPemaR package

 ## End(Not run) 
  
 
```
 
 
