---
title: "System.ServiceModel.Channels.ConnectionPoolCloseException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.Channels.ConnectionPoolCloseException
При закрытии подключений в этом пуле подключений возникло исключение.  
  
## Описание  
 Эта трассировка уровня ошибки указывает, что возникла ошибка при закрытии пулов подключений, используемых функцией пулов подключений [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].Эта ошибка может быть вызвана тем, что не удалось закрыть подключение \(или набор подключений\) из пула в течение времени ожидания \(CloseTimeout\).При выдаче этого исключения все оставшиеся незакрытые подключения из этого пула прерываются. Незакрытые подключения из других пулов оставляются.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)