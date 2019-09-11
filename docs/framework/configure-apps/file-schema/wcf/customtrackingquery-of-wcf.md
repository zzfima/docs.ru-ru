---
title: <customTrackingQuery>WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855418"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="8319b-102">\<Кустомтраккингкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="8319b-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="8319b-103">Представляет запрос, который используется для трассировки событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="8319b-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="8319b-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="8319b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="8319b-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="8319b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8319b-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8319b-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8319b-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8319b-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8319b-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8319b-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="8319b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="8319b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="8319b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8319b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="8319b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8319b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="8319b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Кустомтраккингкуериес >** ](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8319b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="8319b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Кустомтраккингкуери >**</span><span class="sxs-lookup"><span data-stu-id="8319b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8319b-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8319b-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8319b-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8319b-115">Attributes and elements</span></span>  

<span data-ttu-id="8319b-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8319b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8319b-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8319b-117">Attributes</span></span>  
  
|<span data-ttu-id="8319b-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8319b-118">Attribute</span></span>|<span data-ttu-id="8319b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8319b-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="8319b-120">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="8319b-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="8319b-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="8319b-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8319b-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8319b-122">Child elements</span></span>

<span data-ttu-id="8319b-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="8319b-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8319b-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8319b-124">Parent elements</span></span>

|<span data-ttu-id="8319b-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="8319b-125">Element</span></span>|<span data-ttu-id="8319b-126">Описание</span><span class="sxs-lookup"><span data-stu-id="8319b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8319b-127">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="8319b-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="8319b-128">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="8319b-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="8319b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8319b-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8319b-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8319b-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8319b-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8319b-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
