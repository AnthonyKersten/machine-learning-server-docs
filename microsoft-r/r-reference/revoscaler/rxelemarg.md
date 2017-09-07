--- 
 
# required metadata 
title: " Helper function for rxExec arguments " 
description: " Allows different argument values to be passed to different (named and unnamed) nodes or cores through the elipsis argument for rxExec. A vector or list of the argument values is used. " 
keywords: "RevoScaleR, rxElemArg, IO" 
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
 
 
 #rxElemArg:  Helper function for rxExec arguments 

 Applies to version 9.1.0 of package RevoScaleR.
 
 ##Description
 
Allows different argument values to be passed to different (named and unnamed) nodes or cores through
the elipsis argument for rxExec. A vector or list of the argument values is used.
 
 
 
 ##Usage

```   
  rxElemArg(x)
 
```
 
 
 ##Arguments

   
  
 ### x
 The list or vector to be applied across the set of computations. 
  
 
 
 
 ##Details
 
This function is designed for use only within a call to [rxExec](rxexec.md).  [rxExec](rxexec.md)
allows for the processing of a user function on multiple nodes or cores.  Arguments
for the user function can be passed directly through the call to [rxExec](rxexec.md).  By default,
the same argument value will be passed to each of the nodes or cores.  If instead, 
a vector or list of argument values is wrapped in a call to `rxElemArg`, 
a distinct argument value will be passed to each node or core.  

If `timesToRun` is specified for [rxExec](rxexec.md), the length of the vector or 
list within `rxElemsArg` must have a length equalto `timesToRun`. If `timesToRun` 
is not specified and the `elemType` is set to `"cores"`, the length of the vector 
or list will determine the `timesToRun`. 

If `elemArgs` is used in addition to the `rxElemArg` function, the length of both
lists/vectors must be the same.
 
 
 ##Value
 
x is returned with attributes modified for use by rxExec.
 
 ##Author(s)
 Microsoft Corporation [`Microsoft Technical Support`](https://go.microsoft.com/fwlink/?LinkID=698556&clcid=0x409)
 
 
 ##See Also
 
[rxExec](rxexec.md)
   
 
 ##Examples

 ```
   
  ## Not run:
 
# Setup an HPC Server compute context
myCluster <- RxHpcServer(
    headNode = "cluster-head", 
    shareDir = "\\AllShare\username",
    revoPath = file.path(defaultRNodePath, "bin", "x64"), 
    workingDir = "C:\\Users\\username", 
    wait = TRUE)
rxOptions( computeContext = myCluster )

# Create a function to be run on multiple cores
myFunc <- function( sampleSize = 100, seed = 5)
{
	set.seed(seed)
	mean( rnorm( sampleSize ))
}	

# Use the same sampleSize for every computation, but a separate seed.
# The function will run 20 times, because that is the length of the
# vector in rxElemArg
mySeeds <- runif(20, min=1, max=1000)
rxExec( myFunc, 100, seed = rxElemArg( mySeeds ), elemType = "cores")

# Send different sample sizes and different seeds
# Both mySeeds and mySampleSizes must have the same length
mySampleSizes <- 2^c(1:20)
res <- rxExec(myFunc, rxElemArg( mySampleSizes ), seed = rxElemArg( mySeeds ),
   elemType = "cores")
 ## End(Not run) 
  
 
```
 
 
