---
title: "Надежные сеансы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Windows Communication Foundation, sessions and instances"
  - "WCF, sessions and instances"
  - "sessions and instances [WCF]"
helpviewer_keywords: 
  - "экземпляры [WCF]"
  - "сеансы [WCF]"
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Надежные сеансы
В этом разделе описано, что такое надежный сеанс [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], для чего он используется, как и когда его следует использовать, какие конфигурации привязки поддерживают его, а также приведены ссылки на рекомендации.В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.  
  
 Надежный сеанс [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует, что сообщения, которыми обмениваются конечные точки, передаются по протоколу SOAP или через транспортные посредники и что они доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.  
  
 Для применения надежных сеансов в приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] следует использовать предоставляемые системой привязки в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которые по умолчанию поддерживают надежные сеансы, либо можно создать собственную пользовательскую привязку, которая бы поддерживала такие сеансы.  
  
## В этом подразделе  
 [Общие сведения о надежных сеансах](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 Описание надежных сеансов, ситуаций, в которых они используются, различных привязок, которые поддерживают надежные сеансы, и принципы их работы.  
  
 [Как обмениваться сообщениями в рамках надежного сеанса](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)  
 Описание процесса создания надежного сеанса через протокол HTTP с помощью пользовательской привязки, заданной в конфигурации.  
  
 [Как защитить сообщения с помощью надежных сеансов](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)  
 Обеспечение защиты надежного сеанса.  
  
 [Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)  
 Создание надежного сеанса через протокол HTTPS.  
  
 [Рекомендации по работе с надежными сеансами](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)  
 Описание некоторых рекомендаций по использованию надежных сеансов.  
  
## Ссылка  
 <xref:System.ServiceModel.ReliableSession>  
  
## См. также  
 [Очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)