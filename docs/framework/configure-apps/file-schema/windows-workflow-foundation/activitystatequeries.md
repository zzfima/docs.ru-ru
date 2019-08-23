---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 6e91078a24a950c6de027d57e3883e38f19447d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945455"
---
# <a name="activitystatequeries"></a><span data-ttu-id="13407-101">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="13407-101">\<activityStateQueries></span></span>
<span data-ttu-id="13407-102">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="13407-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="13407-103">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="13407-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="13407-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="13407-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="13407-105">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="13407-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="13407-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="13407-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="13407-107">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="13407-107">\<system.serviceModel></span></span>  
<span data-ttu-id="13407-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="13407-108">\<tracking></span></span>  
<span data-ttu-id="13407-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="13407-109">\<trackingProfile></span></span>  
<span data-ttu-id="13407-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="13407-110">\<workflow></span></span>  
<span data-ttu-id="13407-111">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="13407-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13407-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13407-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13407-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13407-113">Attributes and Elements</span></span>  
 <span data-ttu-id="13407-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13407-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13407-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13407-115">Attributes</span></span>  
 <span data-ttu-id="13407-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="13407-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13407-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13407-117">Child Elements</span></span>  
  
|<span data-ttu-id="13407-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="13407-118">Element</span></span>|<span data-ttu-id="13407-119">Описание</span><span class="sxs-lookup"><span data-stu-id="13407-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13407-120">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="13407-120">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="13407-121">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="13407-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="13407-122">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="13407-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13407-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13407-123">Parent Elements</span></span>  
  
|<span data-ttu-id="13407-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="13407-124">Element</span></span>|<span data-ttu-id="13407-125">Описание</span><span class="sxs-lookup"><span data-stu-id="13407-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13407-126">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="13407-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="13407-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="13407-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13407-128">См. также</span><span class="sxs-lookup"><span data-stu-id="13407-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="13407-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="13407-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="13407-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="13407-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
