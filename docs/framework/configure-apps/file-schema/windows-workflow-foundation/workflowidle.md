---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947163"
---
# <a name="workflowidle"></a><span data-ttu-id="f3874-101">\<Воркфловидле ></span><span class="sxs-lookup"><span data-stu-id="f3874-101">\<workflowIdle></span></span>
<span data-ttu-id="f3874-102">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f3874-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="f3874-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f3874-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3874-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="f3874-104">\<behaviors></span></span>  
<span data-ttu-id="f3874-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f3874-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f3874-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="f3874-106">\<behavior></span></span>  
<span data-ttu-id="f3874-107">\<Воркфловидле ></span><span class="sxs-lookup"><span data-stu-id="f3874-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3874-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3874-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3874-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3874-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f3874-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3874-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3874-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3874-111">Attributes</span></span>  
  
|<span data-ttu-id="f3874-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3874-112">Attribute</span></span>|<span data-ttu-id="f3874-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f3874-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3874-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="f3874-114">timeToPersist</span></span>|<span data-ttu-id="f3874-115">Значение TimeSpan, указывающее продолжительность между временем бездействия рабочего процесса и его сохранением.</span><span class="sxs-lookup"><span data-stu-id="f3874-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="f3874-116">Значение по умолчанию — TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="f3874-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="f3874-117">Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="f3874-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="f3874-118">Этот атрибут полезен, если необходимо, чтобы экземпляр рабочего процесса был более агрессивным, а экземпляр по-прежнему сохранялся в памяти в течение как можно большего времени.</span><span class="sxs-lookup"><span data-stu-id="f3874-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="f3874-119">Этот атрибут допустим только в том случае, если его значение меньше, чем атрибут **тиметаунлоад** .</span><span class="sxs-lookup"><span data-stu-id="f3874-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="f3874-120">Если значение больше, оно не учитывается.</span><span class="sxs-lookup"><span data-stu-id="f3874-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="f3874-121">Если этот атрибут истекает до значения, заданного атрибутом **тиметаунлоад** , сохраняемость должна завершиться до выгрузки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f3874-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="f3874-122">Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="f3874-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="f3874-123">Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="f3874-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="f3874-124">В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f3874-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="f3874-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="f3874-125">timeToUnload</span></span>|<span data-ttu-id="f3874-126">Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки.</span><span class="sxs-lookup"><span data-stu-id="f3874-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="f3874-127">Значение по умолчанию - 1 минута.</span><span class="sxs-lookup"><span data-stu-id="f3874-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="f3874-128">При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.</span><span class="sxs-lookup"><span data-stu-id="f3874-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="f3874-129">Если этот атрибут имеет значение 0, экземпляр рабочего процесса сохраняется и выгружается сразу же после того, как рабочий процесс переходит в состояние бездействия.</span><span class="sxs-lookup"><span data-stu-id="f3874-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="f3874-130">Установка для этого атрибута значения TimeSpan. MaxValue фактически отключает операцию выгрузки.</span><span class="sxs-lookup"><span data-stu-id="f3874-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="f3874-131">Простаивающие экземпляры рабочего процесса не выгружаются.</span><span class="sxs-lookup"><span data-stu-id="f3874-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3874-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3874-132">Child Elements</span></span>  
 <span data-ttu-id="f3874-133">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3874-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3874-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3874-134">Parent Elements</span></span>  
  
|<span data-ttu-id="f3874-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3874-135">Element</span></span>|<span data-ttu-id="f3874-136">Описание</span><span class="sxs-lookup"><span data-stu-id="f3874-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3874-137">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="f3874-137">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="f3874-138">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="f3874-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3874-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f3874-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
