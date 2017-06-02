---
title: "3503 - DuplicateCorrelationQuery | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3503 - DuplicateCorrelationQuery
## Свойства  
  
|||  
|-|-|  
|Идентификатор|3503|  
|Ключевые слова|WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что обнаружен повторяющийся запрос CorrelationQuery.  Повторяющийся запрос не будет использоваться при расчете корреляции.  
  
## Сообщение  
 Обнаружен повторяющийся запрос CorrelationQuery с параметром Where\=«%1».  Это дубликат не будет использоваться при расчете корреляции.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Where|xs:string|Часть Where в запросе корреляции.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|