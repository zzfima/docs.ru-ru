---
title: "218 — ClientOperationCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 218 — ClientOperationCompleted
## Свойства  
  
|||  
|-|-|  
|ID|218|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается клиентом сразу после завершения операции.Для односторонних операций оно создается сразу после успешной отправки сообщения.Для операций типа «запрос\-ответ» оно создается после получения ответа.  
  
## Message  
 Клиент завершил выполнение действия «%1», связанного с контрактом «%2».Сообщение было отправлено «%3».  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Заголовок действия SOAP исходящего сообщения.|  
|Contract Name|`xs:string`|Имя контракта.Пример: ICalculator.|  
|Destination|`xs:string`|Адрес конечной точки службы, которой было отправлено сообщение.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|