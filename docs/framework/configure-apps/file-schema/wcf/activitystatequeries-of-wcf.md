---
title: <activityStateQueries>WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 415cd4a75ecab725f91bcd298f8a7966ea6079d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920302"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="8f275-102">\<Активитистатекуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="8f275-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="8f275-103">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8f275-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8f275-104">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8f275-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8f275-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="8f275-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8f275-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="8f275-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="8f275-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8f275-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="8f275-108">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="8f275-108">\<system.serviceModel></span></span>  
<span data-ttu-id="8f275-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8f275-109">\<tracking></span></span>  
<span data-ttu-id="8f275-110">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="8f275-110">\<profiles></span></span>  
<span data-ttu-id="8f275-111">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8f275-111">\<trackingProfile></span></span>  
<span data-ttu-id="8f275-112">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8f275-112">\<workflow></span></span>  
<span data-ttu-id="8f275-113">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="8f275-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="8f275-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f275-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="8f275-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8f275-115">Attributes and elements</span></span>

<span data-ttu-id="8f275-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8f275-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8f275-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8f275-117">Attributes</span></span>  

<span data-ttu-id="8f275-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="8f275-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="8f275-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8f275-119">Child elements</span></span>

|<span data-ttu-id="8f275-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f275-120">Element</span></span>|<span data-ttu-id="8f275-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8f275-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f275-122">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="8f275-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="8f275-123">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="8f275-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8f275-124">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="8f275-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8f275-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8f275-125">Parent elements</span></span>

|<span data-ttu-id="8f275-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f275-126">Element</span></span>|<span data-ttu-id="8f275-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8f275-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f275-128">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8f275-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="8f275-129">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8f275-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="8f275-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8f275-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="8f275-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8f275-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8f275-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8f275-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
