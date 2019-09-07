---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398622"
---
# <a name="states"></a><span data-ttu-id="a41b8-101">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="a41b8-101">\<states></span></span>
<span data-ttu-id="a41b8-102">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a41b8-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="a41b8-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a41b8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a41b8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a41b8-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="a41b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="a41b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="a41b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="a41b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Воркфловинстанцекуериес >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="a41b8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="a41b8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="a41b8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<состояния >**</span><span class="sxs-lookup"><span data-stu-id="a41b8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a41b8-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a41b8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a41b8-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a41b8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a41b8-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a41b8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a41b8-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a41b8-115">Attributes</span></span>  
 <span data-ttu-id="a41b8-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="a41b8-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a41b8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a41b8-117">Child Elements</span></span>  
  
|<span data-ttu-id="a41b8-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="a41b8-118">Element</span></span>|<span data-ttu-id="a41b8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a41b8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a41b8-120">\<> состояния</span><span class="sxs-lookup"><span data-stu-id="a41b8-120">\<state></span></span>](states.md)|<span data-ttu-id="a41b8-121">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a41b8-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a41b8-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a41b8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a41b8-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="a41b8-123">Element</span></span>|<span data-ttu-id="a41b8-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a41b8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a41b8-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="a41b8-125">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="a41b8-126">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="a41b8-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a41b8-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="a41b8-127">Remarks</span></span>  
 <span data-ttu-id="a41b8-128">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="a41b8-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="a41b8-129">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a41b8-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="a41b8-130">Область</span><span class="sxs-lookup"><span data-stu-id="a41b8-130">State</span></span>|<span data-ttu-id="a41b8-131">Описание</span><span class="sxs-lookup"><span data-stu-id="a41b8-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a41b8-132">Прерывание</span><span class="sxs-lookup"><span data-stu-id="a41b8-132">Aborted</span></span>|<span data-ttu-id="a41b8-133">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="a41b8-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="a41b8-134">Завершено</span><span class="sxs-lookup"><span data-stu-id="a41b8-134">Completed</span></span>|<span data-ttu-id="a41b8-135">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="a41b8-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="a41b8-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="a41b8-136">Deleted</span></span>|<span data-ttu-id="a41b8-137">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="a41b8-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="a41b8-138">Бездействие</span><span class="sxs-lookup"><span data-stu-id="a41b8-138">Idle</span></span>|<span data-ttu-id="a41b8-139">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="a41b8-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="a41b8-140">Сохранение</span><span class="sxs-lookup"><span data-stu-id="a41b8-140">Persisted</span></span>|<span data-ttu-id="a41b8-141">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="a41b8-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="a41b8-142">Возобновление</span><span class="sxs-lookup"><span data-stu-id="a41b8-142">Resumed</span></span>|<span data-ttu-id="a41b8-143">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="a41b8-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="a41b8-144">Запуск</span><span class="sxs-lookup"><span data-stu-id="a41b8-144">Started</span></span>|<span data-ttu-id="a41b8-145">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="a41b8-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="a41b8-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="a41b8-146">UnhandledException</span></span>|<span data-ttu-id="a41b8-147">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="a41b8-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="a41b8-148">Выгружен</span><span class="sxs-lookup"><span data-stu-id="a41b8-148">Unloaded</span></span>|<span data-ttu-id="a41b8-149">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="a41b8-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="a41b8-150">Отменено</span><span class="sxs-lookup"><span data-stu-id="a41b8-150">Canceled</span></span>|<span data-ttu-id="a41b8-151">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="a41b8-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="a41b8-152">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="a41b8-152">Suspended</span></span>|<span data-ttu-id="a41b8-153">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="a41b8-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="a41b8-154">Завершение</span><span class="sxs-lookup"><span data-stu-id="a41b8-154">Terminated</span></span>|<span data-ttu-id="a41b8-155">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="a41b8-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="a41b8-156">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="a41b8-156">Unsuspended</span></span>|<span data-ttu-id="a41b8-157">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="a41b8-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a41b8-158">Пример</span><span class="sxs-lookup"><span data-stu-id="a41b8-158">Example</span></span>  
 <span data-ttu-id="a41b8-159">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="a41b8-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a41b8-160">См. также</span><span class="sxs-lookup"><span data-stu-id="a41b8-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a41b8-161">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a41b8-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a41b8-162">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a41b8-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
