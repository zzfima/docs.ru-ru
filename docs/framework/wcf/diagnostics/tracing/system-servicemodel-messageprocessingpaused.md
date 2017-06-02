---
title: "System.ServiceModel.MessageProcessingPaused | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## Описание  
 При обработке сообщения произошло переключение потоков.  
  
 Обработка сообщения может быть приостановлена по следующим причинам:  
  
-   ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.  
  
-   Транзакция разрешена; служба обрабатывает другую транзакцию.  
  
-   Контекст синхронизации устарел.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)