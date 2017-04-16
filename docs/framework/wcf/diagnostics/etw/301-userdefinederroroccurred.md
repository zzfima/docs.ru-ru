---
title: "301 — UserDefinedErrorOccurred | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 301 — UserDefinedErrorOccurred
## Свойства  
  
|||  
|-|-|  
|ID|301|  
|Keywords|Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Level|Error|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается в пользовательском коде.Разработчики могут создать это событие, если определенная пользователем ошибка возникает в принадлежащей им службе.Это можно сделать при помощи API\-интерфейсов <xref:System.Diagnostics.Eventing>.Помимо этого, есть образец WCF, который включает этот API\-интерфейс и показывает, как правильно создать это событие.  
  
## Message  
 Имя: «%1», Ссылка: «%2», Полезные данные: %3  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Name|`xs:string`|Определенное пользователем имя события.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|Payload|`xs:string`|Определенные пользователем полезные данные события.|