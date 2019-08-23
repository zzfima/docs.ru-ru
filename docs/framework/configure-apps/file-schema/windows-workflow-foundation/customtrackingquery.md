---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9605f5d050baf046ff3c549c19191934299a65e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945750"
---
# <a name="customtrackingquery"></a><span data-ttu-id="e8734-101">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="e8734-101">\<customTrackingQuery></span></span>
<span data-ttu-id="e8734-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="e8734-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e8734-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e8734-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e8734-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e8734-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e8734-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="e8734-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e8734-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="e8734-106">\<tracking></span></span>  
<span data-ttu-id="e8734-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e8734-107">\<trackingProfile></span></span>  
<span data-ttu-id="e8734-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e8734-108">\<workflow></span></span>  
<span data-ttu-id="e8734-109">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="e8734-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="e8734-110">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="e8734-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8734-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8734-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8734-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e8734-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e8734-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e8734-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8734-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e8734-114">Attributes</span></span>  
  
|<span data-ttu-id="e8734-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e8734-115">Attribute</span></span>|<span data-ttu-id="e8734-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e8734-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8734-117">activityName</span><span class="sxs-lookup"><span data-stu-id="e8734-117">activityName</span></span>|<span data-ttu-id="e8734-118">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e8734-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="e8734-119">имя</span><span class="sxs-lookup"><span data-stu-id="e8734-119">name</span></span>|<span data-ttu-id="e8734-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e8734-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8734-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e8734-121">Child Elements</span></span>  
 <span data-ttu-id="e8734-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8734-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8734-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e8734-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e8734-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8734-124">Element</span></span>|<span data-ttu-id="e8734-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e8734-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8734-126">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="e8734-126">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="e8734-127">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="e8734-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8734-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e8734-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e8734-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e8734-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e8734-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e8734-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
