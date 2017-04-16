---
title: "1025 - BookmarkScopeInitialized | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63584434-e709-471d-9e96-97d3d99e70d6
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1025 - BookmarkScopeInitialized
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1025|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что инициализирован объект BookmarkScope.  
  
## Сообщение  
 Объект BookmarkScope с идентификатором TemporaryId: «%1» инициализирован идентификатором «%2».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|TemporaryId|xs:string|Временный идентификатор закладки.|  
|InitializedId|xs:string|Инициализированный идентификатор закладки.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|