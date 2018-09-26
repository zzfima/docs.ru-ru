---
title: '&lt;Общие параметры&gt;'
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 5e4c19c48709ffd81cb00e9820e6c3cdb297ec7e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086402"
---
# <a name="ltcommonparametersgt"></a><span data-ttu-id="5dd5b-102">&lt;Общие параметры&gt;</span><span class="sxs-lookup"><span data-stu-id="5dd5b-102">&lt;commonParameters&gt;</span></span>
<span data-ttu-id="5dd5b-103">Представляет коллекцию параметров, используемых глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-103">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="5dd5b-104">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-104">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="5dd5b-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5dd5b-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-106">\<behaviors></span></span>  
<span data-ttu-id="5dd5b-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="5dd5b-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-108">\<behavior></span></span>  
<span data-ttu-id="5dd5b-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-109">\<workflowRuntime></span></span>  
<span data-ttu-id="5dd5b-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-110">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd5b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5dd5b-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dd5b-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5dd5b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5dd5b-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dd5b-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5dd5b-114">Attributes</span></span>  
 <span data-ttu-id="5dd5b-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5dd5b-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5dd5b-116">Child Elements</span></span>  
  
|<span data-ttu-id="5dd5b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5dd5b-117">Element</span></span>|<span data-ttu-id="5dd5b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5dd5b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dd5b-119">\<add></span><span class="sxs-lookup"><span data-stu-id="5dd5b-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="5dd5b-120">Добавляет в коллекцию пару общих параметров вида «имя-значение», используемых службами.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dd5b-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5dd5b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5dd5b-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="5dd5b-122">Element</span></span>|<span data-ttu-id="5dd5b-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5dd5b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dd5b-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="5dd5b-124">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="5dd5b-125">Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб на основе рабочего процесса Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5dd5b-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dd5b-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5dd5b-126">Remarks</span></span>  
 <span data-ttu-id="5dd5b-127">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dd5b-128">Служба отслеживания SQL не использует постоянно значение `ConnectionString`, если оно задано в разделе `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="5dd5b-129">В некоторых операциях, например при извлечении свойства `StateMachineWorkflowInstance.StateHistory`, может произойти ошибка.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="5dd5b-130">Чтобы обойти эту проблему, задайте атрибут `ConnectionString` в разделе конфигурации для поставщика отслеживания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="5dd5b-131">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="5dd5b-132">Обратите внимание, что `EnableRetries` параметра можно задать либо на глобальном уровне (как показано в *CommonParameters* раздел) или для отдельных служб, поддерживающих `EnableRetries` (как показано в *служб*раздел).</span><span class="sxs-lookup"><span data-stu-id="5dd5b-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="5dd5b-133">В следующем примере кода показано, как изменять общие параметры программным образом.</span><span class="sxs-lookup"><span data-stu-id="5dd5b-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="5dd5b-134">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объект ведущего приложения Windows Workflow Foundation, см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="5dd5b-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dd5b-135">Пример</span><span class="sxs-lookup"><span data-stu-id="5dd5b-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dd5b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="5dd5b-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="5dd5b-137">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5dd5b-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="5dd5b-138">\<add></span><span class="sxs-lookup"><span data-stu-id="5dd5b-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
