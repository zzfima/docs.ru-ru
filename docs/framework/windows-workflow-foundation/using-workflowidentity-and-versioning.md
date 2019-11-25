---
title: Использование WorkflowIdentity и управления версиями
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 66ef4fed682554d9fab2a7b0f85bb9cfaf8e8a29
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74142046"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="2ef98-102">Использование WorkflowIdentity и управления версиями</span><span class="sxs-lookup"><span data-stu-id="2ef98-102">Using WorkflowIdentity and Versioning</span></span>

<span data-ttu-id="2ef98-103"><xref:System.Activities.WorkflowIdentity> предоставляет разработчикам приложений рабочих процессов способ связать имя и <xref:System.Version> с определением рабочего процесса, а также связать эти сведения с сохраненным экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-103"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="2ef98-104">Эти идентификационные данные могут быть использованы разработчиками приложений рабочего процесса для поддержки таких сценариев, как параллельное выполнение нескольких версий определения рабочего процесса, и являются ключевым элементом для других функциональных возможностей, таких как динамическое обновление.</span><span class="sxs-lookup"><span data-stu-id="2ef98-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="2ef98-105">В этом разделе представлены общие сведения об использовании <xref:System.Activities.WorkflowIdentity> с размещением <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-105">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="2ef98-106">Сведения о параллельном выполнении определений рабочих процессов в службе рабочего процесса см. [в разделе параллельное управление версиями в WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span><span class="sxs-lookup"><span data-stu-id="2ef98-106">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="2ef98-107">Дополнительные сведения о динамическом обновлении см. в разделе [динамическое обновление](dynamic-update.md).</span><span class="sxs-lookup"><span data-stu-id="2ef98-107">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="2ef98-108">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="2ef98-108">In this topic</span></span>

- [<span data-ttu-id="2ef98-109">Использование WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="2ef98-109">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [<span data-ttu-id="2ef98-110">Параллельное выполнение с помощью WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="2ef98-110">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)

- [<span data-ttu-id="2ef98-111">Обновление .NET Framework 4 баз данных сохраняемости для поддержки управления версиями рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2ef98-111">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [<span data-ttu-id="2ef98-112">Обновление схемы базы данных</span><span class="sxs-lookup"><span data-stu-id="2ef98-112">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a><span data-ttu-id="2ef98-113">Использование WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="2ef98-113">Using WorkflowIdentity</span></span>

<span data-ttu-id="2ef98-114">Чтобы использовать <xref:System.Activities.WorkflowIdentity>, создайте экземпляр, настройте его и свяжите с экземпляром <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-114">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="2ef98-115">В экземпляре <xref:System.Activities.WorkflowIdentity> содержатся три элемента информации для идентификации.</span><span class="sxs-lookup"><span data-stu-id="2ef98-115">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="2ef98-116"><xref:System.Activities.WorkflowIdentity.Name%2A> и <xref:System.Activities.WorkflowIdentity.Version%2A> содержат имя и <xref:System.Version> и являются обязательными, а <xref:System.Activities.WorkflowIdentity.Package%2A> является необязательным и может использоваться для указания дополнительной строки с информацией (например, именем сборки или другими полезными сведениями).</span><span class="sxs-lookup"><span data-stu-id="2ef98-116"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="2ef98-117"><xref:System.Activities.WorkflowIdentity> уникален, если какое-либо из его трех свойств отличается от другого <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-117">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ef98-118">Экземпляр <xref:System.Activities.WorkflowIdentity> не должен содержать персональные данные (PII).</span><span class="sxs-lookup"><span data-stu-id="2ef98-118">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="2ef98-119">Сведения об объекте <xref:System.Activities.WorkflowIdentity>, используемом для создания экземпляра, передаются средой выполнения всем настроенным службам отслеживания на различных этапах жизненного цикла действия.</span><span class="sxs-lookup"><span data-stu-id="2ef98-119">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="2ef98-120">Отслеживание WF не имеет механизмов, позволяющих скрывать персональные данные (конфиденциальные пользовательские данные).</span><span class="sxs-lookup"><span data-stu-id="2ef98-120">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="2ef98-121">Поэтому экземпляр <xref:System.Activities.WorkflowIdentity> не должен содержать никаких персональных данных, так как они будут передаваться средой выполнения в записях отслеживания и могут отображаться любому пользователю с доступом к записям отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2ef98-121">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>

<span data-ttu-id="2ef98-122">В следующем примере создается <xref:System.Activities.WorkflowIdentity> и связывается с экземпляром рабочего процесса, созданного с использованием определения рабочего процесса `MortgageWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="2ef98-122">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="2ef98-123">При повторной загрузке и возобновлении рабочего процесса необходимо использовать <xref:System.Activities.WorkflowIdentity>, который настроен так, чтобы соответствовать <xref:System.Activities.WorkflowIdentity> сохраненного экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-123">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="2ef98-124">Если <xref:System.Activities.WorkflowIdentity> используется, когда заново загружаемый экземпляр рабочего процесса не соответствует сохраненному <xref:System.Activities.WorkflowIdentity>, выдается исключение <xref:System.Activities.VersionMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-124">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="2ef98-125">В следующем примере предпринимается попытка загрузки для экземпляра `MortgageWorkflow`, который был сохранен в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="2ef98-125">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="2ef98-126">Эта попытка загрузки выполняется с помощью <xref:System.Activities.WorkflowIdentity>, настроенного для более новой версии рабочего процесса ипотеки, не соответствующей сохраненному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="2ef98-126">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="2ef98-127">Если предыдущий код выполняется, выдается исключение <xref:System.Activities.VersionMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-127">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>

```
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a><span data-ttu-id="2ef98-128">Параллельное выполнение с помощью WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="2ef98-128">Side-by-side Execution using WorkflowIdentity</span></span>

<span data-ttu-id="2ef98-129">Метод <xref:System.Activities.WorkflowIdentity> можно использовать, чтобы облегчить параллельное выполнение нескольких версий рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-129"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="2ef98-130">Одним из типичных сценариев является изменение бизнес-требований в длительном рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="2ef98-130">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="2ef98-131">Несколько экземпляров рабочего процесса могут выполняться при развертывании обновленной версии.</span><span class="sxs-lookup"><span data-stu-id="2ef98-131">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="2ef98-132">Ведущее приложение можно настроить для использования обновленного определения рабочего процесса при запуске новых экземпляров. Обязанностью ведущего приложения является предоставление правильного определения рабочего процесса при возобновлении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2ef98-132">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="2ef98-133"><xref:System.Activities.WorkflowIdentity> можно использовать для определения и предоставления соответствующего определения рабочего процесса при возобновлении экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-133"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>

<span data-ttu-id="2ef98-134">Для получения <xref:System.Activities.WorkflowIdentity> сохраненного экземпляра рабочего процесса используется метод <xref:System.Activities.WorkflowApplication.GetInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-134">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="2ef98-135">Метод <xref:System.Activities.WorkflowApplication.GetInstance%2A> принимает <xref:System.Activities.WorkflowApplication.Id%2A> сохраненного экземпляра рабочего процесса и <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, который содержит сохраненный экземпляр и возвращает <xref:System.Activities.WorkflowApplicationInstance>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-135">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="2ef98-136">Объект <xref:System.Activities.WorkflowApplicationInstance> содержит сведения о сохраненном экземпляре рабочего процесса, включая связанный с ним <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-136">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="2ef98-137">Связанный объект <xref:System.Activities.WorkflowIdentity> может использоваться ведущим приложением, чтобы указать правильное определение рабочего процесса при загрузке и возобновлении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-137">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef98-138">Значение NULL для <xref:System.Activities.WorkflowIdentity> допустимо и может использоваться основным приложением для сопоставления экземпляров, которые были сохранены без связанного объекта <xref:System.Activities.WorkflowIdentity> в правильном определении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-138">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="2ef98-139">Этот сценарий может возникать, если приложение рабочего процесса изначально не было написано с управлением версиями рабочего процесса или когда приложение обновляется с .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2ef98-139">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from .NET Framework 4.</span></span> <span data-ttu-id="2ef98-140">Дополнительные сведения см. [в статье обновление .NET Framework 4 базы данных сохраняемости для поддержки управления версиями рабочих процессов](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span><span class="sxs-lookup"><span data-stu-id="2ef98-140">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>

<span data-ttu-id="2ef98-141">В следующем примере `Dictionary<WorkflowIdentity, Activity>` используется для связывания экземпляров <xref:System.Activities.WorkflowIdentity> с их определениями рабочего процесса, а рабочий процесс запускается с помощью определения рабочего процесса `MortgageWorkflow`, связанного с `identityV1` <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2ef98-141">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowIdentity identityV2 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v2",
    Version = new Version(2, 0, 0, 0)
};

Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="2ef98-142">В следующем примере сведения о сохраненном экземпляре рабочего процесса из предыдущего примера возвращаются путем вызова метода <xref:System.Activities.WorkflowApplication.GetInstance%2A> и сохраненные данные <xref:System.Activities.WorkflowIdentity> используются для получения соответствующего определения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ef98-142">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="2ef98-143">Эти сведения используются для настройки <xref:System.Activities.WorkflowApplication>, а затем загружается рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="2ef98-143">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="2ef98-144">Обратите внимание, что, поскольку используется перегрузка <xref:System.Activities.WorkflowApplication.Load%2A>, принимающая <xref:System.Activities.WorkflowApplicationInstance>, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, который настроен на <xref:System.Activities.WorkflowApplicationInstance>, используется <xref:System.Activities.WorkflowApplication> и, следовательно, его свойству <xref:System.Activities.WorkflowApplication.InstanceStore%2A> не нужно задавать значение.</span><span class="sxs-lookup"><span data-stu-id="2ef98-144">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef98-145">Если свойство <xref:System.Activities.WorkflowApplication.InstanceStore%2A> имеет значение, то его необходимо установить на один и тот же экземпляр <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, используемый <xref:System.Activities.WorkflowApplicationInstance>, иначе будет создаваться исключение <xref:System.ArgumentException> со следующим сообщением: `The instance is configured with a different InstanceStore than this WorkflowApplication.`</span><span class="sxs-lookup"><span data-stu-id="2ef98-145">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>

```csharp
// Get the WorkflowApplicationInstance of the desired workflow from the specified
// SqlWorkflowInstanceStore.
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);

// Use the persisted WorkflowIdentity to retrieve the correct workflow
// definition from the dictionary.
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];

WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(instance);

// Resume the workflow...
```

## <a name="UpdatingWF4PersistenceDatabases"></a><span data-ttu-id="2ef98-146">Обновление .NET Framework 4 баз данных сохраняемости для поддержки управления версиями рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2ef98-146">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>

<span data-ttu-id="2ef98-147">Для обновления баз данных сохраняемости, созданных с помощью скриптов базы данных .NET Framework 4, предоставляется скрипт базы данных SqlWorkflowInstanceStoreSchemaUpgrade. SQL.</span><span class="sxs-lookup"><span data-stu-id="2ef98-147">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the .NET Framework 4 database scripts.</span></span> <span data-ttu-id="2ef98-148">Этот сценарий обновляет базы данных для поддержки новых возможностей управления версиями, появившихся в .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="2ef98-148">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="2ef98-149">Все сохраняемые экземпляры рабочих процессов в базах данных получают значения управления версиями по умолчанию и затем могут участвовать в параллельном выполнении и динамическом обновлении.</span><span class="sxs-lookup"><span data-stu-id="2ef98-149">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>

<span data-ttu-id="2ef98-150">Если приложение рабочего процесса .NET Framework 4,5 пытается выполнить любые операции сохранения, использующие новые функции управления версиями в базе данных сохраняемости, которая не была обновлена с помощью предоставленного скрипта, создается <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> с сообщением, аналогичным приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="2ef98-150">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>

```
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a><span data-ttu-id="2ef98-151">Обновление схемы базы данных</span><span class="sxs-lookup"><span data-stu-id="2ef98-151">To upgrade the database schema</span></span>

1. <span data-ttu-id="2ef98-152">Откройте SQL Server Management Studio и подключитесь к серверу базы данных сохраняемости, например **.\SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="2ef98-152">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>

2. <span data-ttu-id="2ef98-153">Выберите **Открыть**, **файл** в меню **файл** .</span><span class="sxs-lookup"><span data-stu-id="2ef98-153">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="2ef98-154">Перейдите в следующую папку: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="2ef98-154">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span></span>

3. <span data-ttu-id="2ef98-155">Выберите **SqlWorkflowInstanceStoreSchemaUpgrade. SQL** и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="2ef98-155">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>

4. <span data-ttu-id="2ef98-156">Выберите имя базы данных сохраняемости в раскрывающемся списке **Доступные базы данных** .</span><span class="sxs-lookup"><span data-stu-id="2ef98-156">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>

5. <span data-ttu-id="2ef98-157">В меню **запрос** выберите команду **выполнить** .</span><span class="sxs-lookup"><span data-stu-id="2ef98-157">Choose **Execute** from the **Query** menu.</span></span>

<span data-ttu-id="2ef98-158">По завершении запроса обновляется схема базы данных, и при желании можно просмотреть идентификатор рабочего процесса по умолчанию, который был назначен сохраняемым экземплярам рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="2ef98-158">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="2ef98-159">Разверните базу данных сохраняемости в узле **базы данных** **обозревателя объектов**, а затем разверните узел **представления** .</span><span class="sxs-lookup"><span data-stu-id="2ef98-159">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="2ef98-160">Щелкните правой кнопкой мыши **System. activitys. DurableInstancing. Instances** и выберите **пункт выбрать первые 1000 строк**.</span><span class="sxs-lookup"><span data-stu-id="2ef98-160">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="2ef98-161">Прокрутите до конца столбцов и обратите внимание на то, что в представление добавлены шесть дополнительных столбцов: **идентитинаме**, **идентитипаккаже**, **Build**, **Major**, **minor**и **Revision**.</span><span class="sxs-lookup"><span data-stu-id="2ef98-161">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="2ef98-162">Все сохраненные рабочие процессы будут иметь значение **null** для этих полей, представляющее идентификатор рабочего процесса, равный null.</span><span class="sxs-lookup"><span data-stu-id="2ef98-162">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
