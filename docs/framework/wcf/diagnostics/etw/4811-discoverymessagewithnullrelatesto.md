---
title: "4811 - DiscoveryMessageWithNullRelatesTo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dab901e8-a2b3-41c1-a76b-bcd8b3c7c29a
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 4811 - DiscoveryMessageWithNullRelatesTo
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4811|  
|Ключевые слова|Обнаружение|  
|Уровень|Предупреждение|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Это событие создается при удалении сообщения обнаружения объектом DiscoveryClient из\-за отсутствия в заголовке сообщения обязательного свойства RelatesTo.  
  
## Сообщение  
 Сообщение %1 с messageId\="%2" удалено клиентом DiscoveryClient, поскольку заголовок сообщения не содержит обязательного свойства RelatesTo.  
  
## Подробные сведения