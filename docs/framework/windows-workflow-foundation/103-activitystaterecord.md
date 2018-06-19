---
title: 103 ― ActivityStateRecord
ms.date: 03/30/2017
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
ms.openlocfilehash: 38cec570cffebf6af6d35df481cbec8c7dca8cd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513868"
---
# <a name="103---activitystaterecord"></a>103 ― ActivityStateRecord
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|103|  
|Ключевые слова|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие выдается участником отслеживания ETW, когда действие в экземпляре рабочего процесса создает запись ActivityStateRecord.  
  
## <a name="message"></a>Сообщение  
 TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Состояние|xs:string|Состояние действия.|  
|Имя|xs:string|Отображаемое имя действия, выдавшего событие.|  
|ActivityId|xs:string|Идентификатор создающего действия.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра создающего действия.|  
|ActivityTypeName|xs:string|Имя типа выдающего действия.|  
|Аргументы|xs:string|Аргументы, которые были отслежены вместе с этим событием.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «argumentName» type="System.String" > argumentValue\</товар > \< /items >.  Если никакие аргументы не отслеживались, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.  Следующие типы сохраняются со своим значением, возвращаемым при помощи метода ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.  Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Переменные|xs:string|Переменные, которые были отслежены совместно с этим событием.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «variableName» type="System.String" > variableValue\</товар > \< /items >.  Если отсутствуют переменные не отслеживались, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения переменных с \<элементы >...  \< /items >.  Следующие типы сохраняются со своим значением, возвращаемым при помощи метода ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.  Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.  Если не задано никаких заметок, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Ее формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName" Пример: "веб-сайт по умолчанию/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
