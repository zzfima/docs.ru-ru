---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 6f187e9cdcabc358ee69d65e392bc59aa38e52ca
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398169"
---
# <a name="commonparameters"></a><span data-ttu-id="ccb5d-101">\<Общиепараметры ></span><span class="sxs-lookup"><span data-stu-id="ccb5d-101">\<commonParameters></span></span>
<span data-ttu-id="ccb5d-102">Представляет коллекцию параметров, используемых глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="ccb5d-103">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="ccb5d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccb5d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ccb5d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ccb5d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ccb5d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ccb5d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ccb5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ccb5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="ccb5d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ccb5d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="ccb5d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="ccb5d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="ccb5d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Общиепараметры >**</span><span class="sxs-lookup"><span data-stu-id="ccb5d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb5d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccb5d-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccb5d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ccb5d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ccb5d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccb5d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ccb5d-114">Attributes</span></span>  
 <span data-ttu-id="ccb5d-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ccb5d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ccb5d-116">Child Elements</span></span>  
  
|<span data-ttu-id="ccb5d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ccb5d-117">Element</span></span>|<span data-ttu-id="ccb5d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ccb5d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccb5d-119">\<add></span><span class="sxs-lookup"><span data-stu-id="ccb5d-119">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="ccb5d-120">Добавляет в коллекцию пару общих параметров вида «имя-значение», используемых службами.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccb5d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ccb5d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ccb5d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ccb5d-122">Element</span></span>|<span data-ttu-id="ccb5d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ccb5d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccb5d-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="ccb5d-124">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="ccb5d-125">Задает параметры экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccb5d-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccb5d-126">Remarks</span></span>  
 <span data-ttu-id="ccb5d-127">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccb5d-128">Служба отслеживания SQL не использует постоянно значение `ConnectionString`, если оно задано в разделе `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="ccb5d-129">В некоторых операциях, например при извлечении свойства `StateMachineWorkflowInstance.StateHistory`, может произойти ошибка.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="ccb5d-130">Чтобы обойти эту проблему, задайте атрибут `ConnectionString` в разделе конфигурации для поставщика отслеживания, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="ccb5d-131">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="ccb5d-132">Обратите внимание `EnableRetries` , что параметр можно задать либо на глобальном уровне (как показано в разделе *общиепараметры* ), либо в отдельных службах `EnableRetries` , которые поддерживают (как показано в разделе *службы* ).</span><span class="sxs-lookup"><span data-stu-id="ccb5d-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="ccb5d-133">В следующем примере кода показано, как изменять общие параметры программным образом.</span><span class="sxs-lookup"><span data-stu-id="ccb5d-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="ccb5d-134">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта Windows Workflow Foundation ведущего приложения см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="ccb5d-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccb5d-135">Пример</span><span class="sxs-lookup"><span data-stu-id="ccb5d-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="ccb5d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ccb5d-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="ccb5d-137">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ccb5d-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="ccb5d-138">\<add></span><span class="sxs-lookup"><span data-stu-id="ccb5d-138">\<add></span></span>](add-of-commonparameters.md)
