---
title: "1041 - WorkflowApplicationPersistableIdle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1041 - WorkflowApplicationPersistableIdle
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1041|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что приложение рабочего процесса бездействует и является сохраняемым.  Приложение рабочего процесса будет бездействующим или сохраняемым.  
  
## Сообщение  
 Приложение рабочего процесса с ИД «%1» бездействует и сохраняемо. Будет предпринято следующее действие: %2.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|WorkflowApplicationId|xs:string|Идентификатор приложения рабочего процесса|  
|ActionTaken|xs:string|Действие, которое будет выполняться в приложении рабочего процесса.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|