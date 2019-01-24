---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 5bc2e3ffeb93bdfcd45638d6b50e218c03706f42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520689"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="cb5f8-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="cb5f8-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="cb5f8-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="cb5f8-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="cb5f8-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cb5f8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cb5f8-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cb5f8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cb5f8-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="cb5f8-107">\<tracking></span></span>  
<span data-ttu-id="cb5f8-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cb5f8-108">\<trackingProfile></span></span>  
<span data-ttu-id="cb5f8-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="cb5f8-109">\<workflow></span></span>  
<span data-ttu-id="cb5f8-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="cb5f8-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb5f8-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb5f8-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb5f8-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb5f8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cb5f8-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb5f8-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb5f8-114">Attributes</span></span>  
 <span data-ttu-id="cb5f8-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cb5f8-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb5f8-116">Child Elements</span></span>  
  
|<span data-ttu-id="cb5f8-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb5f8-117">Element</span></span>|<span data-ttu-id="cb5f8-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="cb5f8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb5f8-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="cb5f8-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="cb5f8-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb5f8-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb5f8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cb5f8-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb5f8-122">Element</span></span>|<span data-ttu-id="cb5f8-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="cb5f8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb5f8-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="cb5f8-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="cb5f8-125">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb5f8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cb5f8-126">See also</span></span>
- [<span data-ttu-id="cb5f8-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="cb5f8-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cb5f8-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="cb5f8-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
