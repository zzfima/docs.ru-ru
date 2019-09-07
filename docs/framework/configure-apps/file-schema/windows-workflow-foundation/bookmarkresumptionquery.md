---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398852"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="0b32c-101">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="0b32c-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="0b32c-102">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="0b32c-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0b32c-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="0b32c-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0b32c-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0b32c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0b32c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b32c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b32c-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0b32c-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0b32c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="0b32c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="0b32c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="0b32c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="0b32c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0b32c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="0b32c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Букмаркресумптионкуериес >** ](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="0b32c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="0b32c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Букмаркресумптионкуери >**</span><span class="sxs-lookup"><span data-stu-id="0b32c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b32c-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b32c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b32c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b32c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0b32c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b32c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b32c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b32c-115">Attributes</span></span>  
  
|<span data-ttu-id="0b32c-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b32c-116">Attribute</span></span>|<span data-ttu-id="0b32c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0b32c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b32c-118">имя</span><span class="sxs-lookup"><span data-stu-id="0b32c-118">name</span></span>|<span data-ttu-id="0b32c-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="0b32c-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b32c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b32c-120">Child Elements</span></span>  
 <span data-ttu-id="0b32c-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="0b32c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b32c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b32c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0b32c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b32c-123">Element</span></span>|<span data-ttu-id="0b32c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="0b32c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b32c-125">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="0b32c-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="0b32c-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0b32c-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b32c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0b32c-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0b32c-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0b32c-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0b32c-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0b32c-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
