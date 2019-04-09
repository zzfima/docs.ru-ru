---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 6f1a9474f3f12005df364a6fb84dc63aa1b68e04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108179"
---
# <a name="state"></a><span data-ttu-id="e175a-101">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="e175a-101">\<state></span></span>
<span data-ttu-id="e175a-102">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e175a-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="e175a-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e175a-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e175a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e175a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e175a-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="e175a-105">\<tracking></span></span>  
<span data-ttu-id="e175a-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e175a-106">\<trackingProfile></span></span>  
<span data-ttu-id="e175a-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="e175a-107">\<workflow></span></span>  
<span data-ttu-id="e175a-108">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="e175a-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="e175a-109">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="e175a-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="e175a-110">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="e175a-110">\<states></span></span>  
<span data-ttu-id="e175a-111">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="e175a-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e175a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e175a-112">Syntax</span></span>  
  
```xml  
<tracking>
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
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e175a-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e175a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e175a-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e175a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e175a-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e175a-115">Attributes</span></span>  
  
|<span data-ttu-id="e175a-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e175a-116">Attribute</span></span>|<span data-ttu-id="e175a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e175a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e175a-118">имя</span><span class="sxs-lookup"><span data-stu-id="e175a-118">name</span></span>|<span data-ttu-id="e175a-119">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e175a-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e175a-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e175a-120">Child Elements</span></span>  
 <span data-ttu-id="e175a-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e175a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e175a-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e175a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e175a-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e175a-123">Element</span></span>|<span data-ttu-id="e175a-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e175a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e175a-125">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="e175a-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="e175a-126">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e175a-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e175a-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="e175a-127">Remarks</span></span>  
 <span data-ttu-id="e175a-128">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e175a-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="e175a-129">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e175a-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e175a-130">Регион</span><span class="sxs-lookup"><span data-stu-id="e175a-130">State</span></span>|<span data-ttu-id="e175a-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e175a-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e175a-132">Прерывание</span><span class="sxs-lookup"><span data-stu-id="e175a-132">Aborted</span></span>|<span data-ttu-id="e175a-133">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="e175a-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e175a-134">Завершено</span><span class="sxs-lookup"><span data-stu-id="e175a-134">Completed</span></span>|<span data-ttu-id="e175a-135">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="e175a-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e175a-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="e175a-136">Deleted</span></span>|<span data-ttu-id="e175a-137">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="e175a-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e175a-138">Бездействие</span><span class="sxs-lookup"><span data-stu-id="e175a-138">Idle</span></span>|<span data-ttu-id="e175a-139">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="e175a-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e175a-140">Сохранение</span><span class="sxs-lookup"><span data-stu-id="e175a-140">Persisted</span></span>|<span data-ttu-id="e175a-141">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="e175a-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e175a-142">Возобновление</span><span class="sxs-lookup"><span data-stu-id="e175a-142">Resumed</span></span>|<span data-ttu-id="e175a-143">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="e175a-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e175a-144">Запуск</span><span class="sxs-lookup"><span data-stu-id="e175a-144">Started</span></span>|<span data-ttu-id="e175a-145">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="e175a-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e175a-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e175a-146">UnhandledException</span></span>|<span data-ttu-id="e175a-147">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="e175a-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e175a-148">Выгружен</span><span class="sxs-lookup"><span data-stu-id="e175a-148">Unloaded</span></span>|<span data-ttu-id="e175a-149">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="e175a-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e175a-150">Отменено</span><span class="sxs-lookup"><span data-stu-id="e175a-150">Canceled</span></span>|<span data-ttu-id="e175a-151">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="e175a-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e175a-152">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="e175a-152">Suspended</span></span>|<span data-ttu-id="e175a-153">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="e175a-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e175a-154">Завершение</span><span class="sxs-lookup"><span data-stu-id="e175a-154">Terminated</span></span>|<span data-ttu-id="e175a-155">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="e175a-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e175a-156">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="e175a-156">Unsuspended</span></span>|<span data-ttu-id="e175a-157">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="e175a-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e175a-158">Пример</span><span class="sxs-lookup"><span data-stu-id="e175a-158">Example</span></span>  
 <span data-ttu-id="e175a-159">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="e175a-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e175a-160">См. также</span><span class="sxs-lookup"><span data-stu-id="e175a-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e175a-161">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e175a-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e175a-162">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e175a-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
