---
title: <customTrackingQuery>WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919363"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="b679a-102">\<Кустомтраккингкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="b679a-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="b679a-103">Представляет запрос, который используется для трассировки событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="b679a-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="b679a-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b679a-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="b679a-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b679a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b679a-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="b679a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b679a-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="b679a-107">\<tracking></span></span>  
<span data-ttu-id="b679a-108">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="b679a-108">\<profiles></span></span>  
<span data-ttu-id="b679a-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b679a-109">\<trackingProfile></span></span>  
<span data-ttu-id="b679a-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b679a-110">\<workflow></span></span>  
<span data-ttu-id="b679a-111">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="b679a-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="b679a-112">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="b679a-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b679a-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b679a-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b679a-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="b679a-114">Attributes and elements</span></span>  

<span data-ttu-id="b679a-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b679a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b679a-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b679a-116">Attributes</span></span>  
  
|<span data-ttu-id="b679a-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b679a-117">Attribute</span></span>|<span data-ttu-id="b679a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b679a-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b679a-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b679a-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="b679a-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b679a-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b679a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b679a-121">Child elements</span></span>

<span data-ttu-id="b679a-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="b679a-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b679a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b679a-123">Parent elements</span></span>

|<span data-ttu-id="b679a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b679a-124">Element</span></span>|<span data-ttu-id="b679a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b679a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b679a-126">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="b679a-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="b679a-127">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="b679a-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="b679a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b679a-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b679a-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b679a-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b679a-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b679a-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
