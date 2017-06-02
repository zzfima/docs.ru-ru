---
title: "1014 - ScheduleCompletionWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1014 - ScheduleCompletionWorkItem
## Свойства  
  
|||  
|-|-|  
|Идентификатор|1014|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Описание  
 Указывает, что элемент CompletionWorkItem был запланирован.  
  
## Сообщение  
 CompletionWorkItem запланирован для родительского действия «%1», DisplayName «%2», InstanceId «%3». Выполнено действие «%4», DisplayName «%5», InstanceId «%6».  
  
## Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|-------------------------|-------------------------|--------------|  
|ParentActivity|xs:string|Имя типа родительского действия.|  
|ParentDisplayName|xs:string|Отображаемое имя родительского действия.|  
|ParentInstanceId|xs:string|Идентификатор экземпляра родительского действия.|  
|CompletedActivity|xs:string|Имя типа завершенного действия.|  
|CompletedActivityDisplayName|xs:string|Отображаемое имя завершенного действия.|  
|CompletedActivityInstanceId|xs:string|Идентификатор экземпляра завершенного действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|