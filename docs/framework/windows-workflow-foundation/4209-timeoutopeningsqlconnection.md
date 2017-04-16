---
title: "4209 - TimeoutOpeningSqlConnection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4209 - TimeoutOpeningSqlConnection
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4209|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Ошибка|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что при попытке открыть соединение SQL превышено время ожидания.  
  
## Сообщение  
 Истекло время ожидания при открытии соединения SQL.  Не удалось выполнить операцию за выделенное время ожидания %1.  Возможно, выделенное для этой операции время было частью более длительного времени ожидания.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Время ожидания|xs:string|Значение времени ожидания для открытия соединения SQL.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|