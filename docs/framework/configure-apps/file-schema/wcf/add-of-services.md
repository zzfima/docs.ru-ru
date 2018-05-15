---
title: '&lt;add&gt; для &lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 709636f0b9667a431838b463c05cfd00f6521f6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="bcfe0-102">&lt;add&gt; для &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="bcfe0-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="bcfe0-103">Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="bcfe0-104">Это элемент типа <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="bcfe0-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bcfe0-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="bcfe0-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="bcfe0-106">\<behaviors></span></span>  
<span data-ttu-id="bcfe0-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bcfe0-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="bcfe0-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="bcfe0-108">\<behavior></span></span>  
<span data-ttu-id="bcfe0-109">\<службы ></span><span class="sxs-lookup"><span data-stu-id="bcfe0-109">\<services></span></span>  
<span data-ttu-id="bcfe0-110">\<add></span><span class="sxs-lookup"><span data-stu-id="bcfe0-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfe0-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcfe0-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcfe0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bcfe0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bcfe0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcfe0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bcfe0-114">Attributes</span></span>  
  
|<span data-ttu-id="bcfe0-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bcfe0-115">Attribute</span></span>|<span data-ttu-id="bcfe0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bcfe0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcfe0-117">тип</span><span class="sxs-lookup"><span data-stu-id="bcfe0-117">type</span></span>|<span data-ttu-id="bcfe0-118">Строка, задающая имя типа с указанием сборки для службы, которую необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="bcfe0-119">Заданная служба должна соответствовать определенным правилам, связанным с сигнатурами их конструкторов.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="bcfe0-120">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcfe0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bcfe0-121">Child Elements</span></span>  
 <span data-ttu-id="bcfe0-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcfe0-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bcfe0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bcfe0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcfe0-124">Element</span></span>|<span data-ttu-id="bcfe0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bcfe0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcfe0-126">\<службы ></span><span class="sxs-lookup"><span data-stu-id="bcfe0-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="bcfe0-127">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="bcfe0-128">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="bcfe0-129">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="bcfe0-130">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="bcfe0-131">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcfe0-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcfe0-132">Remarks</span></span>  
 <span data-ttu-id="bcfe0-133">Служба, указанная в данном элементе, инициализируется механизмом среды выполнения рабочих процессов и добавляется в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="bcfe0-134">Поэтому заданная служба должна соответствовать определенным правилам, относящимся к сигнатурам конструкторов.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="bcfe0-135">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bcfe0-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcfe0-136">Пример</span><span class="sxs-lookup"><span data-stu-id="bcfe0-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcfe0-137">См. также</span><span class="sxs-lookup"><span data-stu-id="bcfe0-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="bcfe0-138">Файлы конфигурации рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bcfe0-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
