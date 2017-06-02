---
title: "57398 - MaxInstancesExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 57398 - MaxInstancesExceeded
## Свойства  
  
|||  
|-|-|  
|Идентификатор|57398|  
|Ключевые слова|WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.  
  
## Сообщение  
 Система достигла предела, заданного для ограничителя «MaxConcurrentInstances».  Для этого ограничителя был задан предел %1.  Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Имя|xs:string|Имя элемента.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|