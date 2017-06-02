---
title: "Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
Сбой службы протокола WS\-AT при отправке сообщения Register своему координатору  
  
## Описание  
 Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager по причине невозможности отправить сообщение.  
  
## Устранение неполадок  
 Проверить сообщение трассировки на исключение, приводящее к сбою отправки сообщения  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)