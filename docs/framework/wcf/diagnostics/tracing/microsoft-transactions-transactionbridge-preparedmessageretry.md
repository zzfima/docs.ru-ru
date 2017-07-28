---
title: "Microsoft.Transactions.TransactionBridge.PreparedMessageRetry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
Координатору, который не отвечает, было повторно отправлено сообщение готовности.  
  
## Описание  
 Трассируется, если локальному диспетчеру транзакций потребовалось повторно отправить сообщение готовности \("Prepared"\) вышестоящему координатору, так как за заданное время не был получен отклик.  
  
## Устранение неполадок  
 Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.Обе проблемы значительно снижают пропускную способность транзакций в системе.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)