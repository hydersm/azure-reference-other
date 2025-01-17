---
title: "MIN (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the minimum value in the expression."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 0480d0eb-babe-4356-a5c0-93001b51744c
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# MIN (Azure Stream Analytics)
  Returns the minimum value in the expression.  
  
 ## Syntax  
  
```SQL   
MIN ( expression )  
```  
  
## Arguments  
 **expression**  
  
 Is a constant, column name, or function, and any combination of arithmetic operators. MIN can be used with bigint and float columns. Aggregate functions and subqueries are not permitted.  
  
## Return Types  
 Returns a value same as expression.  
  
## General Remarks  
 If payload schema was not defined with CREATE TABLE statement and type of the result expression is unknown at query compilation time, return value will have float type.  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS OutTime, TollId, MIN (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  
