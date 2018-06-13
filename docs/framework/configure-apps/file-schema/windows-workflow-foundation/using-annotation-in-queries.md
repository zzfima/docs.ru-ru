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
ms.locfileid: "32767054"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="dbb02-102">Использование заметок в запросах</span><span class="sxs-lookup"><span data-stu-id="dbb02-102">Using Annotation in Queries</span></span>
<span data-ttu-id="dbb02-103">Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения.</span><span class="sxs-lookup"><span data-stu-id="dbb02-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="dbb02-104">Например, может потребоваться нескольким записям отслеживания из нескольких рабочих процессов следует пометить как «Mail Server» == «Mail Server1».</span><span class="sxs-lookup"><span data-stu-id="dbb02-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="dbb02-105">Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="dbb02-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="dbb02-106">Добавление заметок</span><span class="sxs-lookup"><span data-stu-id="dbb02-106">Adding Annotations</span></span>  
 <span data-ttu-id="dbb02-107">В следующем примере показано, как добавить заметку к запросу отслеживания.</span><span class="sxs-lookup"><span data-stu-id="dbb02-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="dbb02-108">Эти элементы запроса могут быть использованы для создания профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="dbb02-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="dbb02-109">Профиль отслеживания можно создать в коде или в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dbb02-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb02-110">См. также</span><span class="sxs-lookup"><span data-stu-id="dbb02-110">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="dbb02-111">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="dbb02-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [<span data-ttu-id="dbb02-112">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dbb02-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dbb02-113">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dbb02-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
