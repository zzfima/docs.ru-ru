---
title: "&lt;состояния&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5e9050a01cf58c3c103fdbe4e8b22e173efaf5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt"></a><span data-ttu-id="47692-102">&lt;состояния&gt;</span><span class="sxs-lookup"><span data-stu-id="47692-102">&lt;states&gt;</span></span>
<span data-ttu-id="47692-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="47692-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="47692-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="47692-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="47692-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="47692-105">\<system.serviceModel></span></span>  
<span data-ttu-id="47692-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="47692-106">\<tracking></span></span>  
<span data-ttu-id="47692-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="47692-107">\<trackingProfile></span></span>  
<span data-ttu-id="47692-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="47692-108">\<workflow></span></span>  
<span data-ttu-id="47692-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="47692-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="47692-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="47692-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="47692-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="47692-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47692-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47692-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47692-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47692-113">Attributes and Elements</span></span>  
 <span data-ttu-id="47692-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47692-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47692-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47692-115">Attributes</span></span>  
 <span data-ttu-id="47692-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="47692-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47692-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47692-117">Child Elements</span></span>  
  
|<span data-ttu-id="47692-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="47692-118">Element</span></span>|<span data-ttu-id="47692-119">Описание</span><span class="sxs-lookup"><span data-stu-id="47692-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47692-120">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="47692-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="47692-121">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="47692-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47692-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47692-122">Parent Elements</span></span>  
  
|<span data-ttu-id="47692-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="47692-123">Element</span></span>|<span data-ttu-id="47692-124">Описание</span><span class="sxs-lookup"><span data-stu-id="47692-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47692-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="47692-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="47692-126">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="47692-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47692-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="47692-127">Remarks</span></span>  
 <span data-ttu-id="47692-128">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="47692-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="47692-129">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="47692-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="47692-130">Состояние</span><span class="sxs-lookup"><span data-stu-id="47692-130">State</span></span>|<span data-ttu-id="47692-131">Описание</span><span class="sxs-lookup"><span data-stu-id="47692-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47692-132">Прерывание</span><span class="sxs-lookup"><span data-stu-id="47692-132">Aborted</span></span>|<span data-ttu-id="47692-133">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="47692-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="47692-134">Завершение</span><span class="sxs-lookup"><span data-stu-id="47692-134">Completed</span></span>|<span data-ttu-id="47692-135">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="47692-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="47692-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="47692-136">Deleted</span></span>|<span data-ttu-id="47692-137">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="47692-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="47692-138">Бездействие</span><span class="sxs-lookup"><span data-stu-id="47692-138">Idle</span></span>|<span data-ttu-id="47692-139">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="47692-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="47692-140">Сохранение</span><span class="sxs-lookup"><span data-stu-id="47692-140">Persisted</span></span>|<span data-ttu-id="47692-141">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="47692-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="47692-142">Возобновление</span><span class="sxs-lookup"><span data-stu-id="47692-142">Resumed</span></span>|<span data-ttu-id="47692-143">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="47692-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="47692-144">Запуск</span><span class="sxs-lookup"><span data-stu-id="47692-144">Started</span></span>|<span data-ttu-id="47692-145">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="47692-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="47692-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="47692-146">UnhandledException</span></span>|<span data-ttu-id="47692-147">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="47692-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="47692-148">выгружаемые</span><span class="sxs-lookup"><span data-stu-id="47692-148">Unloaded</span></span>|<span data-ttu-id="47692-149">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="47692-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="47692-150">Отменено</span><span class="sxs-lookup"><span data-stu-id="47692-150">Canceled</span></span>|<span data-ttu-id="47692-151">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="47692-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="47692-152">Приостановлено</span><span class="sxs-lookup"><span data-stu-id="47692-152">Suspended</span></span>|<span data-ttu-id="47692-153">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="47692-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="47692-154">Завершение</span><span class="sxs-lookup"><span data-stu-id="47692-154">Terminated</span></span>|<span data-ttu-id="47692-155">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="47692-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="47692-156">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="47692-156">Unsuspended</span></span>|<span data-ttu-id="47692-157">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="47692-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="47692-158">Пример</span><span class="sxs-lookup"><span data-stu-id="47692-158">Example</span></span>  
 <span data-ttu-id="47692-159">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="47692-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47692-160">См. также</span><span class="sxs-lookup"><span data-stu-id="47692-160">See Also</span></span>  
 <span data-ttu-id="47692-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="47692-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="47692-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="47692-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="47692-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="47692-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="47692-164">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="47692-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="47692-165">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="47692-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
