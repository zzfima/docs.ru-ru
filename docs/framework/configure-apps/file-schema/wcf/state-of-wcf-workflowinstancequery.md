---
title: '&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 168a6980e955f602ee60bff26461f06cb16c836a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145930"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="5a240-102">&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="5a240-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="5a240-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5a240-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="5a240-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5a240-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5a240-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5a240-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5a240-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="5a240-106">\<tracking></span></span>  
<span data-ttu-id="5a240-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="5a240-107">\<profiles></span></span>  
<span data-ttu-id="5a240-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5a240-108">\<trackingProfile></span></span>  
<span data-ttu-id="5a240-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="5a240-109">\<workflow></span></span>  
<span data-ttu-id="5a240-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="5a240-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="5a240-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="5a240-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="5a240-112">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="5a240-112">\<states></span></span>  
<span data-ttu-id="5a240-113">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="5a240-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a240-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a240-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a240-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a240-115">Attributes and elements</span></span>

<span data-ttu-id="5a240-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5a240-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5a240-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a240-117">Attributes</span></span>

|<span data-ttu-id="5a240-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5a240-118">Attribute</span></span>|<span data-ttu-id="5a240-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5a240-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="5a240-120">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5a240-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a240-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5a240-121">Child elements</span></span>

<span data-ttu-id="5a240-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5a240-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5a240-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5a240-123">Parent elements</span></span>

|<span data-ttu-id="5a240-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a240-124">Element</span></span>|<span data-ttu-id="5a240-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5a240-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a240-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="5a240-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="5a240-127">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="5a240-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a240-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a240-128">Remarks</span></span>  

<span data-ttu-id="5a240-129">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="5a240-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="5a240-130">В следующей таблице описаны допустимые значения состояния:</span><span class="sxs-lookup"><span data-stu-id="5a240-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="5a240-131">Регион</span><span class="sxs-lookup"><span data-stu-id="5a240-131">State</span></span>|<span data-ttu-id="5a240-132">Описание</span><span class="sxs-lookup"><span data-stu-id="5a240-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a240-133">Прерывание</span><span class="sxs-lookup"><span data-stu-id="5a240-133">Aborted</span></span>|<span data-ttu-id="5a240-134">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="5a240-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="5a240-135">Завершение</span><span class="sxs-lookup"><span data-stu-id="5a240-135">Completed</span></span>|<span data-ttu-id="5a240-136">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="5a240-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="5a240-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="5a240-137">Deleted</span></span>|<span data-ttu-id="5a240-138">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="5a240-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="5a240-139">Бездействие</span><span class="sxs-lookup"><span data-stu-id="5a240-139">Idle</span></span>|<span data-ttu-id="5a240-140">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="5a240-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="5a240-141">Сохранение</span><span class="sxs-lookup"><span data-stu-id="5a240-141">Persisted</span></span>|<span data-ttu-id="5a240-142">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="5a240-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="5a240-143">Возобновление</span><span class="sxs-lookup"><span data-stu-id="5a240-143">Resumed</span></span>|<span data-ttu-id="5a240-144">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="5a240-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="5a240-145">Запуск</span><span class="sxs-lookup"><span data-stu-id="5a240-145">Started</span></span>|<span data-ttu-id="5a240-146">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="5a240-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="5a240-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="5a240-147">UnhandledException</span></span>|<span data-ttu-id="5a240-148">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="5a240-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="5a240-149">выгружаемые</span><span class="sxs-lookup"><span data-stu-id="5a240-149">Unloaded</span></span>|<span data-ttu-id="5a240-150">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="5a240-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="5a240-151">Отменено</span><span class="sxs-lookup"><span data-stu-id="5a240-151">Canceled</span></span>|<span data-ttu-id="5a240-152">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="5a240-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="5a240-153">Приостановлено</span><span class="sxs-lookup"><span data-stu-id="5a240-153">Suspended</span></span>|<span data-ttu-id="5a240-154">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="5a240-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="5a240-155">Завершение</span><span class="sxs-lookup"><span data-stu-id="5a240-155">Terminated</span></span>|<span data-ttu-id="5a240-156">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="5a240-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="5a240-157">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="5a240-157">Unsuspended</span></span>|<span data-ttu-id="5a240-158">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="5a240-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a240-159">Пример</span><span class="sxs-lookup"><span data-stu-id="5a240-159">Example</span></span>

<span data-ttu-id="5a240-160">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="5a240-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="5a240-161">См. также</span><span class="sxs-lookup"><span data-stu-id="5a240-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5a240-162">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="5a240-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5a240-163">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="5a240-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
