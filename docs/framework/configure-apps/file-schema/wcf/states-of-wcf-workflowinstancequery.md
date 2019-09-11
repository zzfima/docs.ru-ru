---
title: <states>WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855037"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="f164c-102">\<состояния > WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f164c-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="f164c-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f164c-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="f164c-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="f164c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f164c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f164c-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f164c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f164c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="f164c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f164c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="f164c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="f164c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Воркфловинстанцекуериес >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="f164c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f164c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="f164c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<состояния >**</span><span class="sxs-lookup"><span data-stu-id="f164c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f164c-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f164c-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f164c-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="f164c-115">Attributes and elements</span></span>

<span data-ttu-id="f164c-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f164c-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f164c-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f164c-117">Attributes</span></span>  

<span data-ttu-id="f164c-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="f164c-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f164c-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f164c-119">Child elements</span></span>
  
|<span data-ttu-id="f164c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f164c-120">Element</span></span>|<span data-ttu-id="f164c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f164c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f164c-122">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="f164c-122">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="f164c-123">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f164c-123">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f164c-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f164c-124">Parent elements</span></span>  
  
|<span data-ttu-id="f164c-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f164c-125">Element</span></span>|<span data-ttu-id="f164c-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f164c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f164c-127">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f164c-127">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="f164c-128">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="f164c-128">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f164c-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="f164c-129">Remarks</span></span>

<span data-ttu-id="f164c-130">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="f164c-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="f164c-131">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f164c-131">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="f164c-132">Область</span><span class="sxs-lookup"><span data-stu-id="f164c-132">State</span></span>|<span data-ttu-id="f164c-133">Описание</span><span class="sxs-lookup"><span data-stu-id="f164c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f164c-134">Прерывание</span><span class="sxs-lookup"><span data-stu-id="f164c-134">Aborted</span></span>|<span data-ttu-id="f164c-135">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="f164c-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="f164c-136">Завершено</span><span class="sxs-lookup"><span data-stu-id="f164c-136">Completed</span></span>|<span data-ttu-id="f164c-137">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="f164c-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="f164c-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="f164c-138">Deleted</span></span>|<span data-ttu-id="f164c-139">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="f164c-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="f164c-140">Бездействие</span><span class="sxs-lookup"><span data-stu-id="f164c-140">Idle</span></span>|<span data-ttu-id="f164c-141">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="f164c-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="f164c-142">Сохранение</span><span class="sxs-lookup"><span data-stu-id="f164c-142">Persisted</span></span>|<span data-ttu-id="f164c-143">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="f164c-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="f164c-144">Возобновление</span><span class="sxs-lookup"><span data-stu-id="f164c-144">Resumed</span></span>|<span data-ttu-id="f164c-145">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="f164c-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="f164c-146">Запуск</span><span class="sxs-lookup"><span data-stu-id="f164c-146">Started</span></span>|<span data-ttu-id="f164c-147">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="f164c-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="f164c-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="f164c-148">UnhandledException</span></span>|<span data-ttu-id="f164c-149">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="f164c-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="f164c-150">Выгружен</span><span class="sxs-lookup"><span data-stu-id="f164c-150">Unloaded</span></span>|<span data-ttu-id="f164c-151">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="f164c-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="f164c-152">Отменено</span><span class="sxs-lookup"><span data-stu-id="f164c-152">Canceled</span></span>|<span data-ttu-id="f164c-153">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="f164c-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="f164c-154">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="f164c-154">Suspended</span></span>|<span data-ttu-id="f164c-155">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="f164c-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="f164c-156">Завершение</span><span class="sxs-lookup"><span data-stu-id="f164c-156">Terminated</span></span>|<span data-ttu-id="f164c-157">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="f164c-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="f164c-158">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="f164c-158">Unsuspended</span></span>|<span data-ttu-id="f164c-159">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="f164c-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f164c-160">Пример</span><span class="sxs-lookup"><span data-stu-id="f164c-160">Example</span></span>

<span data-ttu-id="f164c-161">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="f164c-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="f164c-162">См. также</span><span class="sxs-lookup"><span data-stu-id="f164c-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f164c-163">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f164c-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f164c-164">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f164c-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
