---
title: "Конечная точка: количество удаленных сообщений, передаваемых по надежным каналам, в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Конечная точка: количество удаленных сообщений, передаваемых по надежным каналам, в секунду
Имя счетчика: Reliable Messaging Sessions Dropped Per Second.  
  
## Описание  
 Общее количество сообщений системы надежного обмена сообщениями, которое было отклонено в данной конечной точке в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по указанной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)