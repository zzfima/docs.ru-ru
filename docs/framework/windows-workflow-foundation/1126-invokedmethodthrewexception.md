---
title: "1126 - InvokedMethodThrewException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1126 - InvokedMethodThrewException
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1126|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.  
  
## Сообщение  
 Возникло исключение в методе, вызванном операцией «%1».  %2  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|Исключение|xs:string|Сведения об исключении|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|