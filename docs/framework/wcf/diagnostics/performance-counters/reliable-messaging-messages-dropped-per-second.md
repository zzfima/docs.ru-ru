---
title: "Количество удаленных сообщений, передаваемых по надежным каналам, в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Количество удаленных сообщений, передаваемых по надежным каналам, в секунду
Имя счетчика: Reliable Messaging Sessions Dropped Per Second.  
  
## Описание  
 Общее количество надежных сообщений, которые были отклонены в данной службе в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)