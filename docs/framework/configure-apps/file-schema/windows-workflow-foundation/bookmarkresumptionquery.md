---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945957"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="9e62d-101">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="9e62d-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="9e62d-102">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="9e62d-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9e62d-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="9e62d-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="9e62d-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="9e62d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9e62d-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="9e62d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9e62d-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="9e62d-106">\<tracking></span></span>  
<span data-ttu-id="9e62d-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9e62d-107">\<trackingProfile></span></span>  
<span data-ttu-id="9e62d-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9e62d-108">\<workflow></span></span>  
<span data-ttu-id="9e62d-109">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="9e62d-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="9e62d-110">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="9e62d-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e62d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e62d-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e62d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e62d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9e62d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9e62d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e62d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e62d-114">Attributes</span></span>  
  
|<span data-ttu-id="9e62d-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9e62d-115">Attribute</span></span>|<span data-ttu-id="9e62d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9e62d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e62d-117">имя</span><span class="sxs-lookup"><span data-stu-id="9e62d-117">name</span></span>|<span data-ttu-id="9e62d-118">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="9e62d-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e62d-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e62d-119">Child Elements</span></span>  
 <span data-ttu-id="9e62d-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="9e62d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e62d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e62d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9e62d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e62d-122">Element</span></span>|<span data-ttu-id="9e62d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9e62d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e62d-124">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="9e62d-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="9e62d-125">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9e62d-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e62d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9e62d-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9e62d-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9e62d-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9e62d-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9e62d-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
