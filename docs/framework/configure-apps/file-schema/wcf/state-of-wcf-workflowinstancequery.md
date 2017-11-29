---
title: '&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e26a55323ceedd06ceadbee6d993306411aa114a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="46750-102">&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="46750-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="46750-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="46750-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="46750-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="46750-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="46750-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="46750-105">\<system.serviceModel></span></span>  
<span data-ttu-id="46750-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="46750-106">\<tracking></span></span>  
<span data-ttu-id="46750-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="46750-107">\<trackingProfile></span></span>  
<span data-ttu-id="46750-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="46750-108">\<workflow></span></span>  
<span data-ttu-id="46750-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="46750-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="46750-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="46750-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="46750-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="46750-111">\<states></span></span>  
<span data-ttu-id="46750-112">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="46750-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46750-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46750-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46750-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46750-114">Attributes and Elements</span></span>  
 <span data-ttu-id="46750-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46750-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46750-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46750-116">Attributes</span></span>  
  
|<span data-ttu-id="46750-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="46750-117">Attribute</span></span>|<span data-ttu-id="46750-118">Описание</span><span class="sxs-lookup"><span data-stu-id="46750-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46750-119">имя</span><span class="sxs-lookup"><span data-stu-id="46750-119">name</span></span>|<span data-ttu-id="46750-120">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="46750-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46750-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46750-121">Child Elements</span></span>  
 <span data-ttu-id="46750-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="46750-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46750-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46750-123">Parent Elements</span></span>  
  
|<span data-ttu-id="46750-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="46750-124">Element</span></span>|<span data-ttu-id="46750-125">Описание</span><span class="sxs-lookup"><span data-stu-id="46750-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46750-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="46750-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="46750-127">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="46750-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46750-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="46750-128">Remarks</span></span>  
 <span data-ttu-id="46750-129">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="46750-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="46750-130">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="46750-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="46750-131">Состояние</span><span class="sxs-lookup"><span data-stu-id="46750-131">State</span></span>|<span data-ttu-id="46750-132">Описание</span><span class="sxs-lookup"><span data-stu-id="46750-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="46750-133">Прерывание</span><span class="sxs-lookup"><span data-stu-id="46750-133">Aborted</span></span>|<span data-ttu-id="46750-134">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="46750-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="46750-135">Завершение</span><span class="sxs-lookup"><span data-stu-id="46750-135">Completed</span></span>|<span data-ttu-id="46750-136">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="46750-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="46750-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="46750-137">Deleted</span></span>|<span data-ttu-id="46750-138">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="46750-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="46750-139">Бездействие</span><span class="sxs-lookup"><span data-stu-id="46750-139">Idle</span></span>|<span data-ttu-id="46750-140">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="46750-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="46750-141">Сохранение</span><span class="sxs-lookup"><span data-stu-id="46750-141">Persisted</span></span>|<span data-ttu-id="46750-142">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="46750-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="46750-143">Возобновление</span><span class="sxs-lookup"><span data-stu-id="46750-143">Resumed</span></span>|<span data-ttu-id="46750-144">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="46750-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="46750-145">Запуск</span><span class="sxs-lookup"><span data-stu-id="46750-145">Started</span></span>|<span data-ttu-id="46750-146">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="46750-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="46750-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="46750-147">UnhandledException</span></span>|<span data-ttu-id="46750-148">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="46750-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="46750-149">выгружаемые</span><span class="sxs-lookup"><span data-stu-id="46750-149">Unloaded</span></span>|<span data-ttu-id="46750-150">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="46750-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="46750-151">Отменено</span><span class="sxs-lookup"><span data-stu-id="46750-151">Canceled</span></span>|<span data-ttu-id="46750-152">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="46750-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="46750-153">Приостановлено</span><span class="sxs-lookup"><span data-stu-id="46750-153">Suspended</span></span>|<span data-ttu-id="46750-154">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="46750-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="46750-155">Завершение</span><span class="sxs-lookup"><span data-stu-id="46750-155">Terminated</span></span>|<span data-ttu-id="46750-156">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="46750-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="46750-157">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="46750-157">Unsuspended</span></span>|<span data-ttu-id="46750-158">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="46750-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46750-159">Пример</span><span class="sxs-lookup"><span data-stu-id="46750-159">Example</span></span>  
 <span data-ttu-id="46750-160">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="46750-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46750-161">См. также</span><span class="sxs-lookup"><span data-stu-id="46750-161">See Also</span></span>  
 <span data-ttu-id="46750-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46750-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="46750-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46750-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="46750-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46750-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="46750-165">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="46750-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="46750-166">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="46750-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
