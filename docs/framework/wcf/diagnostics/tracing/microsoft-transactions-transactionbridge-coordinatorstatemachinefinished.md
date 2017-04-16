---
title: "Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
Конечный автомат для перечисления координаторов перешел в конечное состояние.  
  
## Описание  
 Регистрируется, если локальный диспетчер транзакция полагает, что перечисление координаторов более высокого уровня завершило обработку 2pc.Результатом перечисления может быть значение Committed, Aborted или Forgotten.Кроме того, это событие регистрируется, если на этапе подготовки локальный диспетчер транзакций голосует за режим ReadOnly.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)