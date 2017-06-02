---
title: "4202 - StartSqlCommandExecute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4202 - StartSqlCommandExecute
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4202|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что команда SQL выполняется.  
  
## Сообщение  
 Запуск выполнения команды SQL: %1  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|SqlCommand|xs:string|Команда SQL, которая была выполнена.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|