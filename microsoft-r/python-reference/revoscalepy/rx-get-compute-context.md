--- 
 
# required metadata 
title: "rx_get_compute_context: Get and Set the compute context" 
description: "Get or set the active compute context for revoscalepy computationsrx_set_compute_context(compute_context: ‘RxComputeContext’) rx_get_compute_context()" 
keywords: "context" 
author: "bradsev" 
manager: "jhubbard" 
ms.date: "09/06/2017" 
ms.topic: "reference" 
ms.prod: "microsoft-r" 
ms.service: "" 
ms.assetid: "" 
 
# optional metadata 
ROBOTS: "" 
audience: "" 
ms.devlang: "Python" 
ms.reviewer: "" 
ms.suite: "" 
ms.tgt_pltfrm: "" 
ms.technology: "r-server" 
ms.custom: "" 
 
---

# rx_get_compute_context


**Applies to: SQL Server 2017 RC2**


## Usage



```
revoscalepy.rx_get_compute_context() -> revoscalepy.computecontext.RxComputeContext.RxComputeContext
```





## Description

Get or set the active compute context for revoscalepy computations

rx_set_compute_context(compute_context: ‘RxComputeContext’)
rx_get_compute_context()


## Arguments


### compute_context

character string specifying class name or description
of the specific class to instantiate, or an existing RxComputeContext object.
Choices include: “RxLocalSeq” or “local”, “RxInSqlServer”.


## Returns

rx_set_compute_context returns the previously active compute context
invisibly. rx_get_compute_context returns the active compute context.


## See also

`RxComputeContext`,
[`RxLocalSeq`](RxLocalSeq.md),
[`RxInSqlServer`](RxInSqlServer.md),
[`rx_set_compute_context`](rx-set-compute-context.md).


## Example



```
from revoscalepy import RxLocalSeq, RxInSqlServer, rx_get_compute_context, rx_set_compute_context

local_cc = RxLocalSeq()
sql_server_cc = RxInSqlServer('Driver=SQL Server;Server=.;Database=RevoTestDb;Trusted_Connection=True;')
previous_cc = rx_set_compute_context(sql_server_cc)
rx_get_compute_context()
```

