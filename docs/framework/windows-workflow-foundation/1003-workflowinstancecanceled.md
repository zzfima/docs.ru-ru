---
title: "1003 - WorkflowInstanceCanceled | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 1003 - WorkflowInstanceCanceled
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1003|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что экземпляр рабочего процесса завершено в состоянии Canceled.  
  
## Сообщение  
 Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Canceled.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|