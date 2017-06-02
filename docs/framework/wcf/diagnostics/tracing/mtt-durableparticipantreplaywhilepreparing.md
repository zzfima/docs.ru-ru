---
title: "Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Служба протокола WS\-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение.Поэтому транзакция была прервана.  
  
## Описание  
 Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки.Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.  
  
## Устранение неполадок  
 Получение этого сообщения об ошибке может указывать на то, что постоянный участник \(включая подчиненные диспетчеры транзакций\) был восстановлен после ошибки, однако ему не известен точный результат транзакции, и он запросил ее состояние.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)