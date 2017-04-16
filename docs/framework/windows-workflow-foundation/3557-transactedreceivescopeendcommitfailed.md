---
title: "3557 - TransactedReceiveScopeEndCommitFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3557 - TransactedReceiveScopeEndCommitFailed
## Свойства  
  
|||  
|-|-|  
|Идентификатор|3557|  
|Ключевые слова|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что вызов к EndCommit в CommittableTransaction привел к созданию исключения TransactionException.  
  
## Сообщение  
 Вызов EndCommit для CommittableTransaction с id \= «%1» привел к созданию исключения TransactionException со следующим сообщением: «%2».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|TransactionId|xs:string|Идентификатор CommittableTransaction.|  
|Исключение|xs:string|Сведения об исключении|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|