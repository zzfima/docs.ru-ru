---
title: <add> из <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400669"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="687e6-102">\<Добавление > \<> общиепараметры</span><span class="sxs-lookup"><span data-stu-id="687e6-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="687e6-103">Определяет пару параметров «имя-значение», которые используются глобально в нескольких службах.</span><span class="sxs-lookup"><span data-stu-id="687e6-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="687e6-104">Как правило, этот параметр включает строку подключения базы данных, которая может совместно использоваться долговременными службами.</span><span class="sxs-lookup"><span data-stu-id="687e6-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="687e6-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="687e6-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="687e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="687e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="687e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="687e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="687e6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Общиепараметры >** ](commonparameters.md)</span><span class="sxs-lookup"><span data-stu-id="687e6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)</span></span>\
<span data-ttu-id="687e6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="687e6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="687e6-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="687e6-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="687e6-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="687e6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="687e6-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="687e6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="687e6-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="687e6-116">Attributes</span></span>  
  
|<span data-ttu-id="687e6-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="687e6-117">Attribute</span></span>|<span data-ttu-id="687e6-118">Описание</span><span class="sxs-lookup"><span data-stu-id="687e6-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="687e6-119">имя</span><span class="sxs-lookup"><span data-stu-id="687e6-119">name</span></span>|<span data-ttu-id="687e6-120">Имя параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="687e6-120">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="687e6-121">value</span><span class="sxs-lookup"><span data-stu-id="687e6-121">value</span></span>|<span data-ttu-id="687e6-122">Значение параметра, заданного для службы.</span><span class="sxs-lookup"><span data-stu-id="687e6-122">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="687e6-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="687e6-123">Child Elements</span></span>  
 <span data-ttu-id="687e6-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="687e6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="687e6-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="687e6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="687e6-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="687e6-126">Element</span></span>|<span data-ttu-id="687e6-127">Описание</span><span class="sxs-lookup"><span data-stu-id="687e6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="687e6-128">\<Общиепараметры ></span><span class="sxs-lookup"><span data-stu-id="687e6-128">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="687e6-129">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="687e6-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="687e6-130">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="687e6-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="687e6-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="687e6-131">Remarks</span></span>  
 <span data-ttu-id="687e6-132">Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="687e6-132">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="687e6-133">Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="687e6-133">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="687e6-134">Обратите внимание `EnableRetries` , что параметр может быть установлен на глобальном уровне (как показано в разделе *общиепараметры* ) или для отдельных служб, которые `EnableRetries` поддерживают (как показано в разделе *службы* ).</span><span class="sxs-lookup"><span data-stu-id="687e6-134">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="687e6-135">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта Windows Workflow Foundation ведущего приложения см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="687e6-135">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="687e6-136">Пример</span><span class="sxs-lookup"><span data-stu-id="687e6-136">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="687e6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="687e6-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="687e6-138">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="687e6-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="687e6-139">\<Общиепараметры ></span><span class="sxs-lookup"><span data-stu-id="687e6-139">\<commonParameters></span></span>](commonparameters.md)
