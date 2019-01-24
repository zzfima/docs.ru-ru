---
title: '&lt;activityStateQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: bfd19e00e79a95eb717ca9131e92b5ff5c600d5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511986"
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="3a201-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="3a201-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="3a201-103">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3a201-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3a201-104">Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3a201-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3a201-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="3a201-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3a201-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="3a201-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3a201-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3a201-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3a201-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3a201-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3a201-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="3a201-109">\<tracking></span></span>  
<span data-ttu-id="3a201-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3a201-110">\<trackingProfile></span></span>  
<span data-ttu-id="3a201-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="3a201-111">\<workflow></span></span>  
<span data-ttu-id="3a201-112">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="3a201-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a201-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a201-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a201-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a201-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3a201-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3a201-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a201-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a201-116">Attributes</span></span>  
 <span data-ttu-id="3a201-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3a201-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a201-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a201-118">Child Elements</span></span>  
  
|<span data-ttu-id="3a201-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a201-119">Element</span></span>|<span data-ttu-id="3a201-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="3a201-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a201-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="3a201-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="3a201-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="3a201-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3a201-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="3a201-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a201-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a201-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3a201-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a201-125">Element</span></span>|<span data-ttu-id="3a201-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="3a201-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a201-127">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="3a201-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3a201-128">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="3a201-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a201-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3a201-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3a201-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3a201-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a201-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="3a201-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
