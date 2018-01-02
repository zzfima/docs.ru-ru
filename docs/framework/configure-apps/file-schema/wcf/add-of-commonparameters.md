---
title: "&lt;add&gt; для &lt;commonParameters&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb11f83ed2b7d3d371d7dc5475f4ce3672bb8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="9e1b6-102">&lt;add&gt; для &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="9e1b6-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="9e1b6-103">Определяет пару параметров «имя-значение», которые используются глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="9e1b6-104">Как правило, этот параметр включает строку подключения базы данных, которая может совместно использоваться долговременными службами.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="9e1b6-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9e1b6-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-106">\<behaviors></span></span>  
<span data-ttu-id="9e1b6-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="9e1b6-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-108">\<behavior></span></span>  
<span data-ttu-id="9e1b6-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-109">\<workflowRuntime></span></span>  
<span data-ttu-id="9e1b6-110">\<Общие параметры ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-110">\<commonParameters></span></span>  
<span data-ttu-id="9e1b6-111">\<add></span><span class="sxs-lookup"><span data-stu-id="9e1b6-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e1b6-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e1b6-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e1b6-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e1b6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9e1b6-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e1b6-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e1b6-115">Attributes</span></span>  
  
|<span data-ttu-id="9e1b6-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9e1b6-116">Attribute</span></span>|<span data-ttu-id="9e1b6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9e1b6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e1b6-118">имя</span><span class="sxs-lookup"><span data-stu-id="9e1b6-118">name</span></span>|<span data-ttu-id="9e1b6-119">Имя параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="9e1b6-120">value</span><span class="sxs-lookup"><span data-stu-id="9e1b6-120">value</span></span>|<span data-ttu-id="9e1b6-121">Значение параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e1b6-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e1b6-122">Child Elements</span></span>  
 <span data-ttu-id="9e1b6-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e1b6-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e1b6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9e1b6-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e1b6-125">Element</span></span>|<span data-ttu-id="9e1b6-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="9e1b6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e1b6-127">\<Общие параметры ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-127">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="9e1b6-128">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="9e1b6-129">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e1b6-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e1b6-130">Remarks</span></span>  
 <span data-ttu-id="9e1b6-131">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="9e1b6-132">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="9e1b6-133">Обратите внимание, что `EnableRetries` параметра можно задать либо на глобальном уровне (как показано в *CommonParameters* раздел) или для отдельных служб, поддерживающих `EnableRetries` (как показано в *службы*раздел).</span><span class="sxs-lookup"><span data-stu-id="9e1b6-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="9e1b6-134">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта ведущего приложения Windows Workflow Foundation в разделе [файлы конфигурации рабочего процесса](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="9e1b6-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e1b6-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9e1b6-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e1b6-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9e1b6-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="9e1b6-137">Файлы конфигурации рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9e1b6-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="9e1b6-138">\<Общие параметры ></span><span class="sxs-lookup"><span data-stu-id="9e1b6-138">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
