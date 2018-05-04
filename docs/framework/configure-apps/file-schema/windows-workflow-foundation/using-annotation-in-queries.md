---
title: Использование заметок в запросах
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 692bc965fb62996c205d4e3d1061d8483a4f652c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="using-annotation-in-queries"></a>Использование заметок в запросах
Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения. Например, может потребоваться нескольким записям отслеживания из нескольких рабочих процессов следует пометить как «Mail Server» == «Mail Server1». Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.  
  
## <a name="adding-annotations"></a>Добавление заметок  
 В следующем примере показано, как добавить заметку к запросу отслеживания.  
  
```xml  
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
>  Эти элементы запроса могут быть использованы для создания профиля отслеживания. Профиль отслеживания можно создать в коде или в файле конфигурации.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [\<Участники >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
