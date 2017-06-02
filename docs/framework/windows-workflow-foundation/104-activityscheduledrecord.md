---
title: "104 ― ActivityScheduledRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 104 ― ActivityScheduledRecord
## Свойства  
  
|||  
|-|-|  
|Id|104|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается участником отслеживания ETW, когда действие в экземпляре рабочего процесса создает запись ActivityScheduledRecord.  
  
## Message  
 TrackRecord\=ActivityScheduledRecord, InstanceId\=%1, RecordNumber\=%2, EventTime\=%3, Name \=%4, ActivityId\=%5, ActivityInstanceId\=%6, ActivityTypeName\=%7, ChildActivityName\=%8, ChildActivityId\=%9, ChildActivityInstanceId\=%10, ChildActivityTypeName\=%11, Annotations\=%12, ProfileName\=%13  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Name|xs:string|Имя действия, которое запланировало дочернее действие.|  
|ActivityId|xs:string|Идентификатор действия, которое запланировало дочернее действие.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра действия, которое запланировало дочернее действие.|  
|ActivityTypeName|xs:string|Тип действия, запросившего операцию отмены.|  
|ChildActivityName|xs:string|Имя запланированного действия.|  
|ChildActivityId|xs:string|Идентификатор запланированного действия.|  
|ChildActivityInstanceId|xs:string|Идентификатор экземпляра запланированного действия.|  
|ChildActivityTypeName|xs:string|Тип запланированного действия.|  
|Annotations|xs:string|Заметки, добавленные к этому событию.Значения хранятся в xml\-элементе в формате \<элементы\>\< имя элемента \= "annotationName" тип\="System.String"\>annotationValue\<\/элемент\>\<\/элементы\>.Если ни одной заметки не указано, строка содержит \<элементы\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы\>...\<\/элементы\>.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб\-сайтах, это поле служит уникальным идентификатором службы в веб\-иерархии.Формат определяется следующим образом: «имя\_веб\-сайта виртуальный\_путь\_приложения&#124;виртуальный\_путь\_службы&#124;имя\_службы». Пример: «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService»|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|