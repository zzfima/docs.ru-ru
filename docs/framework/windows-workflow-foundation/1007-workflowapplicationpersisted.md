---
title: "1007 - WorkflowApplicationPersisted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1007 - WorkflowApplicationPersisted
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1007|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что приложение рабочего процесса сохранилось.  
  
## Сообщение  
 Элемент WorkflowApplication с идентификатором «%1» сохранен.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|WorkflowApplicationId|`xs:string`|Идентификатор приложения рабочего процесса|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|