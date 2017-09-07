--- 
 
# required metadata 
title: " Obtain Distributed Computing Job Status and Results " 
description: " Obtain distributed computing results and processing status. " 
keywords: "RevoScaleR, rxGetJobResults, rxGetJobStatus, IO" 
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
 
 
 
 #rxGetJobResults:  Obtain Distributed Computing Job Status and Results 

 Applies to version 9.1.0 of package RevoScaleR.
 
 
 ##Description
 
Obtain distributed computing results and processing status.
 
 
 ##Usage

```   
  rxGetJobResults(jobInfo, consoleOutput = NULL, autoCleanup = NULL)
  rxGetJobStatus(jobInfo)
 
```
 
 
 ##Arguments

   
    
 ### jobInfo
 a `jobInfo` object as returned by [rxExec](rxexec.md) or a **RevoScaleR**analysis function, for example, the `rxgLastPendingJob` object, if available. 
  
  
  
 ### consoleOutput
 `NULL` or logical value. If `TRUE`, the console output from  all of the processes is printed to the user console. If `FALSE`,  no console output is displayed. Output can be retrieved with the function  [rxGetJobOutput](rxgetjoboutput.md) for a non-waiting job. If not `NULL`,  this flag overrides the  value set in the compute context when the job was submitted. If `NULL`,  the setting in the compute context will be used. 
  
  
  
    
 ### autoCleanup
 `NULL` or logical value. If `TRUE`, the default behavior is to clean up  any artifacts created by the distributed computing job. If `FALSE`, then the  artifacts are not deleted, and the results may be acquired using [rxGetJobResults](rxgetjobresults.md),  and the console output via [rxGetJobOutput](rxgetjoboutput.md) until the [rxCleanupJobs](rxcleanup.md) is used to delete the artifacts.  If not `NULL`, this flag overwrites the value set in the compute context when the job was submitted. If you routinely set `autoCleanup=FALSE`, you will eventually fill your hard disk with compute artifacts.If you set `autoCleanup=TRUE`and experience performance degradation on a Windows XP client, consider setting `autoCleanup=FALSE`. 
  
 
 
 
 
 ##Details
 

The possible job status strings returned by `rxGetJobStatus` are:


###"undetermined"
information no longer retained by job scheduler.  May still retrieve results  and output when available.


###"finished"
job has successfully completed.


###"failed"
job has failed.


###"canceled"
job has been canceled and the cancel process is completed.


###"missing"
job is no longer available on the cluster.


###"running"
job is either running or completing it's run (finishing, flushing buffers, etc.), or it is in the process of being canceled.


###"queued"
job is in one of the following states:   it is being configured, has been submitted but has not started, is being validated, or is in the job queue.




On LSF clusters, job information by default is held for only one hour (although this is configurable using
the LSF parameter CLEAN_PERIOD); jobs older than the CLEAN_PERIOD setting will have status `"undetermined"`. 

 
 
 
 ##Value
 
`rxGetJobResults`: either the results of the run (prepended with console output if the
`consoleOutput` argument is set to `TRUE`) or a message saying that the results are 
not available because the job has not finished, has failed, or was deleted. 

`rxGetJobStatus`: a character string denoting the job status.
 
 ##See Also
 
[RxSpark](rxspark.md),
[RxHadoopMR](rxhadoopmr.md),
[RxInTeradata](rxinteradata.md), 
[RxInSqlServer](rxinsqlserver.md),
[rxGetJobs](rxgetjobs.md), 
[rxCleanupJobs](rxcleanup.md),
[rxGetJobStatus](rxgetjobresults.md),
[rxExec](rxexec.md).
   
 ##Examples

 ```
   
  ## Not run:
 
# set up the cluster object
myCluster <- RxHpcServer(
    headNode = "cluster-head", 
    shareDir = "\\AllShare\\username",
    revoPath = file.path(defaultRNodePath, "bin", "x64"), 
    workingDir = "C:\\Users\\username", 
    wait = FALSE)
rxOptions(computeContext=myCluster)

func <- function(name)
{
    print("hi")
    cat(name)
    name
}

jobInfo <- rxExec(func, "dog", elemType = "cores", timesToRun = 5)
rxGetJobStatus(jobInfo)
rxGetJobResults(jobInfo)
 ## End(Not run) 
  
 
```
 
 
 
