---
title: "Использование заметок в запросах"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e871533afc1a472bb5ee05e3e13275bdfb1acc8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
