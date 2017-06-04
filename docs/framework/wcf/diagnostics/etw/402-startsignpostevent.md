---
title: "402 — StartSignpostEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 402 — StartSignpostEvent
## Свойства  
  
|||  
|-|-|  
|Идентификатор|402|  
|Keywords|Устранение неполадок|  
|Level|Information|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Это событие отмечает начало сквозного действия.В ней содержится имя действия.  
  
## Message  
 Граница действия.  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|