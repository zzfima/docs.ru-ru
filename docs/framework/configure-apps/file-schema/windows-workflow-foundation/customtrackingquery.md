---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076657"
---
# <a name="customtrackingquery"></a><span data-ttu-id="1cbd8-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="1cbd8-101">\<customTrackingQuery></span></span>
<span data-ttu-id="1cbd8-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1cbd8-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="1cbd8-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1cbd8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1cbd8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1cbd8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1cbd8-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="1cbd8-106">\<tracking></span></span>  
<span data-ttu-id="1cbd8-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1cbd8-107">\<trackingProfile></span></span>  
<span data-ttu-id="1cbd8-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="1cbd8-108">\<workflow></span></span>  
<span data-ttu-id="1cbd8-109">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="1cbd8-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="1cbd8-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="1cbd8-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cbd8-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cbd8-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cbd8-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1cbd8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1cbd8-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cbd8-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1cbd8-114">Attributes</span></span>  
  
|<span data-ttu-id="1cbd8-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1cbd8-115">Attribute</span></span>|<span data-ttu-id="1cbd8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1cbd8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cbd8-117">activityName</span><span class="sxs-lookup"><span data-stu-id="1cbd8-117">activityName</span></span>|<span data-ttu-id="1cbd8-118">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="1cbd8-119">имя</span><span class="sxs-lookup"><span data-stu-id="1cbd8-119">name</span></span>|<span data-ttu-id="1cbd8-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cbd8-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1cbd8-121">Child Elements</span></span>  
 <span data-ttu-id="1cbd8-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cbd8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1cbd8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1cbd8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1cbd8-124">Element</span></span>|<span data-ttu-id="1cbd8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1cbd8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cbd8-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="1cbd8-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="1cbd8-127">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="1cbd8-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cbd8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1cbd8-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1cbd8-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1cbd8-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1cbd8-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="1cbd8-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
