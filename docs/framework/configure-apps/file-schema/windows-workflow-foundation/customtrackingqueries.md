---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 757bbe500ec3edccef465b7ff23b2c974e4a5011
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598845"
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="07056-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="07056-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="07056-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="07056-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="07056-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="07056-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="07056-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="07056-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="07056-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="07056-106">\<system.serviceModel></span></span>  
<span data-ttu-id="07056-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="07056-107">\<tracking></span></span>  
<span data-ttu-id="07056-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="07056-108">\<trackingProfile></span></span>  
<span data-ttu-id="07056-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="07056-109">\<workflow></span></span>  
<span data-ttu-id="07056-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="07056-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07056-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07056-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07056-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="07056-112">Attributes and Elements</span></span>  
 <span data-ttu-id="07056-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="07056-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07056-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="07056-114">Attributes</span></span>  
 <span data-ttu-id="07056-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="07056-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07056-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="07056-116">Child Elements</span></span>  
  
|<span data-ttu-id="07056-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="07056-117">Element</span></span>|<span data-ttu-id="07056-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="07056-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07056-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="07056-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="07056-120">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="07056-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07056-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="07056-121">Parent Elements</span></span>  
  
|<span data-ttu-id="07056-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="07056-122">Element</span></span>|<span data-ttu-id="07056-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="07056-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07056-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="07056-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="07056-125">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="07056-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07056-126">См. также</span><span class="sxs-lookup"><span data-stu-id="07056-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="07056-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="07056-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="07056-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="07056-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
