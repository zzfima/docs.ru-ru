---
title: "107 ― BookmarkResumptionRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 107 ― BookmarkResumptionRecord
## Свойства  
  
|||  
|-|-|  
|Id|107|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись BookmarkResumptionRecord.  
  
## Message  
 TrackRecord\=BookmarkResumptionRecord, InstanceId\=%1, RecordNumber\=%2,EventTime\=%3, Name\=%4, SubInstanceID\=%5, OwnerActivityName\=%6, OwnerActivityId\=%7, OwnerActivityInstanceId\=%8, OwnerActivityTypeName\=%9, Annotations\=%10, ProfileName\=%11  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Name|xs:string|Имя возобновленной закладки.|  
|SubInstanceID|xs:GUID|Идентификатор области закладки.|  
|OwnerActivityName|xs:string|Имя действия закладки.|  
|OwnerActivityId|xs:string|Идентификатор действия закладки.|  
|OwnerActivityInstanceId|xs:string|Идентификатор экземпляра действия закладки.|  
|OwnerActivityTypeName|xs:string|Тип действия закладки.|  
|Annotations|xs:string|Заметки, добавленные к этому событию.Значения хранятся в xml\-элементе в формате \<элементы\>\< имя элемента \= "annotationName" тип\="System.String"\>annotationValue\<\/элемент\>\<\/элементы\>.Если ни одной заметки не указано, строка содержит \<элементы\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы\>...\<\/элементы\>.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб\-сайтах, это поле служит уникальным идентификатором службы в веб\-иерархии.Формат определяется следующим образом: «имя\_веб\-сайта виртуальный\_путь\_приложения&#124;виртуальный\_путь\_службы&#124;имя\_службы». Пример: «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService»|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|