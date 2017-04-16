---
title: "System.ServiceModel.TxCompletionStatusAbortedOnSessionClose | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
Указанная транзакция прервана, поскольку она была незавершенной на момент закрытия сеанса и атрибуту TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute задано значение "false".  
  
## Описание  
 Трассируется, если текущий активный сеанс был закрыт, транзакция не была завершена и TransactionAutoCompleteOnSessionClose имеет значение `false`.  
  
## Устранение неполадок  
 Эта трассировка указывает о потенциальной ошибке в приложении, наличие которой требуется проверить.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)