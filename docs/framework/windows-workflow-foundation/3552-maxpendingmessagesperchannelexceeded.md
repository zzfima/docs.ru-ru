---
title: "3552 - MaxPendingMessagesPerChannelExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 3552 - MaxPendingMessagesPerChannelExceeded
## Свойства  
  
|||  
|-|-|  
|Идентификатор|3552|  
|Ключевые слова|Quota, WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».  
  
## Сообщение  
 Был достигнут предел регулирования «MaxPendingMessagesPerChannel» для «%1».  Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Limit|xs:string|Был достигнут предел регулирования «MaxPendingMessagesPerChannel».|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|