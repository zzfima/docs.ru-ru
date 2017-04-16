---
title: "3508 - TrackingProfileNotFound | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3508 - TrackingProfileNotFound
## Свойства  
  
|||  
|-|-|  
|Идентификатор|3508|  
|Ключевые слова|WFServices|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.  
  
## Сообщение  
 Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».  Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|TrackingProfile|xs:string|Имя профиля отслеживания.|  
|ActivityDefinitionId|xs:string|Идентификатор определения действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|