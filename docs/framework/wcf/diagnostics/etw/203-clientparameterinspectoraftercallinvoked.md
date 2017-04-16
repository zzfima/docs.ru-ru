---
title: "203 - ClientParameterInspectorAfterCallInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 203 - ClientParameterInspectorAfterCallInvoked
## Свойства  
  
|||  
|-|-|  
|Идентификатор|203|  
|Ключевые слова|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается после того, как модель службы вызывает метод `AfterCall` для инспектора параметров клиента.  
  
## Сообщение  
 Диспетчер вызвал «AfterCall» для ClientParameterInspector типа «%1».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|TypeName|`xs:string`|Имя CLR FullName типа вызванного инспектора.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.  Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».  «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|