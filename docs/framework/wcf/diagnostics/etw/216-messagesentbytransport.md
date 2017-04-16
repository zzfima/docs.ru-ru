---
title: "216 — MessageSentByTransport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 216 — MessageSentByTransport
## Свойства  
  
|||  
|-|-|  
|ID|216|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие возникает при отправке сообщения транспортом на основе TCP.Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта.Это может быть вызвано особенностями инфраструктуры \(и требования безопасности — хороший пример\).Таким образом, количество событий **MessageSentByTransport** может оказаться разным и зависит от привязки службы и ее настроек.  
  
## Сообщение  
 Транспорт отправил сообщение «%1».  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|DestinationAddress|`xs:string`|Адрес, на который было отправлено сообщение запроса.|  
|HostReference|xs:string|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|