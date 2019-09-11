---
title: <state>WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854950"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="410a7-102">\<> состояния WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="410a7-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="410a7-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="410a7-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="410a7-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="410a7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="410a7-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="410a7-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="410a7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="410a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="410a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="410a7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="410a7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="410a7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Воркфловинстанцекуериес >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="410a7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="410a7-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<состояния >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="410a7-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="410a7-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> состояния**</span><span class="sxs-lookup"><span data-stu-id="410a7-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410a7-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="410a7-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="410a7-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="410a7-116">Attributes and elements</span></span>

<span data-ttu-id="410a7-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="410a7-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="410a7-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="410a7-118">Attributes</span></span>

|<span data-ttu-id="410a7-119">Атрибут</span><span class="sxs-lookup"><span data-stu-id="410a7-119">Attribute</span></span>|<span data-ttu-id="410a7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="410a7-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="410a7-121">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="410a7-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="410a7-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="410a7-122">Child elements</span></span>

<span data-ttu-id="410a7-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="410a7-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="410a7-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="410a7-124">Parent elements</span></span>

|<span data-ttu-id="410a7-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="410a7-125">Element</span></span>|<span data-ttu-id="410a7-126">Описание</span><span class="sxs-lookup"><span data-stu-id="410a7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="410a7-127">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="410a7-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="410a7-128">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="410a7-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="410a7-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="410a7-129">Remarks</span></span>  

<span data-ttu-id="410a7-130">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="410a7-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="410a7-131">Возможные значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="410a7-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="410a7-132">Область</span><span class="sxs-lookup"><span data-stu-id="410a7-132">State</span></span>|<span data-ttu-id="410a7-133">Описание</span><span class="sxs-lookup"><span data-stu-id="410a7-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="410a7-134">Прерывание</span><span class="sxs-lookup"><span data-stu-id="410a7-134">Aborted</span></span>|<span data-ttu-id="410a7-135">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="410a7-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="410a7-136">Завершено</span><span class="sxs-lookup"><span data-stu-id="410a7-136">Completed</span></span>|<span data-ttu-id="410a7-137">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="410a7-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="410a7-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="410a7-138">Deleted</span></span>|<span data-ttu-id="410a7-139">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="410a7-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="410a7-140">Бездействие</span><span class="sxs-lookup"><span data-stu-id="410a7-140">Idle</span></span>|<span data-ttu-id="410a7-141">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="410a7-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="410a7-142">Сохранение</span><span class="sxs-lookup"><span data-stu-id="410a7-142">Persisted</span></span>|<span data-ttu-id="410a7-143">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="410a7-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="410a7-144">Возобновление</span><span class="sxs-lookup"><span data-stu-id="410a7-144">Resumed</span></span>|<span data-ttu-id="410a7-145">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="410a7-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="410a7-146">Запуск</span><span class="sxs-lookup"><span data-stu-id="410a7-146">Started</span></span>|<span data-ttu-id="410a7-147">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="410a7-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="410a7-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="410a7-148">UnhandledException</span></span>|<span data-ttu-id="410a7-149">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="410a7-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="410a7-150">Выгружен</span><span class="sxs-lookup"><span data-stu-id="410a7-150">Unloaded</span></span>|<span data-ttu-id="410a7-151">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="410a7-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="410a7-152">Отменено</span><span class="sxs-lookup"><span data-stu-id="410a7-152">Canceled</span></span>|<span data-ttu-id="410a7-153">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="410a7-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="410a7-154">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="410a7-154">Suspended</span></span>|<span data-ttu-id="410a7-155">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="410a7-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="410a7-156">Завершение</span><span class="sxs-lookup"><span data-stu-id="410a7-156">Terminated</span></span>|<span data-ttu-id="410a7-157">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="410a7-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="410a7-158">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="410a7-158">Unsuspended</span></span>|<span data-ttu-id="410a7-159">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="410a7-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="410a7-160">Пример</span><span class="sxs-lookup"><span data-stu-id="410a7-160">Example</span></span>

<span data-ttu-id="410a7-161">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="410a7-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="410a7-162">См. также</span><span class="sxs-lookup"><span data-stu-id="410a7-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="410a7-163">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="410a7-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="410a7-164">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="410a7-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
