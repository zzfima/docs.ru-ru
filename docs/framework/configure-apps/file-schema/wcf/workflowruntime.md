---
title: '&lt;WorkflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 7c2bd4e2a8c1ddbdb98878d1d97c7acc41856310
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755852"
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="4c982-102">&lt;WorkflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="4c982-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="4c982-103">Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4c982-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="4c982-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4c982-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4c982-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="4c982-105">\<behaviors></span></span>  
<span data-ttu-id="4c982-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4c982-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4c982-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="4c982-107">\<behavior></span></span>  
<span data-ttu-id="4c982-108">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="4c982-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c982-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c982-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c982-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c982-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4c982-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4c982-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c982-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c982-112">Attributes</span></span>  
  
|<span data-ttu-id="4c982-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4c982-113">Attribute</span></span>|<span data-ttu-id="4c982-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4c982-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c982-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="4c982-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="4c982-116">Необязательное значение <xref:System.TimeSpan>, определяющее максимальный период времени, в течение которого экземпляр рабочего процесса может оставаться в памяти в неактивном состоянии до принудительной выгрузки или прекращения.</span><span class="sxs-lookup"><span data-stu-id="4c982-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="4c982-117">Если среда выполнения рабочего процесса имеет параметр `PersistenceService`, выполняющий unloadOnIdle, этот атрибут игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4c982-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="4c982-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="4c982-118">enablePerformanceCounters</span></span>|<span data-ttu-id="4c982-119">Необязательное логическое значение, определяющее, включены ли счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="4c982-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="4c982-120">Счетчики производительности предоставляют статистические данные о различных рабочих процессах, но они могут вызывать снижение производительности при запуске подсистемы среды выполнения рабочего процесса и при выполнении экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4c982-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="4c982-121">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="4c982-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="4c982-122">имя</span><span class="sxs-lookup"><span data-stu-id="4c982-122">name</span></span>|<span data-ttu-id="4c982-123">Строка, содержащая имя подсистемы среды выполнения рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="4c982-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="4c982-124">Имя используется в выходных данных для различения данной среды выполнения от других сред выполнения, которые могут выполняться в системе, например в счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="4c982-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="4c982-125">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="4c982-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="4c982-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="4c982-126">validateOnCreate</span></span>|<span data-ttu-id="4c982-127">Необязательное логическое значение, указывающее, будет ли выполняться проверка определения рабочего процесса при открытии WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="4c982-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="4c982-128">Если этому атрибуту задано значение `true`, проверка рабочего процесса выполняется при каждом вызове `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="4c982-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="4c982-129">В случае обнаружения ошибок проверки возникает ошибка <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="4c982-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="4c982-130">Если это свойство имеет значение `false`, проверка определения рабочего процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4c982-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="4c982-131">Значение по умолчанию для этого свойства — `true`.</span><span class="sxs-lookup"><span data-stu-id="4c982-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c982-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c982-132">Child Elements</span></span>  
  
|<span data-ttu-id="4c982-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c982-133">Element</span></span>|<span data-ttu-id="4c982-134">Описание</span><span class="sxs-lookup"><span data-stu-id="4c982-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c982-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="4c982-135">commonParameters</span></span>|<span data-ttu-id="4c982-136">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="4c982-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="4c982-137">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="4c982-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="4c982-138">службы</span><span class="sxs-lookup"><span data-stu-id="4c982-138">services</span></span>|<span data-ttu-id="4c982-139">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="4c982-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="4c982-140">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="4c982-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="4c982-141">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="4c982-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="4c982-142">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="4c982-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="4c982-143">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="4c982-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c982-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c982-144">Parent Elements</span></span>  
  
|<span data-ttu-id="4c982-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c982-145">Element</span></span>|<span data-ttu-id="4c982-146">Описание</span><span class="sxs-lookup"><span data-stu-id="4c982-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c982-147">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="4c982-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4c982-148">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="4c982-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c982-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c982-149">Remarks</span></span>  
 <span data-ttu-id="4c982-150">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта ведущего приложения Windows Workflow Foundation в разделе [файлы конфигурации рабочего процесса](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="4c982-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c982-151">Пример</span><span class="sxs-lookup"><span data-stu-id="4c982-151">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c982-152">См. также</span><span class="sxs-lookup"><span data-stu-id="4c982-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="4c982-153">Файлы конфигурации рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4c982-153">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
