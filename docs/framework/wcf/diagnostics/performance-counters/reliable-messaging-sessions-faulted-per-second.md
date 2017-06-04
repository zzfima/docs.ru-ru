---
title: "Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
Имя счетчика: Reliable Messaging Sessions Faulted Per Second.  
  
## Описание  
 Количество надежных сессий обмена сообщениями этой службы, в которых произошел сбой в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)