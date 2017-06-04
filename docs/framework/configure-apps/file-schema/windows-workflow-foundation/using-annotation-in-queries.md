---
title: "Использование заметок в запросах | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Использование заметок в запросах
Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения.  Например, можно добавить тег “Mail Server” \=\= “Mail Server1” к нескольким записям отслеживания из нескольких рабочих процессов.  Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.  
  
## Добавление заметок  
 В следующем примере показано, как добавить заметку к запросу отслеживания.  
  
```  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
  
```  
  
> [!NOTE]
>  Эти элементы запроса могут быть использованы для создания профиля отслеживания.  Профиль отслеживания можно создать в коде или в файле конфигурации.  
  
## См. также  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>   
 <xref:System.Activities.Tracking.TrackingProfile>   
 [\<participants\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)