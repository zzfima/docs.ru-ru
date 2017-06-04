---
title: "1022 - StartBookmarkWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1022 - StartBookmarkWorkItem
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1022|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что начинается выполнение BookmarkWorkItem.  
  
## Сообщение  
 Начато выполнение BookmarkWorkItem для действия «%1», DisplayName «%2», InstanceId «%3». BookmarkName: %4, BookmarkScope: %5.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|BookmarkName|xs:string|Имя закладки.|  
|BookmarkScope|xs:string|Область закладки.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|