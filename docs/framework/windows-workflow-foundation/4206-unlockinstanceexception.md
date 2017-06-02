---
title: "4206 - UnlockInstanceException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4206 - UnlockInstanceException
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4206|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Ошибка|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что при попытке разблокировать экземпляр возникло исключение.  
  
## Сообщение  
 При попытке разблокировать экземпляр обнаружено исключение «%1».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|