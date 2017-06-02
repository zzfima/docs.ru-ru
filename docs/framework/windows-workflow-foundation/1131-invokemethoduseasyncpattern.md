---
title: "1131 - InvokeMethodUseAsyncPattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1131 - InvokeMethodUseAsyncPattern
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1131|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 На шаге CacheMetadata действие InvokeMethod указывает на использование асинхронного шаблона при вызове метода.  
  
## Сообщение  
 Метод InvokeMethod «%1»: в методе используется асинхронная модель «%2» и «%3».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|BeginMethod|xs:string|Имя метода Begin.|  
|EndMethod|xs:string|Имя метода End.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|