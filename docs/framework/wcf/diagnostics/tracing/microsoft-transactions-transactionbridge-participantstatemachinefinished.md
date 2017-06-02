---
title: "Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
Конечный автомат для перечисления участников перешел в конечное состояние.  
  
## Описание  
 Трассируется, когда перечисление подчиненных участников завершило обработку 2pc.Результатом для перечисления может быть значение Committed или Aborted.Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)