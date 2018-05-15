---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 65bcc1ccd357fb7f331665aefbd975b11a2378cd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="a551b-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="a551b-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="a551b-103">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a551b-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="a551b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a551b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a551b-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="a551b-105">\<behaviors></span></span>  
<span data-ttu-id="a551b-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a551b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a551b-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a551b-107">\<behavior></span></span>  
<span data-ttu-id="a551b-108">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="a551b-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a551b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a551b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a551b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a551b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a551b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a551b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a551b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a551b-112">Attributes</span></span>  
  
|<span data-ttu-id="a551b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a551b-113">Attribute</span></span>|<span data-ttu-id="a551b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a551b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a551b-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="a551b-115">timeToPersist</span></span>|<span data-ttu-id="a551b-116">Значение Timespan, которое указывает время между моментом рабочий процесс переходит в состояние бездействия и сохраняется.</span><span class="sxs-lookup"><span data-stu-id="a551b-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="a551b-117">Значение по умолчанию — TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="a551b-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="a551b-118">Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="a551b-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="a551b-119">Этот атрибут полезен, если вы хотите сохранить экземпляр рабочего процесса активнее, при этом оставляя экземпляр в памяти в то же время.</span><span class="sxs-lookup"><span data-stu-id="a551b-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="a551b-120">Этот атрибут действителен, только если его значение меньше, чем **timeToUnload** атрибута.</span><span class="sxs-lookup"><span data-stu-id="a551b-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="a551b-121">Если значение больше, оно не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a551b-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="a551b-122">Если этот атрибут истекает до значения, указанного в **timeToUnload** атрибут, сохранение должно быть завершено до выгрузки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a551b-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="a551b-123">Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="a551b-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="a551b-124">Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="a551b-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="a551b-125">В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a551b-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="a551b-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="a551b-126">timeToUnload</span></span>|<span data-ttu-id="a551b-127">Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки.</span><span class="sxs-lookup"><span data-stu-id="a551b-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="a551b-128">Значение по умолчанию - 1 минута.</span><span class="sxs-lookup"><span data-stu-id="a551b-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="a551b-129">При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.</span><span class="sxs-lookup"><span data-stu-id="a551b-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="a551b-130">Если этот атрибут имеет значение ноль, экземпляр рабочего процесса сохраняется и выгружается сразу после рабочий процесс становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="a551b-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="a551b-131">Задав этому атрибуту значение TimeSpan.MaxValue фактически операция выгрузки будет отключена.</span><span class="sxs-lookup"><span data-stu-id="a551b-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="a551b-132">Простаивающие экземпляры рабочего процесса не выгружаются.</span><span class="sxs-lookup"><span data-stu-id="a551b-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a551b-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a551b-133">Child Elements</span></span>  
 <span data-ttu-id="a551b-134">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a551b-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a551b-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a551b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a551b-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="a551b-136">Element</span></span>|<span data-ttu-id="a551b-137">Описание</span><span class="sxs-lookup"><span data-stu-id="a551b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a551b-138">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a551b-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a551b-139">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="a551b-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a551b-140">См. также</span><span class="sxs-lookup"><span data-stu-id="a551b-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
