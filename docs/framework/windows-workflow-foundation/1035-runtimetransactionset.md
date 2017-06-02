---
title: "1035 - RuntimeTransactionSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1035 - RuntimeTransactionSet
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1035|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что действие задало транзакцию среды выполнения.  
  
## Сообщение  
 Транзакция среды выполнения настроена действием «%1», DisplayName «%2», InstanceId «%3». Выполнение изолированного действия «%4», DisplayName «%5», InstanceId «%6».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|IsolatedActivity|xs:string|Имя типа для действия, в котором изолирована транзакция.|  
|IsolatedActivityDisplayName|xs:string|Имя отображаемого имени действия, в котором изолирована транзакция.|  
|IsolatedActivityInstanceId|xs:string|Идентификатор экземпляра действия, в котором изолирована транзакция.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|