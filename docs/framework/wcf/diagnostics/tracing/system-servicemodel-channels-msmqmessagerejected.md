---
title: "System.ServiceModel.Channels.MsmqMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMessageRejected
MSMQ отклонила сообщение.  
  
## Описание  
 Данная трассировка показывает, что сообщение MSMQ было отклонено.  
  
 Сообщения MSMQ могут быть отклонены, если [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(используемый либо с классом NetMsmqBinding, либо с классом MsmqIntegrationBinding\) не способен их обработать.Такие сообщения считаются подозрительными.Подозрительное сообщение отклоняется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Reject`.Отклоненное сообщение возвращается в [очередь недоставленных сообщений отправителя](http://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Дополнительные сведения о том, каким образом сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546).  
  
 Подробнее о значении отклоненных сообщений в MSMQ см. [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548).  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)