---
title: "1148 - FlowchartSwitchCaseNotFound | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1148 - FlowchartSwitchCaseNotFound
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1148|  
|Ключевые слова|WFActivities|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что в параметре блок\-схемы не найден ни соответствующий вариант, ни вариант по умолчанию.  Выполнение блок\-схемы будет завершено.  
  
## Сообщение  
 Блок\-схема «%1»\/FlowSwitch \- не удалось найти ни действие Case, ни действие Default Case, соответствующее результату выражения Expression.  Выполнение блок\-схемы будет завершено.  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Блок\-схема|xs:string|Отображаемое имя блок\-схемы.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|