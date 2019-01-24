---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 9d9eb45090367fb2cc18fc357c219e74d63fb667
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628106"
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="86c71-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="86c71-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="86c71-103">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="86c71-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="86c71-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="86c71-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="86c71-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="86c71-105">\<behaviors></span></span>  
<span data-ttu-id="86c71-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="86c71-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="86c71-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="86c71-107">\<behavior></span></span>  
<span data-ttu-id="86c71-108">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="86c71-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c71-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86c71-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86c71-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86c71-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86c71-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86c71-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86c71-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86c71-112">Attributes</span></span>  
  
|<span data-ttu-id="86c71-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="86c71-113">Attribute</span></span>|<span data-ttu-id="86c71-114">Описание</span><span class="sxs-lookup"><span data-stu-id="86c71-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86c71-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="86c71-115">timeToPersist</span></span>|<span data-ttu-id="86c71-116">Значение Timespan, указывающее продолжительность между моментом, когда рабочий процесс переходит в состояние бездействия и сохраняется.</span><span class="sxs-lookup"><span data-stu-id="86c71-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="86c71-117">Значение по умолчанию является TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="86c71-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="86c71-118">Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="86c71-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="86c71-119">Этот атрибут полезен в том случае, если вы хотите сохранять экземпляр рабочего процесса более интенсивно при этом оставляя экземпляр в памяти как можно дольше.</span><span class="sxs-lookup"><span data-stu-id="86c71-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="86c71-120">Этот атрибут действителен, только если его значение меньше, чем **timeToUnload** атрибута.</span><span class="sxs-lookup"><span data-stu-id="86c71-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="86c71-121">Если значение больше, оно не учитывается.</span><span class="sxs-lookup"><span data-stu-id="86c71-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="86c71-122">Если этот атрибут истекает до значения, указанного в **timeToUnload** атрибут, сохранение должно быть завершено до выгрузки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="86c71-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="86c71-123">Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="86c71-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="86c71-124">Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="86c71-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="86c71-125">В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="86c71-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="86c71-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="86c71-126">timeToUnload</span></span>|<span data-ttu-id="86c71-127">Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки.</span><span class="sxs-lookup"><span data-stu-id="86c71-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="86c71-128">Значение по умолчанию - 1 минута.</span><span class="sxs-lookup"><span data-stu-id="86c71-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="86c71-129">При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.</span><span class="sxs-lookup"><span data-stu-id="86c71-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="86c71-130">Если этот атрибут имеет значение ноль, экземпляр рабочего процесса сохраняется и выгружается сразу после становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="86c71-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="86c71-131">Установка для данного атрибута TimeSpan.MaxValue эффективно отключает операция выгрузки.</span><span class="sxs-lookup"><span data-stu-id="86c71-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="86c71-132">Простаивающие экземпляры рабочего процесса не выгружаются.</span><span class="sxs-lookup"><span data-stu-id="86c71-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86c71-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86c71-133">Child Elements</span></span>  
 <span data-ttu-id="86c71-134">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="86c71-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86c71-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86c71-135">Parent Elements</span></span>  
  
|<span data-ttu-id="86c71-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="86c71-136">Element</span></span>|<span data-ttu-id="86c71-137">Описание:</span><span class="sxs-lookup"><span data-stu-id="86c71-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86c71-138">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="86c71-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="86c71-139">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="86c71-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86c71-140">См. также</span><span class="sxs-lookup"><span data-stu-id="86c71-140">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
