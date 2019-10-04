---
title: <bookmarkResumptionQuery>WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834006"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="bbb36-102">\<Букмаркресумптионкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="bbb36-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="bbb36-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="bbb36-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="bbb36-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="bbb36-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="bbb36-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bbb36-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="bbb36-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bbb36-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bbb36-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bbb36-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bbb36-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bbb36-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="bbb36-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="bbb36-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="bbb36-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bbb36-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="bbb36-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bbb36-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="bbb36-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Букмаркресумптионкуериес >** ](bookmarkresumptionqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bbb36-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)</span></span>\
<span data-ttu-id="bbb36-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Букмаркресумптионкуери >**</span><span class="sxs-lookup"><span data-stu-id="bbb36-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb36-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbb36-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbb36-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbb36-115">Attributes and elements</span></span>

<span data-ttu-id="bbb36-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bbb36-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbb36-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbb36-117">Attributes</span></span>  
  
|<span data-ttu-id="bbb36-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bbb36-118">Attribute</span></span>|<span data-ttu-id="bbb36-119">Описание</span><span class="sxs-lookup"><span data-stu-id="bbb36-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bbb36-120">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="bbb36-120">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbb36-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bbb36-121">Child elements</span></span>

<span data-ttu-id="bbb36-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="bbb36-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="bbb36-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bbb36-123">Parent elements</span></span>  
  
|<span data-ttu-id="bbb36-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbb36-124">Element</span></span>|<span data-ttu-id="bbb36-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bbb36-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbb36-126">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="bbb36-126">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="bbb36-127">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bbb36-127">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbb36-128">См. также</span><span class="sxs-lookup"><span data-stu-id="bbb36-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bbb36-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="bbb36-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bbb36-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="bbb36-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
