---
title: 104 ― ActivityScheduledRecord
ms.date: 03/30/2017
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
ms.openlocfilehash: feeac8eee18c36563e17ff0329a5b984a38e99c9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924453"
---
# <a name="104---activityscheduledrecord"></a>104 ― ActivityScheduledRecord
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|104|  
|Ключевые слова|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается участником отслеживания ETW, когда действие в экземпляре рабочего процесса создает запись ActivityScheduledRecord.  
  
## <a name="message"></a>Сообщение  
 TrackRecord=ActivityScheduledRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, Name =%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName=%7, ChildActivityName=%8, ChildActivityId=%9, ChildActivityInstanceId=%10, ChildActivityTypeName=%11, Annotations=%12, ProfileName=%13  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|name|xs:string|Имя действия, которое запланировало дочернее действие.|  
|ActivityId|xs:string|Идентификатор действия, которое запланировало дочернее действие.|  
|ActivityInstanceId|xs:string|Идентификатор экземпляра действия, которое запланировало дочернее действие.|  
|ActivityTypeName|xs:string|Тип действия, запросившего операцию отмены.|  
|ChildActivityName|xs:string|Имя запланированного действия.|  
|ChildActivityId|xs:string|Идентификатор запланированного действия.|  
|ChildActivityInstanceId|xs:string|Идентификатор экземпляра запланированного действия.|  
|ChildActivityTypeName|xs:string|Тип запланированного действия.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в XML-элемент в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</item > \< /items >.  Если не задано никаких заметок, строка содержит \<элементов / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName" Пример: "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
