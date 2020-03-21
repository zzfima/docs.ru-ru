---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152415"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="93d37-101">\<деятельностьЗапланировано></span><span class="sxs-lookup"><span data-stu-id="93d37-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="93d37-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="93d37-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="93d37-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="93d37-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="93d37-104">Для получения дополнительной [информации](../../../windows-workflow-foundation/tracking-profiles.md) о запросах профиля отслеживания см.</span><span class="sxs-lookup"><span data-stu-id="93d37-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="93d37-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="93d37-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="93d37-106">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="93d37-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="93d37-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="93d37-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="93d37-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживаниеПрофильная>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="93d37-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="93d37-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<рабочий процесс>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="93d37-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="93d37-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<активностьЗапланированныезапросы>**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="93d37-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="93d37-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<деятельностьЗапланировано>**</span><span class="sxs-lookup"><span data-stu-id="93d37-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93d37-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93d37-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93d37-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93d37-113">Attributes and Elements</span></span>  
 <span data-ttu-id="93d37-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="93d37-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93d37-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93d37-115">Attributes</span></span>  
  
|<span data-ttu-id="93d37-116">attribute</span><span class="sxs-lookup"><span data-stu-id="93d37-116">Attribute</span></span>|<span data-ttu-id="93d37-117">Описание</span><span class="sxs-lookup"><span data-stu-id="93d37-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93d37-118">activityName</span><span class="sxs-lookup"><span data-stu-id="93d37-118">activityName</span></span>|<span data-ttu-id="93d37-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="93d37-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="93d37-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="93d37-120">childActivityName</span></span>|<span data-ttu-id="93d37-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="93d37-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93d37-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93d37-122">Child Elements</span></span>  
 <span data-ttu-id="93d37-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="93d37-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93d37-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93d37-124">Parent Elements</span></span>  
  
|<span data-ttu-id="93d37-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="93d37-125">Element</span></span>|<span data-ttu-id="93d37-126">Описание</span><span class="sxs-lookup"><span data-stu-id="93d37-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93d37-127">\<деятельностьЗапланировано></span><span class="sxs-lookup"><span data-stu-id="93d37-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="93d37-128">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="93d37-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93d37-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="93d37-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="93d37-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="93d37-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="93d37-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="93d37-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
