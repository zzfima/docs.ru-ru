---
title: "1036 - RuntimeTransactionCompletionRequested | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1036 - RuntimeTransactionCompletionRequested
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1036|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что действие запланировало завершение транзакции среды выполнения.  
  
## Сообщение  
 Действие «%1», DisplayName «%2», InstanceId «%3» запланировало завершение транзакции времени выполнения.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|