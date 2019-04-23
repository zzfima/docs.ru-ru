---
title: Использование WorkflowIdentity и управления версиями
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 5bed526a47b802c60aa679e53c84af4e14656675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327494"
---
# <a name="using-workflowidentity-and-versioning"></a>Использование WorkflowIdentity и управления версиями
<xref:System.Activities.WorkflowIdentity> предоставляет разработчикам приложений рабочих процессов способ связать имя и <xref:System.Version> с определением рабочего процесса, а также связать эти сведения с сохраненным экземпляром рабочего процесса. Эти идентификационные данные могут быть использованы разработчиками приложений рабочего процесса для поддержки таких сценариев, как параллельное выполнение нескольких версий определения рабочего процесса, и являются ключевым элементом для других функциональных возможностей, таких как динамическое обновление. В этом разделе представлены общие сведения об использовании <xref:System.Activities.WorkflowIdentity> с размещением <xref:System.Activities.WorkflowApplication>. Сведения о выполнении side-by-side определений рабочих процессов в службе рабочего процесса, см. в разделе [параллельное управление версиями в WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md). Сведения о динамическом обновлении, см. в разделе [динамического обновления](dynamic-update.md).  
  
## <a name="in-this-topic"></a>Содержание раздела  
  
-   [Использование WorkflowIdentity](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)  
  
    -   [Выполнение Side-by-side, с помощью WorkflowIdentity](using-workflowidentity-and-versioning.md#SxS)  
  
-   [Обновление .NET Framework 4 постоянного хранения и баз данных для поддержки управления версиями рабочего процесса](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)  
  
    -   [Чтобы обновить схему базы данных](using-workflowidentity-and-versioning.md#ToUpgrade)  
  
## <a name="UsingWorkflowIdentity"></a> Использование WorkflowIdentity  
 Чтобы использовать <xref:System.Activities.WorkflowIdentity>, создайте экземпляр, настройте его и свяжите с экземпляром <xref:System.Activities.WorkflowApplication>. В экземпляре <xref:System.Activities.WorkflowIdentity> содержатся три элемента информации для идентификации. <xref:System.Activities.WorkflowIdentity.Name%2A> и <xref:System.Activities.WorkflowIdentity.Version%2A> содержат имя и <xref:System.Version> и являются обязательными, а <xref:System.Activities.WorkflowIdentity.Package%2A> является необязательным и может использоваться для указания дополнительной строки с информацией (например, именем сборки или другими полезными сведениями). <xref:System.Activities.WorkflowIdentity> уникален, если какое-либо из его трех свойств отличается от другого <xref:System.Activities.WorkflowIdentity>.  
  
> [!IMPORTANT]
>  Экземпляр <xref:System.Activities.WorkflowIdentity> не должен содержать персональные данные (PII). Сведения об объекте <xref:System.Activities.WorkflowIdentity>, используемом для создания экземпляра, передаются средой выполнения всем настроенным службам отслеживания на различных этапах жизненного цикла действия. Отслеживание WF не имеет механизмов, позволяющих скрывать персональные данные (конфиденциальные пользовательские данные). Поэтому экземпляр <xref:System.Activities.WorkflowIdentity> не должен содержать никаких персональных данных, так как они будут передаваться средой выполнения в записях отслеживания и могут отображаться любому пользователю с доступом к записям отслеживания.  
  
 В следующем примере создается <xref:System.Activities.WorkflowIdentity> и связывается с экземпляром рабочего процесса, созданного с использованием определения рабочего процесса `MortgageWorkflow`.  
  
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
  
 При повторной загрузке и возобновлении рабочего процесса необходимо использовать <xref:System.Activities.WorkflowIdentity>, который настроен так, чтобы соответствовать <xref:System.Activities.WorkflowIdentity> сохраненного экземпляра рабочего процесса.  
  
```csharp  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Load the workflow.  
wfApp.Load(instanceId);  
  
// Resume the workflow...  
```  
  
 Если <xref:System.Activities.WorkflowIdentity> используется, когда заново загружаемый экземпляр рабочего процесса не соответствует сохраненному <xref:System.Activities.WorkflowIdentity>, выдается исключение <xref:System.Activities.VersionMismatchException>. В следующем примере предпринимается попытка загрузки для экземпляра `MortgageWorkflow`, который был сохранен в предыдущем примере. Эта попытка загрузки выполняется с помощью <xref:System.Activities.WorkflowIdentity>, настроенного для более новой версии рабочего процесса ипотеки, не соответствующей сохраненному экземпляру.  
  
```csharp  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Attempt to load the workflow instance.  
wfApp.Load(instanceId);  
  
// Resume the workflow...  
```  
  
 Если предыдущий код выполняется, выдается исключение <xref:System.Activities.VersionMismatchException>.  
  
 **WorkflowIdentity ("MortgageWorkflow v1. Версия = 1.0.0.0") загружаемого экземпляра не соответствует WorkflowIdentity (" MortgageWorkflow v2. Версия = 2.0.0.0") из указанное определение рабочего процесса. Экземпляр можно загрузить с помощью различные определения или обновить с помощью динамического обновления.**  
### <a name="SxS"></a> Выполнение Side-by-side, с помощью WorkflowIdentity  
 Метод <xref:System.Activities.WorkflowIdentity> можно использовать, чтобы облегчить параллельное выполнение нескольких версий рабочего процесса. Одним из типичных сценариев является изменение бизнес-требований в длительном рабочем процессе. Несколько экземпляров рабочего процесса могут выполняться при развертывании обновленной версии. Ведущее приложение можно настроить для использования обновленного определения рабочего процесса при запуске новых экземпляров. Обязанностью ведущего приложения является предоставление правильного определения рабочего процесса при возобновлении экземпляров. <xref:System.Activities.WorkflowIdentity> можно использовать для определения и предоставления соответствующего определения рабочего процесса при возобновлении экземпляров рабочего процесса.  
  
 Для получения <xref:System.Activities.WorkflowIdentity> сохраненного экземпляра рабочего процесса используется метод <xref:System.Activities.WorkflowApplication.GetInstance%2A>. Метод <xref:System.Activities.WorkflowApplication.GetInstance%2A> принимает <xref:System.Activities.WorkflowApplication.Id%2A> сохраненного экземпляра рабочего процесса и <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, который содержит сохраненный экземпляр и возвращает <xref:System.Activities.WorkflowApplicationInstance>. Объект <xref:System.Activities.WorkflowApplicationInstance> содержит сведения о сохраненном экземпляре рабочего процесса, включая связанный с ним <xref:System.Activities.WorkflowIdentity>. Связанный объект <xref:System.Activities.WorkflowIdentity> может использоваться ведущим приложением, чтобы указать правильное определение рабочего процесса при загрузке и возобновлении экземпляра рабочего процесса.  
  
> [!NOTE]
>  Значение NULL для <xref:System.Activities.WorkflowIdentity> допустимо и может использоваться основным приложением для сопоставления экземпляров, которые были сохранены без связанного объекта <xref:System.Activities.WorkflowIdentity> в правильном определении рабочего процесса. Этот сценарий может возникнуть, когда приложение рабочего процесса изначально не было написано с использованием управления версиями рабочего процесса или если приложение обновлено с версии [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Дополнительные сведения см. в разделе [обновление .NET Framework 4 баз данных постоянного хранения для поддержки управления версиями рабочего процесса](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).  
  
 В следующем примере `Dictionary<WorkflowIdentity, Activity>` позволяет связать <xref:System.Activities.WorkflowIdentity> экземпляры с их соответствующими определениями рабочих процессов и рабочий процесс запускается с помощью `MortgageWorkflow` определения рабочего процесса, связанного с `identityV1` <xref:System.Activities.WorkflowIdentity>.  
  
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
  
 В следующем примере сведения о сохраненном экземпляре рабочего процесса из предыдущего примера возвращаются путем вызова метода <xref:System.Activities.WorkflowApplication.GetInstance%2A> и сохраненные данные <xref:System.Activities.WorkflowIdentity> используются для получения соответствующего определения рабочего процесса. Эти сведения используются для настройки <xref:System.Activities.WorkflowApplication>, а затем загружается рабочий процесс. Обратите внимание, что, поскольку используется перегрузка <xref:System.Activities.WorkflowApplication.Load%2A>, принимающая <xref:System.Activities.WorkflowApplicationInstance>, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, который настроен на <xref:System.Activities.WorkflowApplicationInstance>, используется <xref:System.Activities.WorkflowApplication> и, следовательно, его свойству <xref:System.Activities.WorkflowApplication.InstanceStore%2A> не нужно задавать значение.  
  
> [!NOTE]
>  Если свойство <xref:System.Activities.WorkflowApplication.InstanceStore%2A> имеет значение, то его необходимо установить на один и тот же экземпляр <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, используемый <xref:System.Activities.WorkflowApplicationInstance>, иначе будет создаваться исключение <xref:System.ArgumentException> со следующим сообщением: `The instance is configured with a different InstanceStore than this WorkflowApplication.`  
  
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
  
## <a name="UpdatingWF4PersistenceDatabases"></a> Обновление .NET Framework 4 постоянного хранения и баз данных для поддержки управления версиями рабочего процесса  
 Предоставляется скрипт базы данных SqlWorkflowInstanceStoreSchemaUpgrade.sql для обновления баз данных сохраняемости, созданных с помощью скриптов базы данных [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Этот скрипт обновляет базы данных для поддержки новых возможностей управления версиями, представленных в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Все сохраняемые экземпляры рабочих процессов в базах данных получают значения управления версиями по умолчанию и затем могут участвовать в параллельном выполнении и динамическом обновлении.  
  
 Если приложение рабочего процесса [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] пытается выполнить любые операции сохраняемости, которые используют новые функции управления версиями в долговременной базе данных, которая не была обновлена с применением указанного скрипта, то выдается исключение <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> с сообщением, аналогичным следующему.  
  
 **Хранилище SqlWorkflowInstanceStore содержит версию базы данных "4.0.0.0». Команда InstancePersistenceCommand «System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand» не может быть выполнена для этой версии базы данных.  Обновите базу данных для "4.5.0.0».**  
### <a name="ToUpgrade"></a> Чтобы обновить схему базы данных  
  
1. Откройте SQL Server Management Studio и подключитесь к серверу долговременной базы данных, например **. \SQLEXPRESS**.  
  
2. Выберите **откройте**, **файл** из **файл** меню. Перейдите в следующую папку: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`  
  
3. Выберите **SqlWorkflowInstanceStoreSchemaUpgrade.sql** и нажмите кнопку **откройте**.  
  
4. Выберите имя базы данных сохраняемости в **доступных баз данных** раскрывающегося списка.  
  
5. Выберите **Execute** из **запроса** меню.  
  
 По завершении запроса обновляется схема базы данных, и при желании можно просмотреть идентификатор рабочего процесса по умолчанию, который был назначен сохраняемым экземплярам рабочих процессов. Разверните долговременную базу данных в **баз данных** узел **обозревателя объектов**, а затем разверните **представления** узла. Щелкните правой кнопкой мыши **System.Activities.DurableInstancing.Instances** и выберите **выделить 1000 верхних строк**. Перейдите в конец столбцов и обратите внимание, что в представление добавлены 6 дополнительных столбцов: **IdentityName**, **IdentityPackage**, **построения**, **основных**, **незначительные**, и **редакции**. Все сохраненные рабочие процессы будут иметь значение **NULL** для этих полей, представляющий удостоверение рабочего процесса значение null.
