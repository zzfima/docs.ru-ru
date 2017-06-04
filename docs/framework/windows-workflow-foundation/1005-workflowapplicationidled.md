---
title: "1005 - WorkflowApplicationIdled | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1005 - WorkflowApplicationIdled
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1005|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что приложение рабочего процесса простаивало.  
  
## Сообщение  
 WorkflowApplication с идентификатором «%1» перешло в состояние простоя.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор приложения рабочего процесса|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|