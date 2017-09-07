---

# required metadata
title: "What is azureml-model-management-sdk - Machine Learning Server | Microsoft Docs"
description: "azureml-model-management-sdk Functions"
keywords: "azureml-model-management-sdk package reference"
author: "j-martens"
ms.author: "jmartens"
manager: "jhubbard"
ms.date: "9/25/2017"
ms.topic: "reference"
ms.prod: "microsoft-r"

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

# azureml-model-management-sdk library
 
**Applies to:  Machine Learning Server, SQL Server 2017**

'azureml-model-management-sdk' is a custom library developed by Microsoft. This library provides classes and functions for deploying and managing analytic web services that are backed by Python or R code block / scripts.  

This topic is a high-level description of library functionality. These classes and functions can be called directly. For syntax and other details, see the individual function help topics in the table of contents.

<br/>

| Library details | |
|--------|-|
| Version: |  9.2.0 |
| Supported on: | [Machine Learning Server](../../what-is-machine-learning-server.md) </br>[SQL Server 2017 Machine Learning Services](https://docs.microsoft.com/sql/advanced-analytics/python/sql-server-python-services) </br>[SQL Server 2017 Machine Learning Server (Standalone)](https://docs.microsoft.com/sql/advanced-analytics/r/r-server-standalone#whats-new-in-microsoft-machine-learning-server) |
| Built on: | [Anaconda](https://www.continuum.io/why-anaconda) distribution of [Python 3.5](https://www.python.org/doc) (included when you add Python support during installation). |


## How to use this library

The **azureml-model-management-sdk** library is installed as part of Machine Learning Server and SQL Server Machine Learning Services when you add Python to your installation. It is also [available locally](../../install/python-libraries-interpreter.md).  When you install these products, you get the full collection of proprietary packages plus a Python distribution with its modules and interpreters. 

You can use any Python IDE to write Python scripts that call the classes and functions in **azureml-model-management-sdk**, but the script must run on a computer having Machine Learning Server or SQL Server Machine Learning with Python.

There are **three primary use cases** for this release: 

+ Adding authentication logic to your Python script
+ Deploying standard or realtime Python web services
+ Consuming these web services

## Main classes and functions

* [DeployClient](deploy-client.md) 

* [MLServer](mlserver.md) 

* [Operationalization](operationalization.md) 

* [OperationalizationDefinition](operationalization-definition.md) 

* [ServiceDefinition](service-definition.md) 

* [RealtimeDefinition](realtime-definition.md) 

* [Service](service.md) 

* [ServiceResponse](service-response.md) 

* [Batch](batch.md) 

* [BatchResponse](batch-response.md) 




## Next steps

Add both Python modules to your computer by running setup: 

+ Set up [Machine Learning Server for Python](heidi-to-provide-set-up-link.md) or [Python Machine Learning Services](https://docs.microsoft.com/sql/advanced-analytics/python/setup-python-machine-learning-services).

Next, follow this quickstart for hands on experience:

+ [Quickstart: How to deploy Python model as a service](../../operationalize/python/quickstart-deploy-python-web-service.md) 

+ [How to publish and manage web services in Python](../../operationalize/python/how-to-deploy-manage-web-services.md)


## See also

[Library Reference](../introducing-python-package-reference.md)

[Install Machine Learning Server](../../what-is-machine-learning-server.md)

[Install the Python interpreter and libraries](../../install/python-libraries-interpreter.md)
