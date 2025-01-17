---
title: "AVG (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the average of the values in a group. Null values are ignored."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: c0638288-6ca0-49f7-b119-8c0af842203a
caps.latest.revision: 5
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---

# AVG (Azure Stream Analytics)
  Returns the average of the values in a group. Null values are ignored.  
  
 ## Syntax  
  
```SQL   
AVG (expression )  
```  
  
## Arguments  
 **expression**  
  
 Is an expression of the exact numeric or approximate numeric data type category. AVG can be used with bigint and float columns. Aggregate functions and sub queries are not permitted.  
  
## Return Types  
 The return type is determined by the type of the evaluated result of expression.  
  
## Examples  
  
```SQL
SELECT System.Timestamp() AS OutTime, TollId, AVG (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
