---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398640"
---
# <a name="state"></a><span data-ttu-id="23fbe-101">\<> состояния</span><span class="sxs-lookup"><span data-stu-id="23fbe-101">\<state></span></span>
<span data-ttu-id="23fbe-102">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="23fbe-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="23fbe-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="23fbe-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="23fbe-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="23fbe-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="23fbe-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="23fbe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="23fbe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="23fbe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Воркфловинстанцекуериес >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="23fbe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="23fbe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<состояния >** ](states.md)</span><span class="sxs-lookup"><span data-stu-id="23fbe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)</span></span>\
<span data-ttu-id="23fbe-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> состояния**</span><span class="sxs-lookup"><span data-stu-id="23fbe-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23fbe-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23fbe-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23fbe-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="23fbe-114">Attributes and Elements</span></span>  
 <span data-ttu-id="23fbe-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="23fbe-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23fbe-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="23fbe-116">Attributes</span></span>  
  
|<span data-ttu-id="23fbe-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="23fbe-117">Attribute</span></span>|<span data-ttu-id="23fbe-118">Описание</span><span class="sxs-lookup"><span data-stu-id="23fbe-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23fbe-119">имя</span><span class="sxs-lookup"><span data-stu-id="23fbe-119">name</span></span>|<span data-ttu-id="23fbe-120">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="23fbe-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23fbe-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="23fbe-121">Child Elements</span></span>  
 <span data-ttu-id="23fbe-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="23fbe-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23fbe-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="23fbe-123">Parent Elements</span></span>  
  
|<span data-ttu-id="23fbe-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="23fbe-124">Element</span></span>|<span data-ttu-id="23fbe-125">Описание</span><span class="sxs-lookup"><span data-stu-id="23fbe-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23fbe-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="23fbe-126">\<states></span></span>](states.md)|<span data-ttu-id="23fbe-127">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="23fbe-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23fbe-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="23fbe-128">Remarks</span></span>  
 <span data-ttu-id="23fbe-129">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="23fbe-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="23fbe-130">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="23fbe-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="23fbe-131">Область</span><span class="sxs-lookup"><span data-stu-id="23fbe-131">State</span></span>|<span data-ttu-id="23fbe-132">Описание</span><span class="sxs-lookup"><span data-stu-id="23fbe-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="23fbe-133">Прерывание</span><span class="sxs-lookup"><span data-stu-id="23fbe-133">Aborted</span></span>|<span data-ttu-id="23fbe-134">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="23fbe-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="23fbe-135">Завершено</span><span class="sxs-lookup"><span data-stu-id="23fbe-135">Completed</span></span>|<span data-ttu-id="23fbe-136">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="23fbe-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="23fbe-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="23fbe-137">Deleted</span></span>|<span data-ttu-id="23fbe-138">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="23fbe-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="23fbe-139">Бездействие</span><span class="sxs-lookup"><span data-stu-id="23fbe-139">Idle</span></span>|<span data-ttu-id="23fbe-140">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="23fbe-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="23fbe-141">Сохранение</span><span class="sxs-lookup"><span data-stu-id="23fbe-141">Persisted</span></span>|<span data-ttu-id="23fbe-142">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="23fbe-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="23fbe-143">Возобновление</span><span class="sxs-lookup"><span data-stu-id="23fbe-143">Resumed</span></span>|<span data-ttu-id="23fbe-144">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="23fbe-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="23fbe-145">Запуск</span><span class="sxs-lookup"><span data-stu-id="23fbe-145">Started</span></span>|<span data-ttu-id="23fbe-146">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="23fbe-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="23fbe-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="23fbe-147">UnhandledException</span></span>|<span data-ttu-id="23fbe-148">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="23fbe-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="23fbe-149">Выгружен</span><span class="sxs-lookup"><span data-stu-id="23fbe-149">Unloaded</span></span>|<span data-ttu-id="23fbe-150">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="23fbe-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="23fbe-151">Отменено</span><span class="sxs-lookup"><span data-stu-id="23fbe-151">Canceled</span></span>|<span data-ttu-id="23fbe-152">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="23fbe-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="23fbe-153">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="23fbe-153">Suspended</span></span>|<span data-ttu-id="23fbe-154">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="23fbe-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="23fbe-155">Завершение</span><span class="sxs-lookup"><span data-stu-id="23fbe-155">Terminated</span></span>|<span data-ttu-id="23fbe-156">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="23fbe-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="23fbe-157">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="23fbe-157">Unsuspended</span></span>|<span data-ttu-id="23fbe-158">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="23fbe-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23fbe-159">Пример</span><span class="sxs-lookup"><span data-stu-id="23fbe-159">Example</span></span>  
 <span data-ttu-id="23fbe-160">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="23fbe-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="23fbe-161">См. также</span><span class="sxs-lookup"><span data-stu-id="23fbe-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="23fbe-162">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="23fbe-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="23fbe-163">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="23fbe-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
