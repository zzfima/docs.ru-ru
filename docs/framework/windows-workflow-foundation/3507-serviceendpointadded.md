---
title: "3507 - ServiceEndpointAdded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3507 - ServiceEndpointAdded
## Свойства  
  
|||  
|-|-|  
|Идентификатор|3507|  
|Ключевые слова|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что конечная точка службы была добавлена.  
  
## Сообщение  
 Конечная точка службы была добавлена для адреса «%1», привязки «%2» и контракта «%3».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Адрес|xs:string|Адрес конечной точки.|  
|Привязка|xs:string|Привязка конечной точки.|  
|Контракт|xs:string|Контракт конечной точки.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|