---
title: "105 ― FaultPropagationRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 105 ― FaultPropagationRecord
## Свойства  
  
|||  
|-|-|  
|Id|105|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Level|Warning|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается участником отслеживания ETW, когда действие внутри рабочего процесса создает запись FaultPropagationRecord.  
  
## Message  
 TrackRecord \= FaultPropagationRecord, InstanceID\=%1, RecordNumber\=%2, EventTime\=%3, FaultSourceActivityName\=%4, FaultSourceActivityId\=%5, FaultSourceActivityInstanceId\=%6, FaultSourceActivityTypeName\=%7, FaultHandlerActivityName\=%8,  FaultHandlerActivityId \= %9, FaultHandlerActivityInstanceId \=%10, FaultHandlerActivityTypeName\=%11, Fault\=%12, IsFaultSource\=%13, Annotations\=%14, ProfileName \= %15  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|FaultSourceActivityName|xs:string|Имя действия, создавшего ошибку.|  
|FaultSourceActivityId|xs:string|Идентификатор действия, создавшего ошибку.|  
|FaultSourceActivityInstanceId|xs:string|Идентификатор экземпляра действия, создавшего ошибку.|  
|FaultSourceActivityTypeName|xs:string|Тип действия, создавшего ошибку.|  
|FaultHandlerActivityName|xs:string|Отображаемое имя действия обработчика ошибок.|  
|FaultHandlerActivityId|xs:string|Идентификатор действия обработчика ошибок.|  
|FaultHandlerActivityInstanceId|xs:string|Идентификатор экземпляра действия обработчика ошибок.|  
|FaultHandlerActivityTypeName|xs:string|Тип действия обработчика ошибок.|  
|Fault|xs:string|Сведения об ошибке.|  
|IsFaultSource|xs:unsignedByte|Указывает, если было событие создано источником ошибки.|  
|Annotations|xs:string|Заметки, добавленные к этому событию.Значения хранятся в xml\-элементе в формате \<элементы\>\< имя элемента \= "annotationName" тип\="System.String"\>annotationValue\<\/элемент\>\<\/элементы\>.Если ни одной заметки не указано, строка содержит \<элементы\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы\>...\<\/элементы\>.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб\-сайтах, это поле служит уникальным идентификатором службы в веб\-иерархии.Формат определяется следующим образом: «имя\_веб\-сайта виртуальный\_путь\_приложения&#124;виртуальный\_путь\_службы&#124;имя\_службы». Пример: «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService»|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|