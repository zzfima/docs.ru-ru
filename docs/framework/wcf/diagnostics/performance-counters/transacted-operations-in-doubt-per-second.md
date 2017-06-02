---
title: "Количество операций с поддержкой транзакций с сомнительным результатом в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Количество операций с поддержкой транзакций с сомнительным результатом в секунду
Имя счетчика: Количество операций с поддержкой транзакций с сомнительным результатом в секунду.  
  
## Описание  
 Количество операций с поддержкой транзакций, имеющих сомнительный результат, возникающих в данной службе за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по приведенной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)