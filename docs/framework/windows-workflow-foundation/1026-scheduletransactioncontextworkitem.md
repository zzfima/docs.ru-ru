---
title: "1026 - ScheduleTransactionContextWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1026 - ScheduleTransactionContextWorkItem
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1026|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что TransactionContextWorkItem было запланировано.  
  
## Сообщение  
 TransactionContextWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|