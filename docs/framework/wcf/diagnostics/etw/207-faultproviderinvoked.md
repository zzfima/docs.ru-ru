---
title: "207 - FaultProviderInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 207 - FaultProviderInvoked
## Свойства  
  
|||  
|-|-|  
|Идентификатор|207|  
|Ключевые слова|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается после вызова `FaultProvider`.  
  
## Сообщение  
 Диспетчер вызвал FaultProvider типа «%1» с исключением типа «%2».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|TypeName|`xs:string`|Имя CLR FullName типа вызванного инспектора `FaultProvider`.|  
|ExceptionTypeName|`xs:string`|Имя CLR FullName исключения, обработанного `FaultProvider`.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.  Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».  «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|