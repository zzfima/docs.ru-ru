---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1d8ddaf5d69d87ff6112b5cbb285f0ccfda724e2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397536"
---
# <a name="workflowidle"></a><span data-ttu-id="55ad6-101">\<Воркфловидле ></span><span class="sxs-lookup"><span data-stu-id="55ad6-101">\<workflowIdle></span></span>
<span data-ttu-id="55ad6-102">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="55ad6-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="55ad6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55ad6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55ad6-104">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="55ad6-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="55ad6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="55ad6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="55ad6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="55ad6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="55ad6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="55ad6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="55ad6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Воркфловидле >**</span><span class="sxs-lookup"><span data-stu-id="55ad6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ad6-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55ad6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55ad6-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="55ad6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="55ad6-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="55ad6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55ad6-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="55ad6-112">Attributes</span></span>  
  
|<span data-ttu-id="55ad6-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="55ad6-113">Attribute</span></span>|<span data-ttu-id="55ad6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="55ad6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55ad6-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="55ad6-115">timeToPersist</span></span>|<span data-ttu-id="55ad6-116">Значение TimeSpan, указывающее продолжительность между временем бездействия рабочего процесса и его сохранением.</span><span class="sxs-lookup"><span data-stu-id="55ad6-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="55ad6-117">Значение по умолчанию — TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="55ad6-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="55ad6-118">Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="55ad6-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="55ad6-119">Этот атрибут полезен, если необходимо, чтобы экземпляр рабочего процесса был более агрессивным, а экземпляр по-прежнему сохранялся в памяти в течение как можно большего времени.</span><span class="sxs-lookup"><span data-stu-id="55ad6-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="55ad6-120">Этот атрибут допустим только в том случае, если его значение меньше, чем атрибут **тиметаунлоад** .</span><span class="sxs-lookup"><span data-stu-id="55ad6-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="55ad6-121">Если значение больше, оно не учитывается.</span><span class="sxs-lookup"><span data-stu-id="55ad6-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="55ad6-122">Если этот атрибут истекает до значения, заданного атрибутом **тиметаунлоад** , сохраняемость должна завершиться до выгрузки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="55ad6-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="55ad6-123">Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="55ad6-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="55ad6-124">Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="55ad6-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="55ad6-125">В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="55ad6-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="55ad6-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="55ad6-126">timeToUnload</span></span>|<span data-ttu-id="55ad6-127">Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки.</span><span class="sxs-lookup"><span data-stu-id="55ad6-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="55ad6-128">Значение по умолчанию - 1 минута.</span><span class="sxs-lookup"><span data-stu-id="55ad6-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="55ad6-129">При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.</span><span class="sxs-lookup"><span data-stu-id="55ad6-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="55ad6-130">Если этот атрибут имеет значение 0, экземпляр рабочего процесса сохраняется и выгружается сразу же после того, как рабочий процесс переходит в состояние бездействия.</span><span class="sxs-lookup"><span data-stu-id="55ad6-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="55ad6-131">Установка для этого атрибута значения TimeSpan. MaxValue фактически отключает операцию выгрузки.</span><span class="sxs-lookup"><span data-stu-id="55ad6-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="55ad6-132">Простаивающие экземпляры рабочего процесса не выгружаются.</span><span class="sxs-lookup"><span data-stu-id="55ad6-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55ad6-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="55ad6-133">Child Elements</span></span>  
 <span data-ttu-id="55ad6-134">Нет.</span><span class="sxs-lookup"><span data-stu-id="55ad6-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55ad6-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="55ad6-135">Parent Elements</span></span>  
  
|<span data-ttu-id="55ad6-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="55ad6-136">Element</span></span>|<span data-ttu-id="55ad6-137">Описание</span><span class="sxs-lookup"><span data-stu-id="55ad6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55ad6-138">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="55ad6-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="55ad6-139">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="55ad6-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55ad6-140">См. также</span><span class="sxs-lookup"><span data-stu-id="55ad6-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
