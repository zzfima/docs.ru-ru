---
title: "1125 - InvokeMethodIsNotStatic | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1125 - InvokeMethodIsNotStatic
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1125|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод \- не статический.  
  
## Сообщение  
 Метод InvokeMethod «%1»: метод не является статическим.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|