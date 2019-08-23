---
title: <state>WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 99387a8f60e96beb2ec7706d9abf4bb6ae84b868
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938212"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="7194e-102">\<> состояния WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="7194e-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="7194e-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7194e-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="7194e-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="7194e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7194e-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="7194e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="7194e-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="7194e-106">\<tracking></span></span>  
<span data-ttu-id="7194e-107">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="7194e-107">\<profiles></span></span>  
<span data-ttu-id="7194e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7194e-108">\<trackingProfile></span></span>  
<span data-ttu-id="7194e-109">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7194e-109">\<workflow></span></span>  
<span data-ttu-id="7194e-110">\<Воркфловинстанцекуериес ></span><span class="sxs-lookup"><span data-stu-id="7194e-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="7194e-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="7194e-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="7194e-112">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="7194e-112">\<states></span></span>  
<span data-ttu-id="7194e-113">\<> состояния</span><span class="sxs-lookup"><span data-stu-id="7194e-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7194e-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7194e-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7194e-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7194e-115">Attributes and elements</span></span>

<span data-ttu-id="7194e-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7194e-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7194e-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7194e-117">Attributes</span></span>

|<span data-ttu-id="7194e-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7194e-118">Attribute</span></span>|<span data-ttu-id="7194e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7194e-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="7194e-120">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7194e-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7194e-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7194e-121">Child elements</span></span>

<span data-ttu-id="7194e-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="7194e-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7194e-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7194e-123">Parent elements</span></span>

|<span data-ttu-id="7194e-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="7194e-124">Element</span></span>|<span data-ttu-id="7194e-125">Описание</span><span class="sxs-lookup"><span data-stu-id="7194e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7194e-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="7194e-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="7194e-127">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7194e-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7194e-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="7194e-128">Remarks</span></span>  

<span data-ttu-id="7194e-129">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="7194e-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="7194e-130">Возможные значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7194e-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="7194e-131">Область</span><span class="sxs-lookup"><span data-stu-id="7194e-131">State</span></span>|<span data-ttu-id="7194e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="7194e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7194e-133">Прерывание</span><span class="sxs-lookup"><span data-stu-id="7194e-133">Aborted</span></span>|<span data-ttu-id="7194e-134">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="7194e-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="7194e-135">Завершено</span><span class="sxs-lookup"><span data-stu-id="7194e-135">Completed</span></span>|<span data-ttu-id="7194e-136">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="7194e-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="7194e-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="7194e-137">Deleted</span></span>|<span data-ttu-id="7194e-138">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="7194e-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="7194e-139">Бездействие</span><span class="sxs-lookup"><span data-stu-id="7194e-139">Idle</span></span>|<span data-ttu-id="7194e-140">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="7194e-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="7194e-141">Сохранение</span><span class="sxs-lookup"><span data-stu-id="7194e-141">Persisted</span></span>|<span data-ttu-id="7194e-142">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="7194e-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="7194e-143">Возобновление</span><span class="sxs-lookup"><span data-stu-id="7194e-143">Resumed</span></span>|<span data-ttu-id="7194e-144">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="7194e-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="7194e-145">Запуск</span><span class="sxs-lookup"><span data-stu-id="7194e-145">Started</span></span>|<span data-ttu-id="7194e-146">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="7194e-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="7194e-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="7194e-147">UnhandledException</span></span>|<span data-ttu-id="7194e-148">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="7194e-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="7194e-149">Выгружен</span><span class="sxs-lookup"><span data-stu-id="7194e-149">Unloaded</span></span>|<span data-ttu-id="7194e-150">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="7194e-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="7194e-151">Отменено</span><span class="sxs-lookup"><span data-stu-id="7194e-151">Canceled</span></span>|<span data-ttu-id="7194e-152">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="7194e-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="7194e-153">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="7194e-153">Suspended</span></span>|<span data-ttu-id="7194e-154">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="7194e-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="7194e-155">Завершение</span><span class="sxs-lookup"><span data-stu-id="7194e-155">Terminated</span></span>|<span data-ttu-id="7194e-156">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="7194e-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="7194e-157">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="7194e-157">Unsuspended</span></span>|<span data-ttu-id="7194e-158">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="7194e-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7194e-159">Пример</span><span class="sxs-lookup"><span data-stu-id="7194e-159">Example</span></span>

<span data-ttu-id="7194e-160">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="7194e-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="7194e-161">См. также</span><span class="sxs-lookup"><span data-stu-id="7194e-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7194e-162">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7194e-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7194e-163">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7194e-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
