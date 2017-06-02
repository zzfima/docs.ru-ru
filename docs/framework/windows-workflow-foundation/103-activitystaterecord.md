---
title: "103 ― ActivityStateRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 103 ― ActivityStateRecord
## Свойства  
  
|||  
|-|-|  
|Id|103|  
|Keywords|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Level|Information|  
|Channel|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие выдается участником отслеживания ETW, когда действие в экземпляре рабочего процесса создает запись ActivityStateRecord.  
  
## Message  
 TrackRecord \= ActivityStateRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, State \= %4, Name\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Arguments\=%9, Variables\=%10, Annotations\=%11, ProfileName \= %12  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|State|xs:string|Состояние действия.|  
|Name|xs:string|Отображаемое имя действия, выдавшего событие.|  
|ActivityId|xs:string|Идентификатор создающего действия.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра создающего действия.|  
|ActivityTypeName|xs:string|Имя типа выдающего действия.|  
|Arguments|xs:string|Аргументы, которые были отслежены вместе с этим событием.Значения хранятся в xml\-элементе в формате \<items\>\<\> item  name \= "argumentName" type\="System.String"\<argumentValue\>\<\/item\>\/items.Если аргументы не отслеживались, строка содержит значение \<items\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы\>...\<\/элементы\>.Следующие типы сохраняются со своим значением, возвращаемым при помощи метода ToString\(\); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Variables|xs:string|Переменные, которые были отслежены совместно с этим событием.Значения хранятся в xml\-элементе в формате \<items\>\<\> item  name \= "variableName" type\="System.String"\<variableValue\>\<\/item\>\/items.Если переменные не были отслежены, строка содержит значение \<items\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем удаления заметок и замены значения переменных значением \<items\>...\<\/items\>.Следующие типы сохраняются со своим значением, возвращаемым при помощи метода ToString\(\); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Annotations|xs:string|Заметки, добавленные к этому событию.Значения хранятся в xml\-элементе в формате \<элементы\>\< имя элемента \= "annotationName" тип\="System.String"\>annotationValue\<\/элемент\>\<\/элементы\>.Если ни одной заметки не указано, строка содержит \<элементы\/\>.Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.Если размер события превышает пределы ETW, событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы\>...\<\/элементы\>.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб\-сайтах, это поле служит уникальным идентификатором службы в веб\-иерархии.Формат определяется следующим образом: «имя\_веб\-сайта виртуальный\_путь\_приложения&#124;виртуальный\_путь\_службы&#124;имя\_службы». Пример: «веб\-сайт по умолчанию\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService»|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|