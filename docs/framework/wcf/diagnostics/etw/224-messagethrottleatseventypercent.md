---
title: "224 — MessageThrottleAtSeventyPercent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 224 — MessageThrottleAtSeventyPercent
## Свойства  
  
|||  
|-|-|  
|ID|224|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Level|Warning|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 При превышении одного из основных ограничителей службы создается событие `MessageThrottleExceeded`.Если всплеск активности уменьшился и текущее значение ограничителя составляет 70 процентов от текущего предела, то создается это событие.Обратите внимание, что это событие создается только один раз при замедлении активности.Если текущее значение находится вблизи отметки 70 процентов \(например, 70, 69, 70, 71, 69\), то только первое значение 70 процентов приводит к созданию события.После возникновения события все последующие превышения предела регулирования приводят к возникновению события `MessageThrottleExceeded`.  
  
## Message  
 Предел ограничителя %1 из %2 находится на отметке 70%%.  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Throttle Name|`xs:string`|Имя превышенного ограничителя.`MaxConcurrentCalls`, `MaxConcurrentInstances` либо `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Заданный в данный момент предел ограничителя.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|