---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398863"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="e5a2d-101">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="e5a2d-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="e5a2d-102">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e5a2d-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e5a2d-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="e5a2d-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="e5a2d-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e5a2d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e5a2d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5a2d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5a2d-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e5a2d-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e5a2d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e5a2d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e5a2d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="e5a2d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="e5a2d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e5a2d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="e5a2d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Букмаркресумптионкуериес >**</span><span class="sxs-lookup"><span data-stu-id="e5a2d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="e5a2d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5a2d-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5a2d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5a2d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e5a2d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5a2d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5a2d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5a2d-114">Attributes</span></span>  
 <span data-ttu-id="e5a2d-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="e5a2d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5a2d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5a2d-116">Child Elements</span></span>  
  
|<span data-ttu-id="e5a2d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5a2d-117">Element</span></span>|<span data-ttu-id="e5a2d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e5a2d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a2d-119">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="e5a2d-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="e5a2d-120">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e5a2d-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e5a2d-121">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="e5a2d-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5a2d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5a2d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e5a2d-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5a2d-123">Element</span></span>|<span data-ttu-id="e5a2d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e5a2d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a2d-125">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e5a2d-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="e5a2d-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="e5a2d-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5a2d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e5a2d-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e5a2d-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e5a2d-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e5a2d-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e5a2d-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
