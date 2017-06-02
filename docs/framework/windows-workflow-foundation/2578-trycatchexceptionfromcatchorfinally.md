---
title: "2578 - TryCatchExceptionFromCatchOrFinally | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2578 - TryCatchExceptionFromCatchOrFinally
## Свойства  
  
|||  
|-|-|  
|Идентификатор|2578|  
|Ключевые слова|WFActivities|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что действие Catch или Finally вызвало исключение.  
  
## Сообщение  
 В действии Catch или Finally, связанном с действием TryCatch «%1», произошло исключение.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|