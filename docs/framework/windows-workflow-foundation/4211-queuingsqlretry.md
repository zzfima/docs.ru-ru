---
title: "4211 - QueuingSqlRetry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4211 - QueuingSqlRetry
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4211|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает на повтор SQL с задержкой.  
  
## Сообщение  
 Повторная попытка поместить SQL в очередь с задержкой %1 мс.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Delay|xs:string|Задержка между попытками.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|