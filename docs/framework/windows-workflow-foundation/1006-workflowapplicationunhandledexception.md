---
title: "1006 - WorkflowApplicationUnhandledException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1006 - WorkflowApplicationUnhandledException
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1006|  
|Ключевые слова|WFRuntime|  
|Уровень|Ошибка|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что приложение рабочего процесса обнаружило необработанное исключение.  
  
## Сообщение  
 Идентификатор класса WorkflowInstance: в «%1» обнаружено необработанное исключение. Исключение произошло в действии «%2» \(отображаемое имя «%3»\). Будет предпринято следующее действие: %4.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|Исключение|`xs:string`|Сведения об исключении|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|