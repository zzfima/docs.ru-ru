---
title: "441 — StopSignpostEvent1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 441 — StopSignpostEvent1
## Свойства  
  
|||  
|-|-|  
|Идентификатор|441|  
|Keywords|Устранение неполадок|  
|Level|Information|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 В трассировке действий указывает на то, что сообщение закончило пересекать границу действия при отправке или приеме.  
  
## Сообщение  
 Граница действия.  
  
## Подробности  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|