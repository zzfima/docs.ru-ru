---
title: "4208 - RetryingSqlCommandDueToSqlError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4208 - RetryingSqlCommandDueToSqlError
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4208|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что поставщик SQL повторяет команду SQL из\-за ошибки SQL.  
  
## Сообщение  
 Выполняется повтор команды SQL из\-за ошибки SQL с номером %1.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|ErrorNumber|xs:string|Номер ошибки SQL.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|