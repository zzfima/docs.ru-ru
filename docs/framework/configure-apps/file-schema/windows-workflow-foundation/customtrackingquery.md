---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 4e525bc4c77649a6c6d70ddb2408b6ecce4a0f09
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263773"
---
# <a name="customtrackingquery"></a><span data-ttu-id="f2f51-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f2f51-101">\<customTrackingQuery></span></span>
<span data-ttu-id="f2f51-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f2f51-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f2f51-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f2f51-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f2f51-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f2f51-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f2f51-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f2f51-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f2f51-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f2f51-106">\<tracking></span></span>  
<span data-ttu-id="f2f51-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f2f51-107">\<trackingProfile></span></span>  
<span data-ttu-id="f2f51-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f2f51-108">\<workflow></span></span>  
<span data-ttu-id="f2f51-109">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="f2f51-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="f2f51-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f2f51-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f51-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2f51-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2f51-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f2f51-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f2f51-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f2f51-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2f51-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2f51-114">Attributes</span></span>  
  
|<span data-ttu-id="f2f51-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f2f51-115">Attribute</span></span>|<span data-ttu-id="f2f51-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f2f51-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2f51-117">activityName</span><span class="sxs-lookup"><span data-stu-id="f2f51-117">activityName</span></span>|<span data-ttu-id="f2f51-118">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f2f51-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f2f51-119">имя</span><span class="sxs-lookup"><span data-stu-id="f2f51-119">name</span></span>|<span data-ttu-id="f2f51-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f2f51-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2f51-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f2f51-121">Child Elements</span></span>  
 <span data-ttu-id="f2f51-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f2f51-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2f51-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f2f51-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f2f51-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f2f51-124">Element</span></span>|<span data-ttu-id="f2f51-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f2f51-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2f51-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f2f51-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="f2f51-127">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f2f51-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2f51-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f2f51-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f2f51-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f2f51-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f2f51-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f2f51-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
