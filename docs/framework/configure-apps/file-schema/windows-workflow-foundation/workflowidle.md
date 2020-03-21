---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151849"
---
# <a name="workflowidle"></a><span data-ttu-id="333d0-101">\<рабочий процесс></span><span class="sxs-lookup"><span data-stu-id="333d0-101">\<workflowIdle></span></span>
<span data-ttu-id="333d0-102">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="333d0-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="333d0-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="333d0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="333d0-104">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="333d0-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="333d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="333d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="333d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="333d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="333d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="333d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="333d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<рабочий процесс>**</span><span class="sxs-lookup"><span data-stu-id="333d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="333d0-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="333d0-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="333d0-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="333d0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="333d0-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="333d0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="333d0-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="333d0-112">Attributes</span></span>  
  
|<span data-ttu-id="333d0-113">attribute</span><span class="sxs-lookup"><span data-stu-id="333d0-113">Attribute</span></span>|<span data-ttu-id="333d0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="333d0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="333d0-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="333d0-115">timeToPersist</span></span>|<span data-ttu-id="333d0-116">Значение Timespan, указывающее интервал, который возникает между моментом, когда рабочий процесс становится неактивным, и его сохранением.</span><span class="sxs-lookup"><span data-stu-id="333d0-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="333d0-117">Значением по умолчанию является TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="333d0-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="333d0-118">Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="333d0-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="333d0-119">Этот атрибут может оказаться полезным в том случае, если необходимо более интенсивно сохранять экземпляр рабочего процесса, оставляя его в памяти как можно дольше.</span><span class="sxs-lookup"><span data-stu-id="333d0-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="333d0-120">Этот атрибут действителен только в том случае, если его значение меньше атрибута **timeToUnload.**</span><span class="sxs-lookup"><span data-stu-id="333d0-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="333d0-121">Если значение больше, оно не учитывается.</span><span class="sxs-lookup"><span data-stu-id="333d0-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="333d0-122">Если этот атрибут выполняется раньше значения, указанного атрибутом **timeToUnload,** сохранение должно завершиться до того, как рабочий процесс будет разгружен.</span><span class="sxs-lookup"><span data-stu-id="333d0-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="333d0-123">Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="333d0-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="333d0-124">Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="333d0-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="333d0-125">В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="333d0-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="333d0-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="333d0-126">timeToUnload</span></span>|<span data-ttu-id="333d0-127">Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки.</span><span class="sxs-lookup"><span data-stu-id="333d0-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="333d0-128">Значение по умолчанию - 1 минута.</span><span class="sxs-lookup"><span data-stu-id="333d0-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="333d0-129">При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.</span><span class="sxs-lookup"><span data-stu-id="333d0-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="333d0-130">Если этот атрибут имеет нулевое значение, экземпляр рабочего процесса сохраняется и выгружается сразу после того, как становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="333d0-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="333d0-131">Если задать этому атрибуту значение TimeSpan.MaxValue, операция выгрузки будет фактически отключена.</span><span class="sxs-lookup"><span data-stu-id="333d0-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="333d0-132">Простаивающие экземпляры рабочего процесса не выгружаются.</span><span class="sxs-lookup"><span data-stu-id="333d0-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="333d0-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="333d0-133">Child Elements</span></span>  
 <span data-ttu-id="333d0-134">Нет.</span><span class="sxs-lookup"><span data-stu-id="333d0-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="333d0-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="333d0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="333d0-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="333d0-136">Element</span></span>|<span data-ttu-id="333d0-137">Описание</span><span class="sxs-lookup"><span data-stu-id="333d0-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="333d0-138">\<поведение> \<сервисовПоведение></span><span class="sxs-lookup"><span data-stu-id="333d0-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="333d0-139">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="333d0-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="333d0-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="333d0-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
