---
title: "4212 - LockRetryTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4212 - LockRetryTimeout
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4212|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.  
  
## Сообщение  
 Время ожидания истекло при попытке получить блокировку для экземпляра. Операция не завершилась в течение заданного времени ожидания %1.  Возможно, выделенное для этой операции время было частью более длительного времени ожидания.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Delay|xs:string|Задержка между попытками.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|