---
title: "1027 - StartTransactionContextWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1027 - StartTransactionContextWorkItem
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1027|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что начинается выполнение TransactionContextWorkItem.  
  
## Сообщение  
 Начато выполнение TransactionContextWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|