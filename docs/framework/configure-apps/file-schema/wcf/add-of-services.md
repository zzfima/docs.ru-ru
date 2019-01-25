---
title: '&lt;add&gt; для &lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: dc68357332ebe06affd18f1539a66587b6ed1b91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549998"
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="40fed-102">&lt;add&gt; для &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="40fed-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="40fed-103">Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб на основе рабочего процесса Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="40fed-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="40fed-104">Это элемент типа <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="40fed-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="40fed-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="40fed-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="40fed-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="40fed-106">\<behaviors></span></span>  
<span data-ttu-id="40fed-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="40fed-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="40fed-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="40fed-108">\<behavior></span></span>  
<span data-ttu-id="40fed-109">\<Services ></span><span class="sxs-lookup"><span data-stu-id="40fed-109">\<services></span></span>  
<span data-ttu-id="40fed-110">\<add></span><span class="sxs-lookup"><span data-stu-id="40fed-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40fed-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40fed-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40fed-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40fed-112">Attributes and Elements</span></span>  
 <span data-ttu-id="40fed-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40fed-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40fed-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40fed-114">Attributes</span></span>  
  
|<span data-ttu-id="40fed-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="40fed-115">Attribute</span></span>|<span data-ttu-id="40fed-116">Описание</span><span class="sxs-lookup"><span data-stu-id="40fed-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40fed-117">тип</span><span class="sxs-lookup"><span data-stu-id="40fed-117">type</span></span>|<span data-ttu-id="40fed-118">Строка, задающая имя типа с указанием сборки для службы, которую необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="40fed-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="40fed-119">Заданная служба должна соответствовать определенным правилам, связанным с сигнатурами их конструкторов.</span><span class="sxs-lookup"><span data-stu-id="40fed-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="40fed-120">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="40fed-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40fed-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40fed-121">Child Elements</span></span>  
 <span data-ttu-id="40fed-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="40fed-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40fed-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40fed-123">Parent Elements</span></span>  
  
|<span data-ttu-id="40fed-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="40fed-124">Element</span></span>|<span data-ttu-id="40fed-125">Описание</span><span class="sxs-lookup"><span data-stu-id="40fed-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40fed-126">\<Services ></span><span class="sxs-lookup"><span data-stu-id="40fed-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="40fed-127">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="40fed-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="40fed-128">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="40fed-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="40fed-129">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="40fed-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="40fed-130">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="40fed-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="40fed-131">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="40fed-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40fed-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="40fed-132">Remarks</span></span>  
 <span data-ttu-id="40fed-133">Служба, указанная в данном элементе, инициализируется механизмом среды выполнения рабочих процессов и добавляется в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="40fed-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="40fed-134">Поэтому заданная служба должна соответствовать определенным правилам, относящимся к сигнатурам конструкторов.</span><span class="sxs-lookup"><span data-stu-id="40fed-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="40fed-135">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="40fed-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40fed-136">Пример</span><span class="sxs-lookup"><span data-stu-id="40fed-136">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40fed-137">См. также</span><span class="sxs-lookup"><span data-stu-id="40fed-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="40fed-138">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="40fed-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
