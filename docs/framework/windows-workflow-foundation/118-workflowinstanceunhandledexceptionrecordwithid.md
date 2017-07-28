---
title: "118 - WorkflowInstanceUnhandledExceptionRecordWithId | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ce4b193-e141-4cc4-86a3-2e8c984c110d
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 118 - WorkflowInstanceUnhandledExceptionRecordWithId
## Свойства  
  
|||  
|-|-|  
|Идентификатор|118|  
|Ключевые слова|HealthMonitoring, WFTracking|  
|Уровень|Ошибка|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceUnhandledExceptionRecord.  
  
## Сообщение  
 TrackRecord \= WorkflowInstanceUnhandledExceptionRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, SourceName \= %5, SourceId \= %6, SourceInstanceId \= %7, SourceTypeName\=%8, Exception\=%9, Annotations\= %10, ProfileName \= %11, WorkflowDefinitionIdentity \= %12  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|ActivityDefinitionId|xs:string|Имя корневого действия в рабочем процессе.|  
|SourceName|xs:string|Имя исходного действия, в котором произошла ошибка, что привело к созданию исключения unhandledException.|  
|SourceId|xs:string|Идентификатор исходного действия, в котором произошла ошибка.|  
|SourceInstanceId|xs:string|Идентификатор экземпляра исходного действия, в котором произошла ошибка.|  
|SourceTypeName|xs:string|Имя типа исходного действия, в котором произошла ошибка, что привело к созданию исключения unhandledException.|  
|Исключение|xs:string|Данные необработанного исключения.|  
|Состояние|xs:string|Текущее состояние рабочего процесса.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML\-элементе в формате \<items\>\< item name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\>.  Если ни одной заметки не указано, строка содержит \<items\/\>.  Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.  Если размер события превышает пределы трассировки событий Windows, событие усекается путем отбрасывания заметок и замены значения заметок значением \<items\>...\<\/items\>.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|WorkflowDefinitionIdentity|xs:string|Идентификатор определения рабочего процесса|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|