---
title: "ParticipantRecoveryLogEntryCorrupt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# ParticipantRecoveryLogEntryCorrupt
Идентификатор: 138  
  
 Важность: ошибка  
  
 Категория: TransactionBridge  
  
## Описание  
 Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.Эта ошибка может привести к потере данных.В событии указаны идентификатор транзакции, данные о восстановлении \(в кодировке Base64\), исключение, имя и ИД процесса.  
  
## См. также  
 [Ведение журнала событий](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Общие справочные сведения о событиях](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)