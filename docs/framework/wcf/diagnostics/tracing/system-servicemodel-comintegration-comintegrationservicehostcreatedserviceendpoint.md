---
title: "System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Не удается переместить или удалить сообщение.  
  
## Описание  
 Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.  
  
 Сообщения MSMQ используются [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(при использовании с привязкой NetMsmqBinding или MsmqIntegrationBinding\). Эта трассировка относится к выбранному значению свойства `ReceiveErrorHandling` привязки NetMsmqBinding или MsmqIntegrationBinding.  
  
 Эта трассировка не указывает на общий сбой системы.  Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения.  Дополнительные сведения о том, каким образом сообщения становятся подозрительными и как настроить службу для их правильной обработки, см. в разделе [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546).  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)