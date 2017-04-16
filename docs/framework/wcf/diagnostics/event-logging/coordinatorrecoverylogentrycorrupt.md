---
title: "CoordinatorRecoveryLogEntryCorrupt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# CoordinatorRecoveryLogEntryCorrupt
Идентификатор: 139  
  
 Важность: ошибка  
  
 Категория: TransactionBridge  
  
## Описание  
 Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.Эта ошибка может привести к потере данных.В событии указаны идентификатор транзакции, данные о восстановлении \(в кодировке Base64\), исключение, имя и ИД процесса.  
  
## См. также  
 [Ведение журнала событий](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Общие справочные сведения о событиях](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)