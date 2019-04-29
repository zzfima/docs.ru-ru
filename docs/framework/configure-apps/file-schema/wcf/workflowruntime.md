---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: db5e1083c07d4e204eb19eaae9257ed44439132e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673151"
---
# <a name="workflowruntime"></a><span data-ttu-id="19396-101">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="19396-101">\<workflowRuntime></span></span>
<span data-ttu-id="19396-102">Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб на основе рабочего процесса Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="19396-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="19396-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="19396-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="19396-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="19396-104">\<behaviors></span></span>  
<span data-ttu-id="19396-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="19396-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="19396-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="19396-106">\<behavior></span></span>  
<span data-ttu-id="19396-107">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="19396-107">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19396-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19396-108">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19396-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="19396-109">Attributes and Elements</span></span>  
 <span data-ttu-id="19396-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="19396-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19396-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="19396-111">Attributes</span></span>  
  
|<span data-ttu-id="19396-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="19396-112">Attribute</span></span>|<span data-ttu-id="19396-113">Описание</span><span class="sxs-lookup"><span data-stu-id="19396-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19396-114">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="19396-114">cachedInstanceExpiration</span></span>|<span data-ttu-id="19396-115">Необязательное значение <xref:System.TimeSpan>, определяющее максимальный период времени, в течение которого экземпляр рабочего процесса может оставаться в памяти в неактивном состоянии до принудительной выгрузки или прекращения.</span><span class="sxs-lookup"><span data-stu-id="19396-115">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="19396-116">Если среда выполнения рабочего процесса имеет параметр `PersistenceService`, выполняющий unloadOnIdle, этот атрибут игнорируется.</span><span class="sxs-lookup"><span data-stu-id="19396-116">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="19396-117">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="19396-117">enablePerformanceCounters</span></span>|<span data-ttu-id="19396-118">Необязательное логическое значение, определяющее, включены ли счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="19396-118">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="19396-119">Счетчики производительности предоставляют статистические данные о различных рабочих процессах, но они могут вызывать снижение производительности при запуске подсистемы среды выполнения рабочего процесса и при выполнении экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="19396-119">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="19396-120">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="19396-120">The default value is `true`.</span></span>|  
|<span data-ttu-id="19396-121">имя</span><span class="sxs-lookup"><span data-stu-id="19396-121">name</span></span>|<span data-ttu-id="19396-122">Строка, содержащая имя подсистемы среды выполнения рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="19396-122">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="19396-123">Имя используется в выходных данных для различения данной среды выполнения от других сред выполнения, которые могут выполняться в системе, например в счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="19396-123">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="19396-124">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="19396-124">The default is an empty string.</span></span>|  
|<span data-ttu-id="19396-125">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="19396-125">validateOnCreate</span></span>|<span data-ttu-id="19396-126">Необязательное логическое значение, указывающее, будет ли выполняться проверка определения рабочего процесса при открытии WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="19396-126">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="19396-127">Если этому атрибуту задано значение `true`, проверка рабочего процесса выполняется при каждом вызове `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="19396-127">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="19396-128">В случае обнаружения ошибок проверки возникает ошибка <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="19396-128">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="19396-129">Если это свойство имеет значение `false`, проверка определения рабочего процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="19396-129">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="19396-130">Значение по умолчанию для этого свойства — `true`.</span><span class="sxs-lookup"><span data-stu-id="19396-130">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19396-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="19396-131">Child Elements</span></span>  
  
|<span data-ttu-id="19396-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="19396-132">Element</span></span>|<span data-ttu-id="19396-133">Описание</span><span class="sxs-lookup"><span data-stu-id="19396-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19396-134">commonParameters</span><span class="sxs-lookup"><span data-stu-id="19396-134">commonParameters</span></span>|<span data-ttu-id="19396-135">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="19396-135">A collection of common parameters used by services.</span></span> <span data-ttu-id="19396-136">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="19396-136">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="19396-137">службы</span><span class="sxs-lookup"><span data-stu-id="19396-137">services</span></span>|<span data-ttu-id="19396-138">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="19396-138">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="19396-139">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="19396-139">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="19396-140">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="19396-140">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="19396-141">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="19396-141">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="19396-142">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="19396-142">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19396-143">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="19396-143">Parent Elements</span></span>  
  
|<span data-ttu-id="19396-144">Элемент</span><span class="sxs-lookup"><span data-stu-id="19396-144">Element</span></span>|<span data-ttu-id="19396-145">Описание</span><span class="sxs-lookup"><span data-stu-id="19396-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19396-146">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="19396-146">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="19396-147">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="19396-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19396-148">Примечания</span><span class="sxs-lookup"><span data-stu-id="19396-148">Remarks</span></span>  
 <span data-ttu-id="19396-149">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объект ведущего приложения Windows Workflow Foundation, см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="19396-149">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19396-150">Пример</span><span class="sxs-lookup"><span data-stu-id="19396-150">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19396-151">См. также</span><span class="sxs-lookup"><span data-stu-id="19396-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="19396-152">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="19396-152">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
