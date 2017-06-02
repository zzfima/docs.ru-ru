---
title: "System.ServiceModel.Channels.MsmqPoisonMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqPoisonMessageRejected
Подозрительное сообщение отклонено.  
  
## Описание  
 Указывает, что было обнаружено и отклонено подозрительное сообщение.Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`.Отклоненное сообщение возвращается в [очередь недоставленных сообщений](http://go.microsoft.com/fwlink/?LinkId=99544) отправителя.  
  
 Дополнительные сведения о том, каким образом сообщения становятся поврежденными и как настроить службу для правильной их обработки, см. в разделе [Обработка поврежденных сообщений](http://go.microsoft.com/fwlink/?LinkId=99546).Дополнительные сведения о том, что представляет собой отклоненное сообщение в MSMQ, см. в разделе [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548).  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Обработка поврежденных сообщений](http://go.microsoft.com/fwlink/?LinkId=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)