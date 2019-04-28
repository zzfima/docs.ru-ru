---
title: <states> WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: fad6f9c8871f79e4a1e26c893eed86ba168f6d01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757954"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="96c04-102">\<состояния > WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="96c04-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="96c04-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="96c04-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="96c04-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="96c04-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="96c04-105">\<system.serviceModel > \<отслеживания ></span><span class="sxs-lookup"><span data-stu-id="96c04-105">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="96c04-106">\<профили ></span><span class="sxs-lookup"><span data-stu-id="96c04-106">\<profiles></span></span>  
<span data-ttu-id="96c04-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="96c04-107">\<trackingProfile></span></span>  
<span data-ttu-id="96c04-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="96c04-108">\<workflow></span></span>  
<span data-ttu-id="96c04-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="96c04-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="96c04-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="96c04-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="96c04-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="96c04-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c04-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96c04-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96c04-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="96c04-113">Attributes and elements</span></span>

<span data-ttu-id="96c04-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="96c04-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96c04-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="96c04-115">Attributes</span></span>  

<span data-ttu-id="96c04-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="96c04-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="96c04-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="96c04-117">Child elements</span></span>
  
|<span data-ttu-id="96c04-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="96c04-118">Element</span></span>|<span data-ttu-id="96c04-119">Описание</span><span class="sxs-lookup"><span data-stu-id="96c04-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96c04-120">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="96c04-120">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="96c04-121">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="96c04-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96c04-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="96c04-122">Parent elements</span></span>  
  
|<span data-ttu-id="96c04-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="96c04-123">Element</span></span>|<span data-ttu-id="96c04-124">Описание</span><span class="sxs-lookup"><span data-stu-id="96c04-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96c04-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="96c04-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="96c04-126">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="96c04-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96c04-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="96c04-127">Remarks</span></span>

<span data-ttu-id="96c04-128">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="96c04-128">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="96c04-129">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="96c04-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="96c04-130">Регион</span><span class="sxs-lookup"><span data-stu-id="96c04-130">State</span></span>|<span data-ttu-id="96c04-131">Описание</span><span class="sxs-lookup"><span data-stu-id="96c04-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="96c04-132">Прерывание</span><span class="sxs-lookup"><span data-stu-id="96c04-132">Aborted</span></span>|<span data-ttu-id="96c04-133">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="96c04-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="96c04-134">Завершено</span><span class="sxs-lookup"><span data-stu-id="96c04-134">Completed</span></span>|<span data-ttu-id="96c04-135">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="96c04-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="96c04-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="96c04-136">Deleted</span></span>|<span data-ttu-id="96c04-137">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="96c04-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="96c04-138">Бездействие</span><span class="sxs-lookup"><span data-stu-id="96c04-138">Idle</span></span>|<span data-ttu-id="96c04-139">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="96c04-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="96c04-140">Сохранение</span><span class="sxs-lookup"><span data-stu-id="96c04-140">Persisted</span></span>|<span data-ttu-id="96c04-141">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="96c04-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="96c04-142">Возобновление</span><span class="sxs-lookup"><span data-stu-id="96c04-142">Resumed</span></span>|<span data-ttu-id="96c04-143">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="96c04-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="96c04-144">Запуск</span><span class="sxs-lookup"><span data-stu-id="96c04-144">Started</span></span>|<span data-ttu-id="96c04-145">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="96c04-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="96c04-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="96c04-146">UnhandledException</span></span>|<span data-ttu-id="96c04-147">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="96c04-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="96c04-148">Выгружен</span><span class="sxs-lookup"><span data-stu-id="96c04-148">Unloaded</span></span>|<span data-ttu-id="96c04-149">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="96c04-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="96c04-150">Отменено</span><span class="sxs-lookup"><span data-stu-id="96c04-150">Canceled</span></span>|<span data-ttu-id="96c04-151">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="96c04-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="96c04-152">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="96c04-152">Suspended</span></span>|<span data-ttu-id="96c04-153">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="96c04-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="96c04-154">Завершение</span><span class="sxs-lookup"><span data-stu-id="96c04-154">Terminated</span></span>|<span data-ttu-id="96c04-155">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="96c04-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="96c04-156">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="96c04-156">Unsuspended</span></span>|<span data-ttu-id="96c04-157">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="96c04-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96c04-158">Пример</span><span class="sxs-lookup"><span data-stu-id="96c04-158">Example</span></span>

<span data-ttu-id="96c04-159">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="96c04-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="96c04-160">См. также</span><span class="sxs-lookup"><span data-stu-id="96c04-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="96c04-161">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="96c04-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="96c04-162">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="96c04-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
