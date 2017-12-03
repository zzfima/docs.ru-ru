---
title: "108 ― CustomTrackingRecordInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bee501e-4e00-42cd-b949-e88009c3d4e8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e46a597541442a9a8556dc398b739add82dc4820
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="108---customtrackingrecordinfo"></a>108 ― CustomTrackingRecordInfo
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|108|  
|Ключевые слова|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается участником отслеживания ETW, когда действие в экземпляре рабочего процесса выдает запись CustomTrackingRecord с уровнем Info.  
  
## <a name="message"></a>Сообщение  
 TrackRecord=CustomTrackingRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName=%11  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Имя|xs:string|Имя CustomTrackingRecord.|  
|ActivityName|xs:string|Имя действия, создавшего CustomTrackingRecord.|  
|ActivityId|xs:string|Идентификатор действия, создавшего CustomTrackingRecord.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра действия, создавшего CustomTrackingRecord.|  
|ActivityTypeName|xs:string|Имя действия, создавшего CustomTrackingRecord.|  
|Данные|xs:string|Данные, которые были отслежены с помощью этого события.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «dataName» type="System.String" > dataValue\</товар > \< /items >.  Если данные не было отслеживались, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения данных с \<элементы >...  \< /items >.  Следующие типы сохраняются со своим значением, возвращаемым при помощи метода ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.  Все остальные типы сериализуются при помощи метода System.Runtime.Serialization.NetDataContractSerializer.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.  Если не задано никаких заметок, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName "Пример:" по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
