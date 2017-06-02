---
title: "Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Истекло время ожидания службой протокола WS\-AT ответа на результативное сообщение от неустойчивого участника.При возвращении участника результат транзакции будет поставлен под сомнение.  
  
## Описание  
 Трассируется, когда неустойчивый участник принял решение зафиксировать или прервать транзакцию, однако не ответил на сообщение Commit или Rollback в течение заданного времени.  
  
## Устранение неполадок  
 Убедитесь, что все неустойчивые участники имеют возможность ответить в течение заданного времени.Период времени по умолчанию — 180 секунд.Если этого недостаточно, увеличьте значение политики таймера `VolatileOutcomeDelay` для протокола WS\-AT.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)