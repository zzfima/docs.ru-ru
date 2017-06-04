---
title: "3550 - BufferOutOfOrderMessageNoInstance | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3550 - BufferOutOfOrderMessageNoInstance
## Свойства  
  
|||  
|-|-|  
|Идентификатор|3550|  
|Ключевые слова|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Описание  
 Указывает, что получение через буфер не удалось.  Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.  
  
## Сообщение  
 Операция «%1» сейчас не может быть выполнена.  Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|OperationName|xs:string|Имя операции.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|