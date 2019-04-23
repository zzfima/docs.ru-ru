---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073126"
---
# <a name="states"></a><span data-ttu-id="d4b0c-101">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-101">\<states></span></span>
<span data-ttu-id="d4b0c-102">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="d4b0c-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d4b0c-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d4b0c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d4b0c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d4b0c-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-105">\<tracking></span></span>  
<span data-ttu-id="d4b0c-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-106">\<trackingProfile></span></span>  
<span data-ttu-id="d4b0c-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-107">\<workflow></span></span>  
<span data-ttu-id="d4b0c-108">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="d4b0c-109">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="d4b0c-110">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b0c-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4b0c-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4b0c-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d4b0c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d4b0c-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4b0c-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d4b0c-114">Attributes</span></span>  
 <span data-ttu-id="d4b0c-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4b0c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d4b0c-116">Child Elements</span></span>  
  
|<span data-ttu-id="d4b0c-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="d4b0c-117">Element</span></span>|<span data-ttu-id="d4b0c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d4b0c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4b0c-119">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="d4b0c-120">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4b0c-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d4b0c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d4b0c-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="d4b0c-122">Element</span></span>|<span data-ttu-id="d4b0c-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d4b0c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4b0c-124">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="d4b0c-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="d4b0c-125">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4b0c-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4b0c-126">Remarks</span></span>  
 <span data-ttu-id="d4b0c-127">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="d4b0c-128">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="d4b0c-129">Регион</span><span class="sxs-lookup"><span data-stu-id="d4b0c-129">State</span></span>|<span data-ttu-id="d4b0c-130">Описание</span><span class="sxs-lookup"><span data-stu-id="d4b0c-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d4b0c-131">Прерывание</span><span class="sxs-lookup"><span data-stu-id="d4b0c-131">Aborted</span></span>|<span data-ttu-id="d4b0c-132">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d4b0c-133">Завершено</span><span class="sxs-lookup"><span data-stu-id="d4b0c-133">Completed</span></span>|<span data-ttu-id="d4b0c-134">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="d4b0c-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="d4b0c-135">Deleted</span></span>|<span data-ttu-id="d4b0c-136">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="d4b0c-137">Бездействие</span><span class="sxs-lookup"><span data-stu-id="d4b0c-137">Idle</span></span>|<span data-ttu-id="d4b0c-138">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="d4b0c-139">Сохранение</span><span class="sxs-lookup"><span data-stu-id="d4b0c-139">Persisted</span></span>|<span data-ttu-id="d4b0c-140">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="d4b0c-141">Возобновление</span><span class="sxs-lookup"><span data-stu-id="d4b0c-141">Resumed</span></span>|<span data-ttu-id="d4b0c-142">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="d4b0c-143">Запуск</span><span class="sxs-lookup"><span data-stu-id="d4b0c-143">Started</span></span>|<span data-ttu-id="d4b0c-144">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="d4b0c-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="d4b0c-145">UnhandledException</span></span>|<span data-ttu-id="d4b0c-146">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="d4b0c-147">Выгружен</span><span class="sxs-lookup"><span data-stu-id="d4b0c-147">Unloaded</span></span>|<span data-ttu-id="d4b0c-148">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="d4b0c-149">Отменено</span><span class="sxs-lookup"><span data-stu-id="d4b0c-149">Canceled</span></span>|<span data-ttu-id="d4b0c-150">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="d4b0c-151">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="d4b0c-151">Suspended</span></span>|<span data-ttu-id="d4b0c-152">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="d4b0c-153">Завершение</span><span class="sxs-lookup"><span data-stu-id="d4b0c-153">Terminated</span></span>|<span data-ttu-id="d4b0c-154">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="d4b0c-155">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="d4b0c-155">Unsuspended</span></span>|<span data-ttu-id="d4b0c-156">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4b0c-157">Пример</span><span class="sxs-lookup"><span data-stu-id="d4b0c-157">Example</span></span>  
 <span data-ttu-id="d4b0c-158">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="d4b0c-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4b0c-159">См. также</span><span class="sxs-lookup"><span data-stu-id="d4b0c-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d4b0c-160">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d4b0c-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d4b0c-161">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d4b0c-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
