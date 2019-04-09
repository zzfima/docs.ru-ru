---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1dc186f5899935dab43c0d33894e659c4b19748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201121"
---
# <a name="workflowidle"></a><span data-ttu-id="fefb6-101">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="fefb6-101">\<workflowIdle></span></span>
<span data-ttu-id="fefb6-102">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fefb6-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="fefb6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fefb6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fefb6-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="fefb6-104">\<behaviors></span></span>  
<span data-ttu-id="fefb6-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fefb6-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fefb6-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="fefb6-106">\<behavior></span></span>  
<span data-ttu-id="fefb6-107">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="fefb6-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fefb6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fefb6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fefb6-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fefb6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fefb6-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fefb6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fefb6-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fefb6-111">Attributes</span></span>  
  
|<span data-ttu-id="fefb6-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fefb6-112">Attribute</span></span>|<span data-ttu-id="fefb6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fefb6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fefb6-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="fefb6-114">timeToPersist</span></span>|<span data-ttu-id="fefb6-115">Значение Timespan, указывающее продолжительность между моментом, когда рабочий процесс переходит в состояние бездействия и сохраняется.</span><span class="sxs-lookup"><span data-stu-id="fefb6-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="fefb6-116">Значение по умолчанию является TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="fefb6-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="fefb6-117">Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="fefb6-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="fefb6-118">Этот атрибут полезен в том случае, если вы хотите сохранять экземпляр рабочего процесса более интенсивно при этом оставляя экземпляр в памяти как можно дольше.</span><span class="sxs-lookup"><span data-stu-id="fefb6-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="fefb6-119">Этот атрибут действителен, только если его значение меньше, чем **timeToUnload** атрибута.</span><span class="sxs-lookup"><span data-stu-id="fefb6-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="fefb6-120">Если значение больше, оно не учитывается.</span><span class="sxs-lookup"><span data-stu-id="fefb6-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="fefb6-121">Если этот атрибут истекает до значения, указанного в **timeToUnload** атрибут, сохранение должно быть завершено до выгрузки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fefb6-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="fefb6-122">Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="fefb6-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="fefb6-123">Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="fefb6-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="fefb6-124">В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fefb6-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="fefb6-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="fefb6-125">timeToUnload</span></span>|<span data-ttu-id="fefb6-126">Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки.</span><span class="sxs-lookup"><span data-stu-id="fefb6-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="fefb6-127">Значение по умолчанию - 1 минута.</span><span class="sxs-lookup"><span data-stu-id="fefb6-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="fefb6-128">При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.</span><span class="sxs-lookup"><span data-stu-id="fefb6-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="fefb6-129">Если этот атрибут имеет значение ноль, экземпляр рабочего процесса сохраняется и выгружается сразу после становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="fefb6-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="fefb6-130">Установка для данного атрибута TimeSpan.MaxValue эффективно отключает операция выгрузки.</span><span class="sxs-lookup"><span data-stu-id="fefb6-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="fefb6-131">Простаивающие экземпляры рабочего процесса не выгружаются.</span><span class="sxs-lookup"><span data-stu-id="fefb6-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fefb6-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fefb6-132">Child Elements</span></span>  
 <span data-ttu-id="fefb6-133">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fefb6-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fefb6-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fefb6-134">Parent Elements</span></span>  
  
|<span data-ttu-id="fefb6-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="fefb6-135">Element</span></span>|<span data-ttu-id="fefb6-136">Описание</span><span class="sxs-lookup"><span data-stu-id="fefb6-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fefb6-137">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fefb6-137">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fefb6-138">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="fefb6-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fefb6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="fefb6-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
