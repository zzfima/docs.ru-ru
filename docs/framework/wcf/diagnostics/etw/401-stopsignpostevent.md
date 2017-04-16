---
title: "401 - StopSignPostEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 401 - StopSignPostEvent
## Свойства  
  
|||  
|-|-|  
|Идентификатор|401|  
|Ключевые слова|Устранение неполадок|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие отмечает окончание сквозного действия.  В ней содержится имя действия.  
  
## Сообщение  
 Граница действия.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|