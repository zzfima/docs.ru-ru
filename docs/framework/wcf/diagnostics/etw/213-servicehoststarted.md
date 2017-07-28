---
title: "213 — ServiceHostStarted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 213 — ServiceHostStarted
## Свойства  
  
|||  
|-|-|  
|ID|213|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost|  
|Level|LogAlways|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается при запуске службы, размещенной на веб\-сервере.Обычно это происходит, когда служба активируется сообщением.Это также может произойти, если служба настроена для автоматического запуска.  
  
## Message  
 ServiceHost запущена: '%1'.  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Имя типа службы|`xs:string`|Имя CLR FullName типа реализации службы.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле служит уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|