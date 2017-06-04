---
title: "404 — ResumeSignpostEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 395cc7ca-f35f-4295-be97-39a077f99c97
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 404 — ResumeSignpostEvent
## Свойства  
  
|||  
|-|-|  
|Идентификатор|404|  
|Keywords|Устранение неполадок|  
|Level|Information|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие отмечает продолжение сквозного действия.В ней содержится имя действия.  
  
## Message  
 Граница действия.  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|