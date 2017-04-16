---
title: "Количество сообщений из очереди, отклоненных за секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Количество сообщений из очереди, отклоненных за секунду
Имя счетчика: Queued Messages Rejected Per Second.  
  
## Описание  
 Количество сообщений, отклоненных транспортом очередей этой службы за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)