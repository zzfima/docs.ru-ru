---
title: "Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a174bbf5-0ffe-4fda-969d-e7fbd1996123
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata
Служба протокола WS\-Atomic Transaction получила от координатора сообщение RegisterResponse, в котором содержится ссылка на конечную точку с недействительными или несовместимыми метаданными.  
  
## Описание  
 Отслеживается, когда локальный диспетчер транзакций выполняет попытку регистрации посредством диспетчера транзакций более высокого уровня и последний возвращает недействительный адрес в сообщении RegisterResponse.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)