---
title: "Конечная точка: количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Конечная точка: количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
Имя счетчика: Reliable Messaging Sessions Faulted Per Second.  
  
## Описание  
 Количество сеансов надежного обмена сообщениями, в которых произошел сбой на этой конечной точке в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)