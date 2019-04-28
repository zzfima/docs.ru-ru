---
title: <activityStateQuery> для WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 97fce512415ad6ae165b29c7e8eff3394d5e675a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704535"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="ad17a-102">\<activityStateQuery > из WCF</span><span class="sxs-lookup"><span data-stu-id="ad17a-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="ad17a-103">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ad17a-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ad17a-104">Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ad17a-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ad17a-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="ad17a-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ad17a-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="ad17a-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="ad17a-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ad17a-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="ad17a-108">\<system.serviceModel > \<отслеживания ></span><span class="sxs-lookup"><span data-stu-id="ad17a-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="ad17a-109">\<профили > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ad17a-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="ad17a-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ad17a-110">\<workflow></span></span>  
<span data-ttu-id="ad17a-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ad17a-111">\<activityStateQueries></span></span>  
<span data-ttu-id="ad17a-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ad17a-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad17a-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad17a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad17a-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad17a-114">Attributes and elements</span></span>  

<span data-ttu-id="ad17a-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad17a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad17a-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad17a-116">Attributes</span></span>  
  
|<span data-ttu-id="ad17a-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ad17a-117">Attribute</span></span>|<span data-ttu-id="ad17a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ad17a-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad17a-119">activityName</span><span class="sxs-lookup"><span data-stu-id="ad17a-119">activityName</span></span>|<span data-ttu-id="ad17a-120">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="ad17a-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad17a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad17a-121">Child elements</span></span>  
  
|<span data-ttu-id="ad17a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad17a-122">Element</span></span>|<span data-ttu-id="ad17a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ad17a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad17a-124">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="ad17a-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="ad17a-125">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="ad17a-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="ad17a-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="ad17a-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="ad17a-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ad17a-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="ad17a-128">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="ad17a-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="ad17a-129">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="ad17a-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad17a-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad17a-130">Parent elements</span></span>  
  
|<span data-ttu-id="ad17a-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad17a-131">Element</span></span>|<span data-ttu-id="ad17a-132">Описание</span><span class="sxs-lookup"><span data-stu-id="ad17a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad17a-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ad17a-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="ad17a-134">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="ad17a-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ad17a-135">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="ad17a-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad17a-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad17a-136">Remarks</span></span>

<span data-ttu-id="ad17a-137">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ad17a-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ad17a-138">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad17a-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ad17a-139">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ad17a-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ad17a-140">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="ad17a-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="ad17a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ad17a-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="ad17a-142">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ad17a-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ad17a-143">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ad17a-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
