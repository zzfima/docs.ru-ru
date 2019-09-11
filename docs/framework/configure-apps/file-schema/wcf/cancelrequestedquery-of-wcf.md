---
title: <cancelRequestedQuery>WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850048"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="ec40d-102">\<Канцелрекуестедкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="ec40d-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="ec40d-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="ec40d-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ec40d-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="ec40d-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="ec40d-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ec40d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="ec40d-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec40d-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ec40d-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ec40d-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ec40d-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ec40d-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="ec40d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="ec40d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="ec40d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ec40d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="ec40d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ec40d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="ec40d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Канцелрекуестедкуериес >** ](cancelrequestedqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ec40d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)</span></span>\
<span data-ttu-id="ec40d-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Канцелрекуестедкуери >**</span><span class="sxs-lookup"><span data-stu-id="ec40d-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ec40d-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec40d-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec40d-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec40d-115">Attributes and elements</span></span>

<span data-ttu-id="ec40d-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec40d-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec40d-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec40d-117">Attributes</span></span>  
  
|<span data-ttu-id="ec40d-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ec40d-118">Attribute</span></span>|<span data-ttu-id="ec40d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ec40d-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="ec40d-120">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="ec40d-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="ec40d-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="ec40d-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec40d-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec40d-122">Child elements</span></span>

<span data-ttu-id="ec40d-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="ec40d-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="ec40d-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec40d-124">Parent elements</span></span>
  
|<span data-ttu-id="ec40d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec40d-125">Element</span></span>|<span data-ttu-id="ec40d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ec40d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec40d-127">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="ec40d-127">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="ec40d-128">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="ec40d-128">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec40d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ec40d-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ec40d-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ec40d-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ec40d-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ec40d-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
