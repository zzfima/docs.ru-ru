---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: ad41c1afec0b46a404f8f24882587c1dfeb68a80
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267811"
---
# <a name="activitystatequeries"></a><span data-ttu-id="6c23b-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6c23b-101">\<activityStateQueries></span></span>
<span data-ttu-id="6c23b-102">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6c23b-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="6c23b-103">Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6c23b-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="6c23b-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="6c23b-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="6c23b-105">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="6c23b-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="6c23b-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6c23b-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6c23b-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c23b-107">\<system.serviceModel></span></span>  
<span data-ttu-id="6c23b-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="6c23b-108">\<tracking></span></span>  
<span data-ttu-id="6c23b-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6c23b-109">\<trackingProfile></span></span>  
<span data-ttu-id="6c23b-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="6c23b-110">\<workflow></span></span>  
<span data-ttu-id="6c23b-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6c23b-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c23b-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c23b-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c23b-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c23b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6c23b-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c23b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c23b-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c23b-115">Attributes</span></span>  
 <span data-ttu-id="6c23b-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6c23b-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c23b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c23b-117">Child Elements</span></span>  
  
|<span data-ttu-id="6c23b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c23b-118">Element</span></span>|<span data-ttu-id="6c23b-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="6c23b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c23b-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6c23b-120">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="6c23b-121">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="6c23b-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6c23b-122">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="6c23b-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c23b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c23b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6c23b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c23b-124">Element</span></span>|<span data-ttu-id="6c23b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="6c23b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c23b-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="6c23b-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6c23b-127">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="6c23b-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c23b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6c23b-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c23b-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6c23b-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c23b-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="6c23b-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
