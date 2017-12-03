---
title: "105 ― FaultPropagationRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 546e2a00fdfa16027b2fa145c5274e1bee4335ca
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="105---faultpropagationrecord"></a>105 ― FaultPropagationRecord
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|105|  
|Ключевые слова|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается участником отслеживания ETW, когда действие внутри рабочего процесса создает запись FaultPropagationRecord.  
  
## <a name="message"></a>Сообщение  
 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId=%9, FaultHandlerActivityInstanceId=%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName=%15  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|FaultSourceActivityName|xs:string|Имя действия, создавшего ошибку.|  
|FaultSourceActivityId|xs:string|Идентификатор действия, создавшего ошибку.|  
|FaultSourceActivityInstanceId|xs:string|Идентификатор экземпляра действия, создавшего ошибку.|  
|FaultSourceActivityTypeName|xs:string|Тип действия, создавшего ошибку.|  
|FaultHandlerActivityName|xs:string|Отображаемое имя действия обработчика ошибок.|  
|FaultHandlerActivityId|xs:string|Идентификатор действия обработчика ошибок.|  
|FaultHandlerActivityInstanceId|xs:string|Идентификатор экземпляра действия обработчика ошибок.|  
|FaultHandlerActivityTypeName|xs:string|Тип действия обработчика ошибок.|  
|Fault|xs:string|Сведения об ошибке.|  
|IsFaultSource|xs:unsignedByte|Указывает, если было событие создано источником ошибки.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.  Если не задано никаких заметок, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName "Пример:" по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
