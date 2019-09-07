---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 398b018ce407aee0687c95037753f3affa07aa9b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398784"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="54402-101">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="54402-101">\<customTrackingQueries></span></span>
<span data-ttu-id="54402-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="54402-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="54402-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="54402-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="54402-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="54402-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="54402-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="54402-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="54402-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="54402-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="54402-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="54402-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="54402-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="54402-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="54402-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="54402-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="54402-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Кустомтраккингкуериес >**</span><span class="sxs-lookup"><span data-stu-id="54402-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54402-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54402-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54402-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="54402-112">Attributes and Elements</span></span>  
 <span data-ttu-id="54402-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="54402-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54402-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="54402-114">Attributes</span></span>  
 <span data-ttu-id="54402-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="54402-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="54402-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="54402-116">Child Elements</span></span>  
  
|<span data-ttu-id="54402-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="54402-117">Element</span></span>|<span data-ttu-id="54402-118">Описание</span><span class="sxs-lookup"><span data-stu-id="54402-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54402-119">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="54402-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="54402-120">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="54402-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54402-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="54402-121">Parent Elements</span></span>  
  
|<span data-ttu-id="54402-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="54402-122">Element</span></span>|<span data-ttu-id="54402-123">Описание</span><span class="sxs-lookup"><span data-stu-id="54402-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54402-124">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="54402-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="54402-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="54402-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54402-126">См. также</span><span class="sxs-lookup"><span data-stu-id="54402-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="54402-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="54402-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="54402-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="54402-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
