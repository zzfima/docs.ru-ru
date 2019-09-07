---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398980"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="52734-101">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="52734-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="52734-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="52734-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="52734-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="52734-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="52734-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="52734-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="52734-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52734-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52734-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="52734-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="52734-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="52734-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="52734-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="52734-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="52734-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="52734-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="52734-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитисчедуледкуериес >**</span><span class="sxs-lookup"><span data-stu-id="52734-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52734-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52734-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52734-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52734-112">Attributes and Elements</span></span>  
 <span data-ttu-id="52734-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52734-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52734-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52734-114">Attributes</span></span>  
 <span data-ttu-id="52734-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="52734-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52734-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52734-116">Child Elements</span></span>  
  
|<span data-ttu-id="52734-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="52734-117">Element</span></span>|<span data-ttu-id="52734-118">Описание</span><span class="sxs-lookup"><span data-stu-id="52734-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52734-119">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="52734-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="52734-120">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="52734-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52734-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52734-121">Parent Elements</span></span>  
  
|<span data-ttu-id="52734-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="52734-122">Element</span></span>|<span data-ttu-id="52734-123">Описание</span><span class="sxs-lookup"><span data-stu-id="52734-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52734-124">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="52734-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="52734-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="52734-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52734-126">См. также</span><span class="sxs-lookup"><span data-stu-id="52734-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="52734-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="52734-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="52734-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="52734-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
