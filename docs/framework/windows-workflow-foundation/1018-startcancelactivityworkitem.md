---
title: "1018 - StartCancelActivityWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1018 - StartCancelActivityWorkItem
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1018|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что CancelActivityWorkItem начинает выполнение.  
  
## Сообщение  
 Начато выполнение CancelActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|