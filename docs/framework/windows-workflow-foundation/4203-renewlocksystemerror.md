---
title: "4203 - RenewLockSystemError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4203 - RenewLockSystemError
## Свойства  
  
|||  
|-|-|  
|Идентификатор|4203|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Ошибка|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что поставщику SQL не удалось продлить срок блокировки либо из\-за того, что срок блокировки уже истек, либо из\-за того, что владелец блокировки был удален.  SqlWorkflowInstanceStore будет прервано.  
  
## Сообщение  
 Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален.  Прерывание блокировки SqlWorkflowInstanceStore.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|