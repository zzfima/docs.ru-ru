---
title: <bookmarkResumptionQueries>WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850137"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="2b575-102">\<Букмаркресумптионкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="2b575-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="2b575-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2b575-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2b575-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="2b575-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="2b575-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2b575-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="2b575-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b575-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2b575-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2b575-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2b575-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2b575-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="2b575-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="2b575-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="2b575-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2b575-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="2b575-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2b575-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="2b575-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Букмаркресумптионкуериес >**</span><span class="sxs-lookup"><span data-stu-id="2b575-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="2b575-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b575-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b575-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b575-114">Attributes and elements</span></span>  
  
<span data-ttu-id="2b575-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2b575-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b575-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b575-116">Attributes</span></span>  
  
<span data-ttu-id="2b575-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="2b575-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b575-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b575-118">Child elements</span></span>  
  
|<span data-ttu-id="2b575-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b575-119">Element</span></span>|<span data-ttu-id="2b575-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2b575-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b575-121">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="2b575-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="2b575-122">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2b575-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2b575-123">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="2b575-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b575-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b575-124">Parent elements</span></span>  
  
|<span data-ttu-id="2b575-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b575-125">Element</span></span>|<span data-ttu-id="2b575-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2b575-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b575-127">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="2b575-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="2b575-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="2b575-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b575-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2b575-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2b575-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2b575-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2b575-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2b575-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
