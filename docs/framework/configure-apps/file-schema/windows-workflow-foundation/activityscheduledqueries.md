---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152428"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="5b350-101">\<активностьЗапланированныезапросы></span><span class="sxs-lookup"><span data-stu-id="5b350-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="5b350-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="5b350-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="5b350-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="5b350-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="5b350-104">Для получения дополнительной [информации](../../../windows-workflow-foundation/tracking-profiles.md) о запросах профиля отслеживания см.</span><span class="sxs-lookup"><span data-stu-id="5b350-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5b350-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b350-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5b350-106">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5b350-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5b350-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5b350-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5b350-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживаниеПрофильная>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5b350-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5b350-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<рабочий процесс>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5b350-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5b350-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<активностьЗапланированныезапросы>**</span><span class="sxs-lookup"><span data-stu-id="5b350-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b350-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b350-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b350-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5b350-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5b350-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5b350-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b350-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5b350-114">Attributes</span></span>  
 <span data-ttu-id="5b350-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="5b350-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b350-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5b350-116">Child Elements</span></span>  
  
|<span data-ttu-id="5b350-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5b350-117">Element</span></span>|<span data-ttu-id="5b350-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5b350-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b350-119">\<деятельностьЗапланировано></span><span class="sxs-lookup"><span data-stu-id="5b350-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="5b350-120">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="5b350-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b350-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5b350-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5b350-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="5b350-122">Element</span></span>|<span data-ttu-id="5b350-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5b350-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b350-124">\<рабочий процесс></span><span class="sxs-lookup"><span data-stu-id="5b350-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="5b350-125">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, идентифицированного свойством **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="5b350-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b350-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b350-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5b350-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="5b350-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5b350-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="5b350-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
