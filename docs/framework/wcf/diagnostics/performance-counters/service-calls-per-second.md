---
title: "Служба: количество вызовов в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Служба: количество вызовов в секунду
Имя счетчика: Calls Per Second.  
  
## Описание  
 Количество вызовов данной службы в секунду.  
  
 Этот счетчик производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\). Таким образом, числитель \(N\) представляет число операций, выполненных за последний интервал измерения, знаменатель \(D\) представляет число импульсов, прошедших за последний интервал наблюдения, а F — частота импульсов.