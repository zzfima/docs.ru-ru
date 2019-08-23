---
title: <add> из <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 38dec132626b97accacea1b7007d914edcab0abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926650"
---
# <a name="add-of-services"></a><span data-ttu-id="09cd7-102">\<Добавление > \<служб ></span><span class="sxs-lookup"><span data-stu-id="09cd7-102">\<add> of \<services></span></span>
<span data-ttu-id="09cd7-103">Задает параметры экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="09cd7-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="09cd7-104">Это элемент типа <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="09cd7-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="09cd7-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="09cd7-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="09cd7-106">\<behaviors></span></span>  
<span data-ttu-id="09cd7-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="09cd7-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="09cd7-108">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="09cd7-108">\<behavior></span></span>  
<span data-ttu-id="09cd7-109">\<службы ></span><span class="sxs-lookup"><span data-stu-id="09cd7-109">\<services></span></span>  
<span data-ttu-id="09cd7-110">\<add></span><span class="sxs-lookup"><span data-stu-id="09cd7-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09cd7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09cd7-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09cd7-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09cd7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="09cd7-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09cd7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09cd7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09cd7-114">Attributes</span></span>  
  
|<span data-ttu-id="09cd7-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="09cd7-115">Attribute</span></span>|<span data-ttu-id="09cd7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="09cd7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09cd7-117">type</span><span class="sxs-lookup"><span data-stu-id="09cd7-117">type</span></span>|<span data-ttu-id="09cd7-118">Строка, задающая имя типа с указанием сборки для службы, которую необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="09cd7-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="09cd7-119">Заданная служба должна соответствовать определенным правилам, связанным с сигнатурами их конструкторов.</span><span class="sxs-lookup"><span data-stu-id="09cd7-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="09cd7-120">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09cd7-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09cd7-121">Child Elements</span></span>  
 <span data-ttu-id="09cd7-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="09cd7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09cd7-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09cd7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="09cd7-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="09cd7-124">Element</span></span>|<span data-ttu-id="09cd7-125">Описание</span><span class="sxs-lookup"><span data-stu-id="09cd7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09cd7-126">\<службы ></span><span class="sxs-lookup"><span data-stu-id="09cd7-126">\<services></span></span>](services-of-workflowruntime.md)|<span data-ttu-id="09cd7-127">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="09cd7-128">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="09cd7-129">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="09cd7-130">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="09cd7-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="09cd7-131">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09cd7-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="09cd7-132">Remarks</span></span>  
 <span data-ttu-id="09cd7-133">Служба, указанная в данном элементе, инициализируется механизмом среды выполнения рабочих процессов и добавляется в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="09cd7-134">Поэтому заданная служба должна соответствовать определенным правилам, относящимся к сигнатурам конструкторов.</span><span class="sxs-lookup"><span data-stu-id="09cd7-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="09cd7-135">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="09cd7-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09cd7-136">Пример</span><span class="sxs-lookup"><span data-stu-id="09cd7-136">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="09cd7-137">См. также</span><span class="sxs-lookup"><span data-stu-id="09cd7-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="09cd7-138">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="09cd7-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
