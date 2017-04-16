---
title: "102 ― WorkflowInstanceAbortedRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bde4378d-4eea-4907-aaf2-c1a2bc770a37
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 102 ― WorkflowInstanceAbortedRecord
## Свойства  
  
|||  
|-|-|  
|Id|102|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Level|Warning|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceAbortedRecord.  
  
## Message  
 TrackRecord\=WorkflowInstanceAbortedRecord, InstanceId\=%1, RecordNumber\=%2, EventTime\=%3, ActivityDefinitionId\=%4, Reason\=%5, Annotations\=%6, ProfileName\=%7  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|ActivityDefinitionId|xs:string|Имя корневого действия в рабочем процессе.|  
|Reason|xs:string|Причина, по которой был прерван рабочий процесс.|  
|Annotations|xs:string|Заметки, добавленные к этому событию.Значения хранятся в xml\-элементе в формате \<элементы\>\< имя элемента \= "annotationName" тип\="System.String"\>annotationValue\<\/элемент\>\<\/элементы\>.Если ни одной заметки не указано, строка содержит \<элементы\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы\>...\<\/элементы\>.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб\-сайтах, это поле служит уникальным идентификатором службы в веб\-иерархии.Формат определяется следующим образом: «имя\_веб\-сайта виртуальный\_путь\_приложения&#124;виртуальный\_путь\_службы&#124;имя\_службы». Пример: «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService»|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|