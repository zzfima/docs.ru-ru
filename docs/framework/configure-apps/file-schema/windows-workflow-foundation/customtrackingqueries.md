---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790225"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="5103e-101">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="5103e-101">\<customTrackingQueries></span></span>
<span data-ttu-id="5103e-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="5103e-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5103e-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5103e-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5103e-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5103e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5103e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5103e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5103e-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="5103e-106">\<tracking></span></span>  
<span data-ttu-id="5103e-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5103e-107">\<trackingProfile></span></span>  
<span data-ttu-id="5103e-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="5103e-108">\<workflow></span></span>  
<span data-ttu-id="5103e-109">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="5103e-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5103e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5103e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5103e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5103e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5103e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5103e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5103e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5103e-113">Attributes</span></span>  
 <span data-ttu-id="5103e-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5103e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5103e-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5103e-115">Child Elements</span></span>  
  
|<span data-ttu-id="5103e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="5103e-116">Element</span></span>|<span data-ttu-id="5103e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5103e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5103e-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="5103e-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="5103e-119">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="5103e-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5103e-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5103e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5103e-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="5103e-121">Element</span></span>|<span data-ttu-id="5103e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5103e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5103e-123">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="5103e-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5103e-124">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="5103e-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5103e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5103e-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5103e-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="5103e-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5103e-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="5103e-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
