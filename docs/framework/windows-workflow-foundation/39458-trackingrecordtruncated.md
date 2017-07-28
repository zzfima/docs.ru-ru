---
title: "39458 - TrackingRecordTruncated | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 39458 - TrackingRecordTruncated
## Свойства  
  
|||  
|-|-|  
|Идентификатор|39458|  
|Ключевые слова|WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что запись отслеживания была усечена.  Данные переменных, заметок, пользователей удалены.  
  
## Сообщение  
 Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2.  Данные переменных, заметок, пользователей удалены  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|RecordNumber|xs:string|Номер записи отслеживания.|  
|ProviderId|xs:string|Идентификатор поставщика трассировки событий Windows.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|