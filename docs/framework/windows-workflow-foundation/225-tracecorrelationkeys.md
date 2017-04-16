---
title: "225 — TraceCorrelationKeys | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 225 — TraceCorrelationKeys
## Свойства  
  
|||  
|-|-|  
|ID|225|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается, если в качестве службы рабочего процесса используется корреляция на основе содержимого.Оно содержит ключи, применяемые для корреляции сообщения с экземпляром.  
  
## Message  
 Вычисленный ключ корреляции «%1» с использованием значений «%2» в родительской области «%3».  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Instance Key|`xs:GUID`|Ключ, созданный из значений корреляции.|  
|Values|`xs:string`|Значения, использованные для вычисления ключа экземпляра корреляции.|  
|Parent Scope|`xs:string`||  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле служит уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|