---
title: "205 — OperationInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 205 — OperationInvoked
## Свойства  
  
|||  
|-|-|  
|ID|205|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается непосредственно перед тем, как `OperationInvoker` по умолчанию модели службы начнет вызов метода.  
  
## Message  
 OperationInvoker вызвал метод «%1».Сведения о вызывающем объекте: «%2».  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Method name|`xs:string`|Имя CLR метода, который был вызван `OperationInvoker`.|  
|Caller Information|`xs:string`|IP\-адрес и номер порта клиента в формате «IPAddress:PortNumber».Эти два значения извлекаются из свойства сообщения «System.ServiceModel.Channels.RemoteEndpointMessageProperty» в контексте операции.Следует отметить, что для привязок, отличных от TCP, это значение `null`.|  
|HostReference|`xs:string`|Для служб, размещенных на веб\-узле, это поле является уникальным идентификатором службы в веб\-иерархии.Ее формат определяется следующим образом: «имя веб\-сайта виртуальный путь приложения&#124;виртуальный путь службы&#124;ServiceName».«веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService».|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|