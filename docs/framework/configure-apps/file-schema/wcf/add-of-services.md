---
title: "&lt;add&gt; для &lt;services&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a859676adf48fda05040633fb8909d161e9ce8e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="6137a-102">&lt;add&gt; для &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="6137a-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="6137a-103">Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], основанных на рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="6137a-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="6137a-104">Это элемент типа <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6137a-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="6137a-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6137a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6137a-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="6137a-106">\<behaviors></span></span>  
<span data-ttu-id="6137a-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6137a-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="6137a-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6137a-108">\<behavior></span></span>  
<span data-ttu-id="6137a-109">\<службы ></span><span class="sxs-lookup"><span data-stu-id="6137a-109">\<services></span></span>  
<span data-ttu-id="6137a-110">\<add></span><span class="sxs-lookup"><span data-stu-id="6137a-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6137a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6137a-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6137a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6137a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6137a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6137a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6137a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6137a-114">Attributes</span></span>  
  
|<span data-ttu-id="6137a-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6137a-115">Attribute</span></span>|<span data-ttu-id="6137a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6137a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6137a-117">тип</span><span class="sxs-lookup"><span data-stu-id="6137a-117">type</span></span>|<span data-ttu-id="6137a-118">Строка, задающая имя типа с указанием сборки для службы, которую необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="6137a-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="6137a-119">Заданная служба должна соответствовать определенным правилам, связанным с сигнатурами их конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6137a-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="6137a-120">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6137a-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6137a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6137a-121">Child Elements</span></span>  
 <span data-ttu-id="6137a-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6137a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6137a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6137a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6137a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6137a-124">Element</span></span>|<span data-ttu-id="6137a-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="6137a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6137a-126">\<службы ></span><span class="sxs-lookup"><span data-stu-id="6137a-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="6137a-127">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="6137a-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="6137a-128">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6137a-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="6137a-129">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="6137a-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="6137a-130">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6137a-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="6137a-131">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6137a-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6137a-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="6137a-132">Remarks</span></span>  
 <span data-ttu-id="6137a-133">Служба, указанная в данном элементе, инициализируется механизмом среды выполнения рабочих процессов и добавляется в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="6137a-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="6137a-134">Поэтому заданная служба должна соответствовать определенным правилам, относящимся к сигнатурам конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6137a-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="6137a-135">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6137a-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6137a-136">Пример</span><span class="sxs-lookup"><span data-stu-id="6137a-136">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6137a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="6137a-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="6137a-138">Файлы конфигурации рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6137a-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
