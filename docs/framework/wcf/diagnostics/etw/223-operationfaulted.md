---
title: "223 — OperationFaulted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 223 — OperationFaulted
## Свойства  
  
|||  
|-|-|  
|ID|223|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Level|Warning|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие вызывается в том случае, если при вызове `OperationInvoker` модели службы по умолчанию обнаружено исключение, производное от `FaultException`.  
  
## Message  
 Метод «%1» вызывал исключение FaultException после того, как был вызван OperationInvoker.Длительность вызова метода составила «%2» мс.  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|MethodName|`xs:string`|Имя CLR метода, который был вызван `OperationInvoker`.|  
|Duration|`xs:long`|Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|