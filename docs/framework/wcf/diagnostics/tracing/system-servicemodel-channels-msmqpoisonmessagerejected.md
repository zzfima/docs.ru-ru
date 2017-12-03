---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55ae2ed6ac8a02218fa4c13063fb8b8a8c474fd8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
Подозрительное сообщение отклонено.  
  
## <a name="description"></a>Описание  
 Указывает, что было обнаружено и отклонено подозрительное сообщение. Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`. Отклоненные сообщение доставляется отправителя [очереди недоставленных сообщений](http://go.microsoft.com/fwlink/?LinkId=99544).  
  
 В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkId=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки. В разделе [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) для получения дополнительных сведений о означает отклоненных сообщений в MSMQ.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)
