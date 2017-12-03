---
title: "107 ― BookmarkResumptionRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d3effb662ec2994351e1de7975b8ce2737c5ef0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="107----bookmarkresumptionrecord"></a>107 ― BookmarkResumptionRecord
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|107|  
|Ключевые слова|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись BookmarkResumptionRecord.  
  
## <a name="message"></a>Сообщение  
 TrackRecord=BookmarkResumptionRecord, InstanceId=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5, OwnerActivityName=%6, OwnerActivityId=%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName=%11  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Идентификатор экземпляра для рабочего процесса.|  
|RecordNumber|xs:long|Порядковый номер созданной записи.|  
|EventTime|xs:dateTime|Время в формате UTC, когда было создано событие.|  
|Имя|xs:string|Имя возобновленной закладки.|  
|SubInstanceID|xs:GUID|Идентификатор области закладки.|  
|OwnerActivityName|xs:string|Имя действия закладки.|  
|OwnerActivityId|xs:string|Идентификатор действия закладки.|  
|OwnerActivityInstanceId|xs:string|Идентификатор экземпляра действия закладки.|  
|OwnerActivityTypeName|xs:string|Тип действия закладки.|  
|Заметки|xs:string|Заметки, добавленные к этому событию.  Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.  Если не задано никаких заметок, строка содержит \<элементы / >. Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW. Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.|  
|ProfileName|xs:string|Имя или профиль отслеживания, который привел к созданию этого события.|  
|HostReference|xs:string|Для служб, размещенных на веб-сайтах, это поле служит уникальным идентификатором службы в веб-иерархии.  Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName "Пример:" по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
