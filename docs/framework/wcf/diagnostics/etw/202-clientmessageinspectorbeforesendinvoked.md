---
title: "202 — ClientMessageInspectorBeforeSendInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 202 — ClientMessageInspectorBeforeSendInvoked
## Свойства  
  
|||  
|-|-|  
|ID|202|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается после того, как модель службы вызывает метод `BeforeSendRequest` для инспектора сообщений клиента.  
  
## Message  
 Диспетчер вызвал BeforeSendRequest для ClientMessageInspector типа «%1».  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|TypeName|`xs:string`|Имя CLR FullName типа вызванного инспектора.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|