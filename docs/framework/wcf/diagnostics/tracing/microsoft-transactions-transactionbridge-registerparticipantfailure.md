---
title: "Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
Службе протокола WS\-AT не удалось зарегистрировать участника для протокола управления.  
  
## Описание  
 Отслеживается, обнаруживает ли MSDTC недопустимый запрос на регистрацию.Это может происходить из\-за множественных запросов на регистрацию завершения и внутренних ошибок.  
  
## Устранение неполадок  
 Не пытайтесь зарегистрировать завершение несколько раз.Проверьте строку состояния в сообщении трассировки, чтобы определить, имеются ли элементы, с которыми можно произвести какие\-либо действия.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)