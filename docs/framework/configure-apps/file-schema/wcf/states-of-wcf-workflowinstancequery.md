---
title: '&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef3d8d05dad684b07ee527dbd34ae6269ae57657
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749492"
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="359c9-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="359c9-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="359c9-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="359c9-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="359c9-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="359c9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="359c9-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="359c9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="359c9-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="359c9-106">\<tracking></span></span>  
<span data-ttu-id="359c9-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="359c9-107">\<trackingProfile></span></span>  
<span data-ttu-id="359c9-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="359c9-108">\<workflow></span></span>  
<span data-ttu-id="359c9-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="359c9-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="359c9-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="359c9-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="359c9-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="359c9-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359c9-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="359c9-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="359c9-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="359c9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="359c9-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="359c9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="359c9-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="359c9-115">Attributes</span></span>  
 <span data-ttu-id="359c9-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="359c9-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="359c9-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="359c9-117">Child Elements</span></span>  
  
|<span data-ttu-id="359c9-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="359c9-118">Element</span></span>|<span data-ttu-id="359c9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="359c9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="359c9-120">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="359c9-120">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="359c9-121">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="359c9-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="359c9-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="359c9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="359c9-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="359c9-123">Element</span></span>|<span data-ttu-id="359c9-124">Описание</span><span class="sxs-lookup"><span data-stu-id="359c9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="359c9-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="359c9-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="359c9-126">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="359c9-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="359c9-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="359c9-127">Remarks</span></span>  
 <span data-ttu-id="359c9-128">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="359c9-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="359c9-129">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="359c9-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="359c9-130">Состояние</span><span class="sxs-lookup"><span data-stu-id="359c9-130">State</span></span>|<span data-ttu-id="359c9-131">Описание</span><span class="sxs-lookup"><span data-stu-id="359c9-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="359c9-132">Прерывание</span><span class="sxs-lookup"><span data-stu-id="359c9-132">Aborted</span></span>|<span data-ttu-id="359c9-133">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="359c9-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="359c9-134">Завершение</span><span class="sxs-lookup"><span data-stu-id="359c9-134">Completed</span></span>|<span data-ttu-id="359c9-135">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="359c9-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="359c9-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="359c9-136">Deleted</span></span>|<span data-ttu-id="359c9-137">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="359c9-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="359c9-138">Бездействие</span><span class="sxs-lookup"><span data-stu-id="359c9-138">Idle</span></span>|<span data-ttu-id="359c9-139">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="359c9-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="359c9-140">Сохранение</span><span class="sxs-lookup"><span data-stu-id="359c9-140">Persisted</span></span>|<span data-ttu-id="359c9-141">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="359c9-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="359c9-142">Возобновление</span><span class="sxs-lookup"><span data-stu-id="359c9-142">Resumed</span></span>|<span data-ttu-id="359c9-143">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="359c9-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="359c9-144">Запуск</span><span class="sxs-lookup"><span data-stu-id="359c9-144">Started</span></span>|<span data-ttu-id="359c9-145">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="359c9-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="359c9-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="359c9-146">UnhandledException</span></span>|<span data-ttu-id="359c9-147">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="359c9-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="359c9-148">выгружаемые</span><span class="sxs-lookup"><span data-stu-id="359c9-148">Unloaded</span></span>|<span data-ttu-id="359c9-149">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="359c9-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="359c9-150">Отменено</span><span class="sxs-lookup"><span data-stu-id="359c9-150">Canceled</span></span>|<span data-ttu-id="359c9-151">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="359c9-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="359c9-152">Приостановлено</span><span class="sxs-lookup"><span data-stu-id="359c9-152">Suspended</span></span>|<span data-ttu-id="359c9-153">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="359c9-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="359c9-154">Завершение</span><span class="sxs-lookup"><span data-stu-id="359c9-154">Terminated</span></span>|<span data-ttu-id="359c9-155">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="359c9-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="359c9-156">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="359c9-156">Unsuspended</span></span>|<span data-ttu-id="359c9-157">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="359c9-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="359c9-158">Пример</span><span class="sxs-lookup"><span data-stu-id="359c9-158">Example</span></span>  
 <span data-ttu-id="359c9-159">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="359c9-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="359c9-160">См. также</span><span class="sxs-lookup"><span data-stu-id="359c9-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="359c9-161">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="359c9-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="359c9-162">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="359c9-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
