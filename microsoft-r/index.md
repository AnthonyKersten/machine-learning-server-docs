---

# required metadata
title: "What is Microsoft R Server and R Client"
description: "Learn about Microsoft R features and components in R Server, R Client, R Open."
keywords: ""
author: "j-martens"
ms.author: "jmartens"
manager: "jhubbard"
ms.date: "06/22/2017"
ms.topic: "get-started-article"
ms.prod: "microsoft-r"

# optional metadata
#ROBOTS: ""
#audience: ""
#ms.devlang: ""
#ms.reviewer: ""
#ms.suite: ""
#ms.tgt_pltfrm: ""
ms.technology:
  - r-client
  - r-server
#ms.custom: ""

---

# Microsoft R

Microsoft R is a collection of packages, interpreters, and infrastructure for developing and deploying R-based machine learning and data science solutions on a range of platforms, from local standalone installations on Linux and Windows, to large distributed deployments on node clusters. We make these capabilities available in several products and services to meet the needs of individual or teams of data scientists and developers.

+ [Microsoft R Server](what-is-microsoft-r-server.md) is the flagship product and supports very large workloads in the enterprise. 

+ [Microsoft R Client](r-client/what-is-microsoft-r-client.md) is a free workstation version. It includes the same R Server functionality, but for local workloads.

+ [Microsoft R Open](https://mran.microsoft.com/open/) is Microsoft's distribution of open source R, without the proprietary packages and infrastructure of our other products. This R distribution is included in both Microsoft R Client and R Server. 

## Quickstarts and Step-by-Step

In minutes, you can step through a classic what-if problem using sample data and R script in the first quickstart. Additional step-by-step tutorials offer a hands-on experience performing practical data science tasks.

* [Quickstart: Run R code in Microsoft R](r/quickstart-run-r-code.md) 

* [Quickstart: Deploy R code as a web service](operationalize/quickstart-publish-r-web-service.md) 

* [Tutorial: Explore R-to-RevoScaleR](r/tutorial-r-to-revoscaler.md) 

* [Tutorial: Import and transform data](r/tutorial-revoscaler-data-import-transform.md)  

* [Tutorial: Visualize and analyze data](r/tutorial-revoscaler-data-model-analysis.md) 

## Pre-built solutions

We offer solutions tailored to specific industries and problem sets, such as:
+ Predicting Length of Stay in Hospitals

+ Campaign Optimization with SQL Server

+ Campaign Optimization with Azure HDInsight Spark Clusters

+ Loan Credit Risk with SQL Server

Explore machine learning how-to solutions at https://aka.ms/rsolutiontemplates.

## Embedded R Server

Additionally, you can use embedded Microsoft R packages, interpreters, and libraries in Azure data science virtual machines, in Azure HDInsight (Microsoft's distribution of Hadoop), and as an in-database service in SQL Server.

* [Azure: HDInsight and R Server](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-r-server-get-started) 

* [Azure: Data Science virtual machine](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-virtual-machine-overview)

* [SQL Server Machine Learning Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services)

## Start with a local installation

If you are new to Microsoft R, we recommend starting with either [R Server for Windows](install/r-server-install-windows.md), [R Server for Linux](install/r-server-install-linux-server.md), or the free [R Client](r-client-install.md), and an integrated development environment like [R Tools for Visual Studio (RTVS)](https://docs.microsoft.com/visualstudio/rtvs/installation). 

You can install these configurations for free. Each one gives you Microsoft R Open with full support of all base R functions so that you can write R-only solutions, but also includes Microsoft R proprietary packages that run locally on your development computer.

Since the R engine lies underneath, you can use the R Core Team manuals that are part of every R distribution to learn how to code in R. Built-in manuals include *An Introduction to R*, *The R Language Definition*, *Writing R Extensions* and more. Beyond the standard R manuals, there are many other resources. [Learn about them here](resources-more.md).

However, because you have R Client or R Server, your script can also include functions shipped only with Microsoft R products, including the [MicrosoftML](r-reference/microsoftml/microsoftml-package.md), [olapR](r-reference/olapr/olapr.md), [mrsdeploy](r-reference/mrsdeploy/mrsdeploy-package.md), and [RevoScaleR](r-reference/revoscaler/revoscaler.md) packages. All of these packages are available in both R Client and R Server, but at different levels of capacity.

## Next steps

Learn more about Microsoft R in these articles:

+ [Operationalizing R code with R Server](what-is-operationalization.md)

+ [What's new in R Server](whats-new-in-r-server.md)

+ [What's new in R Client](whats-new-in-r-server.md)

+ [Microsoft R Product Web Page](https://www.microsoft.com/en-us/cloud-platform/r-server)

+ [Supported platforms in Microsoft R Server](install/r-server-install-supported-platforms.md)

+ [Microsoft R Client Get Started](r-client-get-started.md)

+ [Microsoft R Forum](https://social.msdn.microsoft.com/Forums/en-US/home?forum=microsoftr)

+ [SQL Server Machine Learning Services](https://msdn.microsoft.com/en-us/library/mt604845.aspx)

+ [Additional Resources](resources-more.md)

