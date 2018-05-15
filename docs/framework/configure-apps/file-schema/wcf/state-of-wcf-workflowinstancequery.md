---
title: '&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 69ebedec40243d3e6580b8350c1253fca83e0802
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="d0cc5-102">&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="d0cc5-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="d0cc5-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="d0cc5-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d0cc5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="d0cc5-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d0cc5-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-106">\<tracking></span></span>  
<span data-ttu-id="d0cc5-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-107">\<trackingProfile></span></span>  
<span data-ttu-id="d0cc5-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-108">\<workflow></span></span>  
<span data-ttu-id="d0cc5-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="d0cc5-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="d0cc5-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-111">\<states></span></span>  
<span data-ttu-id="d0cc5-112">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0cc5-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0cc5-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0cc5-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0cc5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="d0cc5-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0cc5-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0cc5-116">Attributes</span></span>  
  
|<span data-ttu-id="d0cc5-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0cc5-117">Attribute</span></span>|<span data-ttu-id="d0cc5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d0cc5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0cc5-119">имя</span><span class="sxs-lookup"><span data-stu-id="d0cc5-119">name</span></span>|<span data-ttu-id="d0cc5-120">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0cc5-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0cc5-121">Child Elements</span></span>  
 <span data-ttu-id="d0cc5-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0cc5-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0cc5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d0cc5-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0cc5-124">Element</span></span>|<span data-ttu-id="d0cc5-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d0cc5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0cc5-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d0cc5-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="d0cc5-127">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0cc5-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0cc5-128">Remarks</span></span>  
 <span data-ttu-id="d0cc5-129">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="d0cc5-130">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="d0cc5-131">Состояние</span><span class="sxs-lookup"><span data-stu-id="d0cc5-131">State</span></span>|<span data-ttu-id="d0cc5-132">Описание</span><span class="sxs-lookup"><span data-stu-id="d0cc5-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0cc5-133">Прерывание</span><span class="sxs-lookup"><span data-stu-id="d0cc5-133">Aborted</span></span>|<span data-ttu-id="d0cc5-134">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d0cc5-135">Завершение</span><span class="sxs-lookup"><span data-stu-id="d0cc5-135">Completed</span></span>|<span data-ttu-id="d0cc5-136">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="d0cc5-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="d0cc5-137">Deleted</span></span>|<span data-ttu-id="d0cc5-138">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="d0cc5-139">Бездействие</span><span class="sxs-lookup"><span data-stu-id="d0cc5-139">Idle</span></span>|<span data-ttu-id="d0cc5-140">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="d0cc5-141">Сохранение</span><span class="sxs-lookup"><span data-stu-id="d0cc5-141">Persisted</span></span>|<span data-ttu-id="d0cc5-142">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="d0cc5-143">Возобновление</span><span class="sxs-lookup"><span data-stu-id="d0cc5-143">Resumed</span></span>|<span data-ttu-id="d0cc5-144">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="d0cc5-145">Запуск</span><span class="sxs-lookup"><span data-stu-id="d0cc5-145">Started</span></span>|<span data-ttu-id="d0cc5-146">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="d0cc5-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="d0cc5-147">UnhandledException</span></span>|<span data-ttu-id="d0cc5-148">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="d0cc5-149">выгружаемые</span><span class="sxs-lookup"><span data-stu-id="d0cc5-149">Unloaded</span></span>|<span data-ttu-id="d0cc5-150">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="d0cc5-151">Отменено</span><span class="sxs-lookup"><span data-stu-id="d0cc5-151">Canceled</span></span>|<span data-ttu-id="d0cc5-152">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="d0cc5-153">Приостановлено</span><span class="sxs-lookup"><span data-stu-id="d0cc5-153">Suspended</span></span>|<span data-ttu-id="d0cc5-154">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="d0cc5-155">Завершение</span><span class="sxs-lookup"><span data-stu-id="d0cc5-155">Terminated</span></span>|<span data-ttu-id="d0cc5-156">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="d0cc5-157">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="d0cc5-157">Unsuspended</span></span>|<span data-ttu-id="d0cc5-158">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0cc5-159">Пример</span><span class="sxs-lookup"><span data-stu-id="d0cc5-159">Example</span></span>  
 <span data-ttu-id="d0cc5-160">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="d0cc5-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0cc5-161">См. также</span><span class="sxs-lookup"><span data-stu-id="d0cc5-161">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="d0cc5-162">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d0cc5-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d0cc5-163">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d0cc5-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
