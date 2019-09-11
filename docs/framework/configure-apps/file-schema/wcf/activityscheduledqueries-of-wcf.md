---
title: <activityScheduledQueries>WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850492"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="a09c2-102">\<Активитисчедуледкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="a09c2-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="a09c2-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="a09c2-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="a09c2-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="a09c2-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="a09c2-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a09c2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a09c2-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a09c2-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a09c2-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a09c2-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a09c2-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a09c2-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="a09c2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="a09c2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="a09c2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a09c2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="a09c2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a09c2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="a09c2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитисчедуледкуериес >**</span><span class="sxs-lookup"><span data-stu-id="a09c2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a09c2-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a09c2-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a09c2-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a09c2-114">Attributes and elements</span></span>  

<span data-ttu-id="a09c2-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a09c2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a09c2-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a09c2-116">Attributes</span></span>  

<span data-ttu-id="a09c2-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="a09c2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a09c2-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a09c2-118">Child elements</span></span>  
  
|<span data-ttu-id="a09c2-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="a09c2-119">Element</span></span>|<span data-ttu-id="a09c2-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a09c2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a09c2-121">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="a09c2-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="a09c2-122">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="a09c2-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a09c2-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a09c2-123">Parent elements</span></span>  
  
|<span data-ttu-id="a09c2-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a09c2-124">Element</span></span>|<span data-ttu-id="a09c2-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a09c2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a09c2-126">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a09c2-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a09c2-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="a09c2-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a09c2-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a09c2-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="a09c2-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a09c2-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a09c2-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a09c2-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
