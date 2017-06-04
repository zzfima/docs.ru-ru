---
title: "Количество подозрительных сообщений из очереди в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Количество подозрительных сообщений из очереди в секунду
Имя счетчика: Queued Poison Messages Per Second.  
  
## Описание  
 Количество сообщений, отмеченных как подозрительные транспортом очередей в этой службе в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)