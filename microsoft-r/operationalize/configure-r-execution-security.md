---

# required metadata
title: "R Execution Security Considerations and user isolation - Machine Learning Server | Microsoft Docs"
description: "R Execution Security Considerations when operationalizing analytics with Machine Learning Server"
keywords: "RServe; deployr-rserve; user isolation"
author: "j-martens"
ms.author: "jmartens"
manager: "jhubbard"
ms.date: "9/25/2017"
ms.topic: "article"
ms.prod: "microsoft-r"

# optional metadata
#ROBOTS: ""
#audience: ""
#ms.devlang: ""
#ms.reviewer: ""
#ms.suite: ""
#ms.tgt_pltfrm: ""
ms.technology:
  - deployr
  - r-server
#ms.custom: ""
---

# R Execution Security Considerations

**Applies to: Machine Learning Server, Microsoft R Server 9.x**

`deployr-rserve` is a forked version of RServe maintained by Microsoft. In this forked version, we support parallel R sessions for both Windows and Linux thereby overcoming this limitation in the original rserve package.

This forked version of RServe is the R execution component behind the compute node for Machine Learning Server (and R Server). Compute nodes are used to execute R code as a session or service. Each compute node has its own [pool of R shells](configure-evaluate-capacity.md#pool).  

This RServe fork acts as an interface to R, which by default is single threaded. However, in this context, this RServe fork sits atop of the RevoScaleR package. Therefore, if you use RevoScaleR package functions, you benefit from multi-threaded processing in the R shell.

>[!IMPORTANT]
>Machine Learning Server's web and compute nodes are not designed for multi-tenancy. To prevent data leakage, follow your organization's best practices.

## The Execution Context

As per the standard usage of R, the current user starts the R executable and interacts with the application via the R Language and the R Interpreter. The R language provides OS-level access via the 'system' function. With this function, a user can execute an OS command such as `system(“rmdir –r C:\\tmp”)`. While the functionality is useful to individual users, **it is also a potential entry point through which the computer's security could be compromised.**

Machine Learning Server provides various [API calls](concept-api.md) that permit the execution of R scripts and R code. All authentication takes place on the web node, and the execution of the R code is managed through Machine Learning's custom version of RServe add-on component. RServe provides a TCP/IP interface to the R Interpreter running on the machine. By default, Rserve runs on the same machine as the compute node. RServe is started by Windows Service (RServeWinService) that runs under a virtual service account with low privileges. RServe inherits the permissions of that virtual service account. In the default configuration, Rserve only accepts socket connections from `localhost`. In other words, only those processes running on the same machine where RServe is running can directly connect to it and execute R code.

>[!Important]
>The compute node should, ideally, be the only local process that connects to RServe. To help ensure this is the case, a username and password is required to validate any connection between RServe and a client process.
>
>However, there exist several vulnerabilities of which you should be aware. They are:
>
>-   RServe only accepts usernames and passwords in plain text from connecting clients.
>-   RServe uses a plain text configuration file to store the username and password.

If your configuration requires additional compute capacity, you can add [additional compute nodes](../operationalize/configure-machine-learning-server-enterprise.md) for more sophisticated load-balancing capabilities.

<a name="isolation"></a>

## Directory & User Isolation Considerations

In the R language, users can change files in the file system, download content from the web, download packages, and so on.

In order to mitigate some of the risks associated with RServe, the service is set up to run using **a single account with write permissions** to the R working directory <MRS_home>\deployr\Rserve\workdir, which is the directory under which R sessions and service calls store artifacts, files, and workspaces.

>[!Important]
>While the custom Rserve service can only write to the working directory, **there is no user isolation between the session folders**. Any user familiar with the directory structure could in theory access another user’s session folder from their R script.
