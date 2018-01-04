---
title: "101 ― WorkflowInstanceUnhandledExceptionRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab7d50a0-5347-4390-8445-1def4dfdff6a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecbd7cad670b4b1bed87cc7d976bc482c786635a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="101---workflowinstanceunhandledexceptionrecord"></a>101 ― WorkflowInstanceUnhandledExceptionRecord
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|101|  
|Ключевые слова|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceUnhandledExceptionRecord.  
  
## <a name="message"></a>Сообщение  
 TrackRecord=WorkflowInstanceUnhandledExceptionRecord, InstanceId=%1, RecordNumber=%2, EventTime=%3, ActivityDefinitionId=%4, SourceName=%5, SourceId=%6, SourceInstanceId=%7, SourceTypeName=%8, Exception=%9, Annotations=%10, ProfileName=%11  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|ActivityDefinitionId|xs:string|Имя корневого действия в рабочем процессе.|  
|SourceName|xs:string|Имя исходного действия, в котором произошла ошибка, что привело к созданию исключения unhandledException.|  
|SourceId|xs:string|Идентификатор исходного действия, в котором произошла ошибка.|  
|SourceInstanceId|xs:string|Идентификатор экземпляра исходного действия, в котором произошла ошибка.|  
|SourceTypeName|xs:string|Имя типа исходного действия, в котором произошла ошибка, что привело к созданию исключения unhandledException.|  
|Исключение|xs:string|Данные необработанного исключения.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.  Если не задано никаких заметок, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName "Пример:" по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
