---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: a92a81062e92f832be78af2bfd75270390eaac3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919496"
---
# <a name="commonparameters"></a><span data-ttu-id="da95e-101">\<Общиепараметры ></span><span class="sxs-lookup"><span data-stu-id="da95e-101">\<commonParameters></span></span>
<span data-ttu-id="da95e-102">Представляет коллекцию параметров, используемых глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="da95e-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="da95e-103">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="da95e-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="da95e-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="da95e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da95e-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="da95e-105">\<behaviors></span></span>  
<span data-ttu-id="da95e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="da95e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="da95e-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="da95e-107">\<behavior></span></span>  
<span data-ttu-id="da95e-108">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="da95e-108">\<workflowRuntime></span></span>  
<span data-ttu-id="da95e-109">\<Общиепараметры ></span><span class="sxs-lookup"><span data-stu-id="da95e-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da95e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da95e-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da95e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da95e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="da95e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da95e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da95e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da95e-113">Attributes</span></span>  
 <span data-ttu-id="da95e-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="da95e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da95e-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da95e-115">Child Elements</span></span>  
  
|<span data-ttu-id="da95e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="da95e-116">Element</span></span>|<span data-ttu-id="da95e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="da95e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da95e-118">\<add></span><span class="sxs-lookup"><span data-stu-id="da95e-118">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="da95e-119">Добавляет в коллекцию пару общих параметров вида «имя-значение», используемых службами.</span><span class="sxs-lookup"><span data-stu-id="da95e-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da95e-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da95e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="da95e-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="da95e-121">Element</span></span>|<span data-ttu-id="da95e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="da95e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da95e-123">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="da95e-123">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="da95e-124">Задает параметры экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="da95e-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da95e-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="da95e-125">Remarks</span></span>  
 <span data-ttu-id="da95e-126">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="da95e-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da95e-127">Служба отслеживания SQL не использует постоянно значение `ConnectionString`, если оно задано в разделе `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="da95e-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="da95e-128">В некоторых операциях, например при извлечении свойства `StateMachineWorkflowInstance.StateHistory`, может произойти ошибка.</span><span class="sxs-lookup"><span data-stu-id="da95e-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="da95e-129">Чтобы обойти эту проблему, задайте атрибут `ConnectionString` в разделе конфигурации для поставщика отслеживания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="da95e-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="da95e-130">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="da95e-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="da95e-131">Обратите внимание `EnableRetries` , что параметр можно задать либо на глобальном уровне (как показано в разделе *общиепараметры* ), либо в отдельных службах `EnableRetries` , которые поддерживают (как показано в разделе *службы* ).</span><span class="sxs-lookup"><span data-stu-id="da95e-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="da95e-132">В следующем примере кода показано, как изменять общие параметры программным образом.</span><span class="sxs-lookup"><span data-stu-id="da95e-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="da95e-133">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта Windows Workflow Foundation ведущего приложения см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="da95e-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da95e-134">Пример</span><span class="sxs-lookup"><span data-stu-id="da95e-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="da95e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="da95e-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="da95e-136">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="da95e-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="da95e-137">\<add></span><span class="sxs-lookup"><span data-stu-id="da95e-137">\<add></span></span>](add-of-commonparameters.md)
