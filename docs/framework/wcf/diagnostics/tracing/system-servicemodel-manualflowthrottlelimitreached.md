---
title: "System.ServiceModel.ManualFlowThrottleLimitReached | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.ManualFlowThrottleLimitReached
System.ServiceModel.ManualFlowThrottleLimitReached  
  
## Описание  
 Система достигла предела, заданного ограничителем ManualFlowControlLimit.Значение регулировки, в зависимости от конкретного случая, может быть изменено с помощью изменения свойства ManualFlowControlLimit либо в классе ServiceHost, либо в классе InstanceContext.  
  
 Такая трассировка выдается, если ручной предел управления потоками первоначально снижается до 0.Последующие изменения до 0 не трассируются.Предел управления потоками в контексте экземпляра трассируется один раз для каждого контекста.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)