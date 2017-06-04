---
title: "WCF и WebSockets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF и WebSockets
В .NET Framework версии 4.5 добавлена поддержка WebSockets в службах Windows Communication Foundation.WebSockets — это эффективная, основанная на стандартах технология, обеспечивающая двусторонний обмен сообщениями через стандартные HTTP\-порты 80 и 443.Использование стандартных HTTP\-портов позволяет WebSockets устанавливать связь по сети через посредников.Были добавлены две стандартные привязки для поддержки обмена данными через транспорт WebSocket.<xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>.Специальные параметры WebSockets можно настроить в элементе <xref:> System.ServiceModel.Channels.HttpTransportBinding?qualifyHint=False&autoUpgrade=True с помощью свойства <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A>.  
  
## В этом подразделе  
 [Использование NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Описывает <xref:System.ServiceModel.NetHttpBinding> и его настройку.  
  
 [Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Описывает процесс создания службы WCF, обменивающейся данными через Websockets.  
  
## Ссылка  
  
## Связанные подразделы