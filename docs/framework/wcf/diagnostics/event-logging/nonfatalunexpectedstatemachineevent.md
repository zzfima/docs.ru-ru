---
title: "NonFatalUnexpectedStateMachineEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfa37c10-cf1b-4325-b756-6ef200606510
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# NonFatalUnexpectedStateMachineEvent
Идентификатор: 148  
  
 Важность: ошибка  
  
 Категория: TransactionBridge  
  
## Описание  
 Это событие указывает, что конечный автомат попытался обработать непредвиденное событие.  Событие не считается неустранимым.  В событии указаны идентификатор транзакции, конечный автомат, текущее состояние, журнал, имя события, сведения о событии, имя процесса и ИД процесса.  
  
## См. также  
 [Ведение журнала событий](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Общие справочные сведения о событиях](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)