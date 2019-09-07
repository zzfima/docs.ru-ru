---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: aa6ee435c66303b5089b459ecc4ed3023297636d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398973"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="1fec2-101">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="1fec2-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="1fec2-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="1fec2-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1fec2-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="1fec2-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="1fec2-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="1fec2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1fec2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1fec2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1fec2-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1fec2-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1fec2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1fec2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1fec2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1fec2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1fec2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1fec2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1fec2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитисчедуледкуериес >** ](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="1fec2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="1fec2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитисчедуледкуери >**</span><span class="sxs-lookup"><span data-stu-id="1fec2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fec2-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fec2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fec2-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1fec2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1fec2-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1fec2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fec2-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1fec2-115">Attributes</span></span>  
  
|<span data-ttu-id="1fec2-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1fec2-116">Attribute</span></span>|<span data-ttu-id="1fec2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1fec2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fec2-118">activityName</span><span class="sxs-lookup"><span data-stu-id="1fec2-118">activityName</span></span>|<span data-ttu-id="1fec2-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="1fec2-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="1fec2-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="1fec2-120">childActivityName</span></span>|<span data-ttu-id="1fec2-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="1fec2-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fec2-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1fec2-122">Child Elements</span></span>  
 <span data-ttu-id="1fec2-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="1fec2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fec2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1fec2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1fec2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="1fec2-125">Element</span></span>|<span data-ttu-id="1fec2-126">Описание</span><span class="sxs-lookup"><span data-stu-id="1fec2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fec2-127">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="1fec2-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="1fec2-128">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="1fec2-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fec2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1fec2-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1fec2-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1fec2-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1fec2-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="1fec2-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
