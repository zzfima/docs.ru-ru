---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790186"
---
# <a name="customtrackingquery"></a><span data-ttu-id="c2e56-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="c2e56-101">\<customTrackingQuery></span></span>
<span data-ttu-id="c2e56-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="c2e56-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="c2e56-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c2e56-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="c2e56-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c2e56-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c2e56-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c2e56-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c2e56-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="c2e56-106">\<tracking></span></span>  
<span data-ttu-id="c2e56-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c2e56-107">\<trackingProfile></span></span>  
<span data-ttu-id="c2e56-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="c2e56-108">\<workflow></span></span>  
<span data-ttu-id="c2e56-109">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="c2e56-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="c2e56-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="c2e56-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e56-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e56-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2e56-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c2e56-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c2e56-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c2e56-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2e56-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c2e56-114">Attributes</span></span>  
  
|<span data-ttu-id="c2e56-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c2e56-115">Attribute</span></span>|<span data-ttu-id="c2e56-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c2e56-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2e56-117">activityName</span><span class="sxs-lookup"><span data-stu-id="c2e56-117">activityName</span></span>|<span data-ttu-id="c2e56-118">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c2e56-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="c2e56-119">имя</span><span class="sxs-lookup"><span data-stu-id="c2e56-119">name</span></span>|<span data-ttu-id="c2e56-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c2e56-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2e56-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c2e56-121">Child Elements</span></span>  
 <span data-ttu-id="c2e56-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c2e56-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2e56-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c2e56-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c2e56-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c2e56-124">Element</span></span>|<span data-ttu-id="c2e56-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c2e56-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2e56-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="c2e56-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="c2e56-127">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="c2e56-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2e56-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e56-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c2e56-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c2e56-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c2e56-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="c2e56-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
