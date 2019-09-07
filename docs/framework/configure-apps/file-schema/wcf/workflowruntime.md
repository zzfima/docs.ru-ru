---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: d12656b77fa219080382603fd04a542d2fa9064a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399086"
---
# <a name="workflowruntime"></a><span data-ttu-id="a808a-101">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="a808a-101">\<workflowRuntime></span></span>
<span data-ttu-id="a808a-102">Задает параметры экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="a808a-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
<span data-ttu-id="a808a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a808a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a808a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a808a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a808a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a808a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a808a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a808a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="a808a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a808a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="a808a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowRuntime >**</span><span class="sxs-lookup"><span data-stu-id="a808a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowRuntime>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a808a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a808a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a808a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a808a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a808a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a808a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a808a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a808a-112">Attributes</span></span>  
  
|<span data-ttu-id="a808a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a808a-113">Attribute</span></span>|<span data-ttu-id="a808a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a808a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a808a-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="a808a-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="a808a-116">Необязательное значение <xref:System.TimeSpan>, определяющее максимальный период времени, в течение которого экземпляр рабочего процесса может оставаться в памяти в неактивном состоянии до принудительной выгрузки или прекращения.</span><span class="sxs-lookup"><span data-stu-id="a808a-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="a808a-117">Если среда выполнения рабочего процесса имеет параметр `PersistenceService`, выполняющий unloadOnIdle, этот атрибут игнорируется.</span><span class="sxs-lookup"><span data-stu-id="a808a-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="a808a-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="a808a-118">enablePerformanceCounters</span></span>|<span data-ttu-id="a808a-119">Необязательное логическое значение, определяющее, включены ли счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="a808a-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="a808a-120">Счетчики производительности предоставляют статистические данные о различных рабочих процессах, но они могут вызывать снижение производительности при запуске подсистемы среды выполнения рабочего процесса и при выполнении экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a808a-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="a808a-121">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="a808a-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="a808a-122">имя</span><span class="sxs-lookup"><span data-stu-id="a808a-122">name</span></span>|<span data-ttu-id="a808a-123">Строка, содержащая имя подсистемы среды выполнения рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="a808a-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="a808a-124">Имя используется в выходных данных для различения данной среды выполнения от других сред выполнения, которые могут выполняться в системе, например в счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="a808a-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="a808a-125">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="a808a-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="a808a-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="a808a-126">validateOnCreate</span></span>|<span data-ttu-id="a808a-127">Необязательное логическое значение, указывающее, будет ли выполняться проверка определения рабочего процесса при открытии WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="a808a-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="a808a-128">Если этому атрибуту задано значение `true`, проверка рабочего процесса выполняется при каждом вызове `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="a808a-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="a808a-129">В случае обнаружения ошибок проверки возникает ошибка <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="a808a-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="a808a-130">Если это свойство имеет значение `false`, проверка определения рабочего процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a808a-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="a808a-131">Значение по умолчанию для этого свойства — `true`.</span><span class="sxs-lookup"><span data-stu-id="a808a-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a808a-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a808a-132">Child Elements</span></span>  
  
|<span data-ttu-id="a808a-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="a808a-133">Element</span></span>|<span data-ttu-id="a808a-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a808a-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a808a-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="a808a-135">commonParameters</span></span>|<span data-ttu-id="a808a-136">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="a808a-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="a808a-137">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="a808a-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="a808a-138">службы</span><span class="sxs-lookup"><span data-stu-id="a808a-138">services</span></span>|<span data-ttu-id="a808a-139">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="a808a-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="a808a-140">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="a808a-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="a808a-141">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="a808a-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="a808a-142">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="a808a-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="a808a-143">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="a808a-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a808a-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a808a-144">Parent Elements</span></span>  
  
|<span data-ttu-id="a808a-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="a808a-145">Element</span></span>|<span data-ttu-id="a808a-146">Описание</span><span class="sxs-lookup"><span data-stu-id="a808a-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a808a-147">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a808a-147">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a808a-148">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="a808a-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a808a-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="a808a-149">Remarks</span></span>  
 <span data-ttu-id="a808a-150">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта Windows Workflow Foundation ведущего приложения см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="a808a-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a808a-151">Пример</span><span class="sxs-lookup"><span data-stu-id="a808a-151">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a808a-152">См. также</span><span class="sxs-lookup"><span data-stu-id="a808a-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="a808a-153">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a808a-153">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
