---
title: "4205 - FoundProcessingError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4205 - FoundProcessingError
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4205|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Ошибка|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает на сбой команды поставщика SQL.  
  
## Сообщение  
 Не удалось выполнить команду: %1  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|Исключение|xs:string|Сведения об исключении|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|