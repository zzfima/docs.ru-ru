---
title: "Согласование безопасности и тайм-ауты | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Согласование безопасности и тайм-ауты
Когда клиенты и службы проходят проверку подлинности, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает режим, в котором в ходе проверки подлинности осуществляется согласование учетных данных.В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту.Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>.Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла «запрос\-ответ».Если согласование завершается за один цикл, время ожидания не используется.  
  
## См. также  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 [Как установить максимальную разницу в показаниях часов](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)