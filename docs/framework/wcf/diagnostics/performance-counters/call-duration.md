---
title: "Длительность обработки вызова | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4973ec3-3c66-4c0b-b5d0-294b62c83f7d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Длительность обработки вызова
Имя счетчика: Call Duration  
  
## Описание  
 Средняя длительность вызовов этой операции.  Средняя длительность вычисляется по следующей формуле: \(N1\-N0\)\/\(D1\-D0\).  
  
> [!WARNING]
>  При использовании в асинхронной службе WCF счетчик Call Duration всегда возвращает \-1.  
  
## См. также  
 [PERF\_AVERAGE\_TIMER](http://go.microsoft.com/fwlink/?LinkID=95015)