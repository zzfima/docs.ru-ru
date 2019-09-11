---
title: <activityScheduledQuery>WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850476"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="4d2f4-102">\<Активитисчедуледкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="4d2f4-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="4d2f4-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="4d2f4-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="4d2f4-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4d2f4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4d2f4-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d2f4-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4d2f4-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4d2f4-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4d2f4-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4d2f4-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="4d2f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="4d2f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="4d2f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4d2f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="4d2f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4d2f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="4d2f4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитисчедуледкуериес >** ](activityscheduledqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4d2f4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)</span></span>\
<span data-ttu-id="4d2f4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитисчедуледкуери >**</span><span class="sxs-lookup"><span data-stu-id="4d2f4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2f4-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d2f4-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d2f4-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d2f4-115">Attributes and elements</span></span>  

<span data-ttu-id="4d2f4-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d2f4-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d2f4-117">Attributes</span></span>  
  
|<span data-ttu-id="4d2f4-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d2f4-118">Attribute</span></span>|<span data-ttu-id="4d2f4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4d2f4-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="4d2f4-120">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="4d2f4-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d2f4-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d2f4-122">Child elements</span></span>

<span data-ttu-id="4d2f4-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="4d2f4-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d2f4-124">Parent elements</span></span>  
  
|<span data-ttu-id="4d2f4-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d2f4-125">Element</span></span>|<span data-ttu-id="4d2f4-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4d2f4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d2f4-127">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="4d2f4-127">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="4d2f4-128">Коллекция запросов, которая используется для трассировки действия, запланированного на выполнение родительским действием.</span><span class="sxs-lookup"><span data-stu-id="4d2f4-128">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d2f4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4d2f4-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="4d2f4-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4d2f4-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4d2f4-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4d2f4-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
