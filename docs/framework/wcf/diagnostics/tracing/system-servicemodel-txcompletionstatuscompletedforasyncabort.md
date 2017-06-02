---
title: "System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
Заданная транзакция для заданной операции завершена в результате асинхронного прерывания.  
  
## Описание  
 Текущая транзакция была прервана, потому что другой участник спровоцировал прерывание, истекло время ожидания или из\-за внутренней ошибки участника транзакции.  
  
## Устранение неполадок  
 Если это прерывание произошло неожиданно, проверьте системные журналы, чтобы определить истинную причину прерывания.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)