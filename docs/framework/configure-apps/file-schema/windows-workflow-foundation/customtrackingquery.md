---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 695fccf88ac0d8a672e710ccc632ea58dd2fc693
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398770"
---
# <a name="customtrackingquery"></a><span data-ttu-id="5c34d-101">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="5c34d-101">\<customTrackingQuery></span></span>
<span data-ttu-id="5c34d-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="5c34d-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5c34d-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5c34d-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5c34d-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="5c34d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5c34d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c34d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c34d-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5c34d-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5c34d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5c34d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5c34d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5c34d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5c34d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5c34d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5c34d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Кустомтраккингкуериес >** ](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="5c34d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="5c34d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Кустомтраккингкуери >**</span><span class="sxs-lookup"><span data-stu-id="5c34d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c34d-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c34d-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c34d-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c34d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5c34d-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5c34d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c34d-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c34d-115">Attributes</span></span>  
  
|<span data-ttu-id="5c34d-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5c34d-116">Attribute</span></span>|<span data-ttu-id="5c34d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5c34d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c34d-118">activityName</span><span class="sxs-lookup"><span data-stu-id="5c34d-118">activityName</span></span>|<span data-ttu-id="5c34d-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5c34d-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="5c34d-120">имя</span><span class="sxs-lookup"><span data-stu-id="5c34d-120">name</span></span>|<span data-ttu-id="5c34d-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5c34d-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c34d-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c34d-122">Child Elements</span></span>  
 <span data-ttu-id="5c34d-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="5c34d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c34d-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c34d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5c34d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c34d-125">Element</span></span>|<span data-ttu-id="5c34d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5c34d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c34d-127">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="5c34d-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="5c34d-128">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="5c34d-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c34d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5c34d-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5c34d-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="5c34d-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5c34d-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="5c34d-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
