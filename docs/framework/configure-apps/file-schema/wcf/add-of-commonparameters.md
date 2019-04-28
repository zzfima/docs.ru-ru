---
title: <add> из <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 6aaba3f82966ad4496e6edaae06b5d7a8aef3863
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673658"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="0b995-102">\<Добавить > из \<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="0b995-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="0b995-103">Определяет пару параметров «имя-значение», которые используются глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="0b995-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="0b995-104">Как правило, этот параметр включает строку подключения базы данных, которая может совместно использоваться долговременными службами.</span><span class="sxs-lookup"><span data-stu-id="0b995-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="0b995-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0b995-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b995-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="0b995-106">\<behaviors></span></span>  
<span data-ttu-id="0b995-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0b995-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="0b995-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0b995-108">\<behavior></span></span>  
<span data-ttu-id="0b995-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="0b995-109">\<workflowRuntime></span></span>  
<span data-ttu-id="0b995-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="0b995-110">\<commonParameters></span></span>  
<span data-ttu-id="0b995-111">\<add></span><span class="sxs-lookup"><span data-stu-id="0b995-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b995-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b995-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b995-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b995-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0b995-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b995-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b995-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b995-115">Attributes</span></span>  
  
|<span data-ttu-id="0b995-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b995-116">Attribute</span></span>|<span data-ttu-id="0b995-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0b995-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b995-118">имя</span><span class="sxs-lookup"><span data-stu-id="0b995-118">name</span></span>|<span data-ttu-id="0b995-119">Имя параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="0b995-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="0b995-120">value</span><span class="sxs-lookup"><span data-stu-id="0b995-120">value</span></span>|<span data-ttu-id="0b995-121">Значение параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="0b995-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b995-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b995-122">Child Elements</span></span>  
 <span data-ttu-id="0b995-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b995-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b995-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b995-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0b995-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b995-125">Element</span></span>|<span data-ttu-id="0b995-126">Описание</span><span class="sxs-lookup"><span data-stu-id="0b995-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b995-127">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="0b995-127">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="0b995-128">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="0b995-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="0b995-129">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="0b995-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b995-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b995-130">Remarks</span></span>  
 <span data-ttu-id="0b995-131">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="0b995-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="0b995-132">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0b995-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="0b995-133">Обратите внимание, что `EnableRetries` параметра может быть задано и на глобальном уровне (как показано в *CommonParameters* раздел) или для отдельных служб, поддерживающих `EnableRetries` (как показано в *служб*раздел).</span><span class="sxs-lookup"><span data-stu-id="0b995-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="0b995-134">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объект ведущего приложения Windows Workflow Foundation, см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0b995-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b995-135">Пример</span><span class="sxs-lookup"><span data-stu-id="0b995-135">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="0b995-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0b995-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="0b995-137">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0b995-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="0b995-138">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="0b995-138">\<commonParameters></span></span>](commonparameters.md)
