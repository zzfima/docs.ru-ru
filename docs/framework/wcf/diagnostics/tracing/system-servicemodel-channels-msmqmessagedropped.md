---
title: "System.ServiceModel.Channels.MsmqMessageDropped | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMessageDropped
Сообщение удалено из очереди MSMQ.  
  
## Описание  
 Данная трассировка указывает, что сообщение MSMQ было удалено.Сообщения MSMQ могут быть удалены, если [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(при использовании либо с классом NetMsmqBinding, либо с классом MsmqIntegrationBinding\) не удается их обработать.Такие сообщения считаются подозрительными.  
  
 Подозрительное сообщение удаляется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.  
  
 Дополнительные сведения о том, каким образом сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546).  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546)