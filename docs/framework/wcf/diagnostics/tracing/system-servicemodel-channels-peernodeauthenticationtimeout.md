---
title: "System.ServiceModel.Channels.PeerNodeAuthenticationTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f294ee94-be83-426c-b40d-6e8a4e5e987c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.Channels.PeerNodeAuthenticationTimeout
Подтверждение безопасности не было успешно завершено в течение заданного времени.  
  
## Описание  
 Эта трассировка возникает при попытке установить безопасное соединение с соседним узлом.  
  
## Устранение неполадок  
 Обеспечьте, чтобы все соседние узлы имели соответствующие учетные данные безопасности и отвечали на все сообщения менее чем за минуту.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)