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
ms.openlocfilehash: 3a6edccba458bfd3629cab851c5d818a69d26173
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="43225-102">Использование заметок в запросах</span><span class="sxs-lookup"><span data-stu-id="43225-102">Using Annotation in Queries</span></span>
<span data-ttu-id="43225-103">Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения.</span><span class="sxs-lookup"><span data-stu-id="43225-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="43225-104">Например, может потребоваться нескольким записям отслеживания из нескольких рабочих процессов следует пометить как «Mail Server» == «Mail Server1».</span><span class="sxs-lookup"><span data-stu-id="43225-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="43225-105">Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="43225-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="43225-106">Добавление заметок</span><span class="sxs-lookup"><span data-stu-id="43225-106">Adding Annotations</span></span>  
 <span data-ttu-id="43225-107">В следующем примере показано, как добавить заметку к запросу отслеживания.</span><span class="sxs-lookup"><span data-stu-id="43225-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="43225-108">Эти элементы запроса могут быть использованы для создания профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="43225-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="43225-109">Профиль отслеживания можно создать в коде или в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="43225-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43225-110">См. также</span><span class="sxs-lookup"><span data-stu-id="43225-110">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="43225-111">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="43225-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [<span data-ttu-id="43225-112">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="43225-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="43225-113">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="43225-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
