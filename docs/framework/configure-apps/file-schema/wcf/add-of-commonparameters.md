---
title: '&lt;add&gt; для &lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 93e82aa3bd44a747d1e85986c51c21522d709bd0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170578"
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="865cc-102">&lt;add&gt; для &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="865cc-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="865cc-103">Определяет пару параметров «имя-значение», которые используются глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="865cc-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="865cc-104">Как правило, этот параметр включает строку подключения базы данных, которая может совместно использоваться долговременными службами.</span><span class="sxs-lookup"><span data-stu-id="865cc-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="865cc-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="865cc-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="865cc-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="865cc-106">\<behaviors></span></span>  
<span data-ttu-id="865cc-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="865cc-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="865cc-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="865cc-108">\<behavior></span></span>  
<span data-ttu-id="865cc-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="865cc-109">\<workflowRuntime></span></span>  
<span data-ttu-id="865cc-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="865cc-110">\<commonParameters></span></span>  
<span data-ttu-id="865cc-111">\<add></span><span class="sxs-lookup"><span data-stu-id="865cc-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="865cc-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="865cc-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="865cc-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="865cc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="865cc-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="865cc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="865cc-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="865cc-115">Attributes</span></span>  
  
|<span data-ttu-id="865cc-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="865cc-116">Attribute</span></span>|<span data-ttu-id="865cc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="865cc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="865cc-118">имя</span><span class="sxs-lookup"><span data-stu-id="865cc-118">name</span></span>|<span data-ttu-id="865cc-119">Имя параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="865cc-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="865cc-120">value</span><span class="sxs-lookup"><span data-stu-id="865cc-120">value</span></span>|<span data-ttu-id="865cc-121">Значение параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="865cc-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="865cc-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="865cc-122">Child Elements</span></span>  
 <span data-ttu-id="865cc-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="865cc-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="865cc-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="865cc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="865cc-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="865cc-125">Element</span></span>|<span data-ttu-id="865cc-126">Описание</span><span class="sxs-lookup"><span data-stu-id="865cc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="865cc-127">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="865cc-127">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="865cc-128">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="865cc-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="865cc-129">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="865cc-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="865cc-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="865cc-130">Remarks</span></span>  
 <span data-ttu-id="865cc-131">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="865cc-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="865cc-132">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="865cc-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="865cc-133">Обратите внимание, что `EnableRetries` параметра может быть задано и на глобальном уровне (как показано в *CommonParameters* раздел) или для отдельных служб, поддерживающих `EnableRetries` (как показано в *служб*раздел).</span><span class="sxs-lookup"><span data-stu-id="865cc-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="865cc-134">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объект ведущего приложения Windows Workflow Foundation, см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="865cc-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="865cc-135">Пример</span><span class="sxs-lookup"><span data-stu-id="865cc-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="865cc-136">См. также</span><span class="sxs-lookup"><span data-stu-id="865cc-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="865cc-137">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="865cc-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="865cc-138">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="865cc-138">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
