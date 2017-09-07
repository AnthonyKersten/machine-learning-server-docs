--- 
 
# required metadata 
title: "Machine Learning Concat Transform" 
description: " Combines several columns into a single vector-valued column. " 
keywords: "MicrosoftML, concat, transform" 
author: "bradsev"
ms.author: "bradsev" 
manager: "jhubbard" 
ms.date: "04/17/2017" 
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
 
 
 
 
 #concat: Machine Learning Concat Transform

 Applies to version 1.3.0 of package MicrosoftML.
 
 ##Description
 
Combines several columns into a single vector-valued column.
 
 
 ##Usage

```   
  concat(vars, ...)
 
```
 
 ##Arguments

   
  
 ### vars
 A named list of character vectors of input variable names and the name of the output variable. Note that all the input variables must be of the same type. It is possible to produce mulitple output columns  with the concatenation transform. In this case, you need to use a list of  vectors to define a one-to-one mappings between input and output variables. For example, to concatenate columns InNameA and InNameB into column OutName1 and also columns InNameC and InNameD into column OutName2, use the list:  (list(OutName1 = c(InNameA, InNameB), outName2 = c(InNameC, InNameD))) 
  
  
  
 ###  ...
 Additional arguments sent to the compute engine 
  
 
 
 ##Details
 
`concat` creates a single vector-valued column from multiple  
columns. It can be performed on data before training a model. The concatenation  
can significantly speed up the processing of data when the number of columns 
is as large as hundreds to thousands.
 
 
 ##Value
 
A `maml` object defining the concatenation transform.
 
 ##Author(s)
 
Microsoft Corporation [`Microsoft Technical Support`](https://go.microsoft.com/fwlink/?LinkID=698556&clcid=0x409)

 
 
 ##See Also
 
[featurizeText](featurizetext.md), [categorical](categorical.md),
[categoricalHash](categoricalhash.md), [rxFastTrees](rxfasttrees.md),
[rxFastForest](rxfastforest.md), [rxNeuralNet](rxneuralnet.md),
[rxOneClassSvm](rxoneclasssvm.md), [rxLogisticRegression](rxlogisticregression.md).
   
 ##Examples

 ```
   
  testObs <- rnorm(nrow(iris)) > 0
  testIris <- iris[testObs,]
  trainIris <- iris[!testObs,]
  
  multiLogitOut <- rxLogisticRegression(
          formula = Species~Features, type = "multiClass", data = trainIris,
          mlTransforms = list(concat(vars = list(
              Features = c("Sepal.Length", "Sepal.Width", "Petal.Length", "Petal.Width")
            ))))
  summary(multiLogitOut)
 
```
 
 
