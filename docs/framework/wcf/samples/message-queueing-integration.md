---
title: "Интеграция очередей сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d2b47a0-5d51-45b5-9633-b62e064e8ea4
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Интеграция очередей сообщений
В этом разделе содержатся образцы, которые демонстрируют интеграцию службы очередей сообщений с [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## В этом подразделе  
 [Передача сообщений из службы очередей сообщений в приложение Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 Показано, как приложение службы очередей сообщений \(MSMQ\) может отправлять сообщения MSMQ службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Пользовательское демультиплексирование](../../../../docs/framework/wcf/samples/custom-demux.md)  
 Показано, как сопоставлять заголовки сообщений MSMQ с различными операциями служб, чтобы службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], использующие <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>, не были ограничены использованием одной операции службы.  
  
 [Отправка сообщений из приложения Windows Communication Foundation в службу очередей сообщений](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 Показан способ отправки сообщения приложению очереди сообщений \(MSMQ\) при помощи приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Корреляция сообщений](../../../../docs/framework/wcf/samples/message-correlation.md)  
 Демонстрирует, как приложение очереди сообщений \(MSMQ\) может отправлять сообщения MSMQ службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и как можно коррелировать сообщения между приложениями отправителя и получателя в сценарии «запрос\-ответ».