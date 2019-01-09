---
title: '&lt;activityStateQueries&gt; (WCF)'
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 2dabfdd248006de60b5e84e739f78e03f364dde3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146190"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="df59b-102">&lt;activityStateQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="df59b-102">&lt;activityStateQueries&gt; of WCF</span></span>

<span data-ttu-id="df59b-103">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="df59b-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="df59b-104">Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="df59b-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="df59b-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="df59b-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="df59b-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="df59b-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="df59b-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="df59b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="df59b-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="df59b-108">\<system.serviceModel></span></span>  
<span data-ttu-id="df59b-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="df59b-109">\<tracking></span></span>  
<span data-ttu-id="df59b-110">\<профили ></span><span class="sxs-lookup"><span data-stu-id="df59b-110">\<profiles></span></span>  
<span data-ttu-id="df59b-111">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="df59b-111">\<trackingProfile></span></span>  
<span data-ttu-id="df59b-112">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="df59b-112">\<workflow></span></span>  
<span data-ttu-id="df59b-113">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="df59b-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="df59b-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df59b-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="df59b-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="df59b-115">Attributes and elements</span></span>

<span data-ttu-id="df59b-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="df59b-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="df59b-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df59b-117">Attributes</span></span>  

<span data-ttu-id="df59b-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="df59b-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="df59b-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df59b-119">Child elements</span></span>

|<span data-ttu-id="df59b-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="df59b-120">Element</span></span>|<span data-ttu-id="df59b-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="df59b-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df59b-122">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="df59b-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="df59b-123">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="df59b-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="df59b-124">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="df59b-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="df59b-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df59b-125">Parent elements</span></span>

|<span data-ttu-id="df59b-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="df59b-126">Element</span></span>|<span data-ttu-id="df59b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="df59b-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df59b-128">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="df59b-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="df59b-129">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="df59b-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="df59b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="df59b-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
- <xref:System.Activities.Tracking.ActivityStateQuery>    
- [<span data-ttu-id="df59b-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="df59b-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="df59b-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="df59b-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
