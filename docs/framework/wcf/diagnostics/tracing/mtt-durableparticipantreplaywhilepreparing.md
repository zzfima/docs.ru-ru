---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 830a55a9f82c38b0a58783c49d3f58f64d5afdb4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Служба протокола WS-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение. Поэтому транзакция была прервана.  
  
## <a name="description"></a>Описание  
 Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки. Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Получение этого сообщения об ошибке может указывать на то, что постоянный участник (включая подчиненные диспетчеры транзакций) был восстановлен после ошибки, однако ему не известен точный результат транзакции, и он запросил ее состояние.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
