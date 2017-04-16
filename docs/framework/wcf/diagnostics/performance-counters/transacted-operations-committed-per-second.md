---
title: "Количество зафиксированных операций с поддержкой транзакций в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Количество зафиксированных операций с поддержкой транзакций в секунду
Имя счетчика: Количество зафиксированных операций с поддержкой транзакций в секунду.  
  
## Описание  
 Количество транзакционных операций, зафиксированных в этой службе за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)