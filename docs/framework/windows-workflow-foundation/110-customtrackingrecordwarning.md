---
title: 110 ― CustomTrackingRecordWarning
ms.date: 03/30/2017
ms.assetid: 3bc093de-be47-4ed0-983f-05b4246446fc
ms.openlocfilehash: 230e889c677ee83b2e71b128413b7107ec11dc2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924141"
---
# <a name="110---customtrackingrecordwarning"></a>110 ― CustomTrackingRecordWarning
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|110|  
|Ключевые слова|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается участником отслеживания ETW, когда действие в экземпляре рабочего процесса формирует запись CustomTrackingRecord с предупреждением уровня  
  
## <a name="message"></a>Сообщение  
 TrackRecord=CustomTrackingRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName=%11  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|name|xs:string|Имя CustomTrackingRecord.|  
|ActivityName|xs:string|Имя действия, создавшего CustomTrackingRecord.|  
|ActivityId|xs:string|Идентификатор действия, создавшего CustomTrackingRecord.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра действия, создавшего CustomTrackingRecord.|  
|ActivityTypeName|xs:string|Имя действия, создавшего CustomTrackingRecord.|  
|Данные|xs:string|Данные, которые были отслежены с помощью этого события.  Значения хранятся в XML-элемент в формате \<элементы >\< имя элемента = «dataName» type="System.String" > dataValue\</item > \< /items >.  Если данные не отслеживались, строка содержит \<элементов / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения данных с помощью \<элементы >...  \< /items >.  Следующие типы сохраняются со своим значением, возвращаемым при помощи метода ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.  Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элемент в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</item > \< /items >.  Если не задано никаких заметок, строка содержит \<элементов / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName" Пример: "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
