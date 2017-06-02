---
title: "1146 - FlowchartSwitchCase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1146 - FlowchartSwitchCase
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1146|  
|Ключевые слова|WFActivities|  
|Уровень|Сведения|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, какой вариант \(Case\) был выбран в параметре блок\-схемы.  
  
## Сообщение  
 Блок\-схема «%1»\/FlowSwitch: выбран вариант Case «%2».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|Блок\-схема|xs:string|Отображаемое имя блок\-схемы.|  
|Case|xs:string|Выбранный вариант Case.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|