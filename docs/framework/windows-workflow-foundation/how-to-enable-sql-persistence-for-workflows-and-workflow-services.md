---
title: "Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов
В данном разделе описано, как настроить функцию хранилища экземпляров рабочих процессов SQL для включения сохраняемости рабочих процессов и служб рабочих процессов программно и с помощью файла конфигурации.  
  
 Windows Server App Fabric упрощает процесс настройки сохраняемости.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Конфигурация фабрики приложения](http://go.microsoft.com/fwlink/?LinkId=201204)  
  
 Перед использованием функции хранилища экземпляров рабочих процессов SQL необходимо создать базу данных, которая используется функцией для сохранения экземпляров рабочих процессов.Программа установки [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] копирует файлы скрипта SQL, связанные с функцией хранилища экземпляров рабочих процессов SQL, в папку %WINDIR%\\Microsoft.NET\\Framework\\v4.xxx\\SQL\\EN.Выполните эти файлы скрипта в базе данных SQL Server 2005 или SQL Server 2008, которая должна использоваться в хранилище экземпляров рабочих процессов SQL для сохранения экземпляров рабочих процессов.Сначала запустите файл SqlWorkflowInstanceStoreSchema.sql, а затем файл SqlWorkflowInstanceStoreLogic.sql.  
  
> [!NOTE]
>  Чтобы очистить базу данных сохраняемости для получения вновь подготовленной базы данных, примените скрипты в каталоге %WINDIR%\\Microsoft.NET\\Framework\\v4.xxx\\SQL\\EN в следующем порядке.  
>   
>  1.  SqlWorkflowInstanceStoreSchema.sql  
> 2.  SqlWorkflowInstanceStoreLogic.sql  
  
> [!IMPORTANT]
>  Если база данных сохраняемости не создана, то при попытке узла сохранить рабочие процессы хранилище экземпляров рабочих процессов SQL вырабатывает исключение, подобное следующему.  
>   
>  System.Data.SqlClient.SqlException: не удается найти хранимую процедуру System.Activities.DurableInstancing.CreateLockOwner  
  
 В следующих разделах описывается включение сохраняемости для рабочих процессов и служб рабочих процессов с использованием хранилища экземпляров рабочих процессов SQL.[!INCLUDE[crabout](../../../includes/crabout-md.md)] свойствах хранилища экземпляров рабочего процесса SQL см. в разделе [Свойства хранилища экземпляров рабочего процесса SQL](../../../docs/framework/windows-workflow-foundation//properties-of-sql-workflow-instance-store.md).  
  
## Включение сохраняемости для резидентных рабочих процессов, которые используют WorkflowApplication  
 Можно включить сохраняемость для резидентных рабочих процессов, которые программно используют <xref:System.Activities.WorkflowApplication> с помощью объектной модели <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.Шаги, необходимые для выполнения этой задачи, содержатся в следующей процедуре.  
  
#### Включение сохраняемости для резидентных рабочих процессов  
  
1.  Добавьте ссылку на «System.Activites.DurableInstancing.dll».  
  
2.  Добавьте следующий оператор в начало исходного файла после существующих инструкций using.  
  
    ```csharp  
    using System.Activities.DurableInstancing;  
    ```  
  
3.  Создайте объект <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> и назначьте его свойству <xref:System.Activities.WorkflowApplication.InstanceStore%2A> приложения <xref:System.Activities.WorkflowApplication>, как показано в следующем примере кода.  
  
    ```csharp  
  
    SqlWorkflowInstanceStore store =   
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");  
  
    WorkflowApplication wfApp =  
        new WorkflowApplication(new Workflow1());  
  
    wfApp.InstanceStore = store;  
  
    ```  
  
    > [!NOTE]
    >  В строке подключения могут указываться различные имена серверов в зависимости от выпуска SQL Server.  
  
4.  Вызовите метод <xref:System.Activities.WorkflowApplication.Persist%2A> объекта <xref:System.Activities.WorkflowApplication>, чтобы сохранить рабочий процесс, или метод <xref:System.Activities.WorkflowApplication.Unload%2A>, чтобы сохранить и выгрузить рабочий процесс.Можно также обрабатывать событие <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>, вызванное объектом <xref:System.Activities.WorkflowApplication>, и возвращать соответствующий элемент \(<xref:System.Activities.PersistableIdleAction> или <xref:System.Activities.PersistableIdleAction>\) действия <xref:System.Activities.PersistableIdleAction>.  
  
    ```csharp  
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
    {  
        return PersistableIdleAction.Persist;  
    };  
    ```  
  
> [!NOTE]
>  Образец [Сохранение приложения рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/persisting-a-workflow-application.md) в разделе [Сохраняемость](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) иллюстрирует включение сохраняемости для рабочих процессов с помощью объекта <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, а пошаговые инструкции приведены в разделе [Как создать и запустить длительно выполняющийся рабочий процесс](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md) документа [Учебник по началу работы](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md).  
  
## Включение сохраняемости для резидентных служб рабочих процессов, которые используют WorkflowServiceHost  
 Можно включить сохраняемость для резидентных служб рабочих процессов, которые программно используют <xref:System.ServiceModel.WorkflowServiceHost> с помощью класса <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> или класса <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.  
  
### Использование класса SqlWorkflowInstanceStoreBehavior  
 В следующем списке перечислены этапы использования класса <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> для включения сохраняемости для резидентных служб рабочих процессов.  
  
##### Включение сохраняемости с помощью SqlWorkflowInstanceStoreBehavior  
  
1.  Добавьте ссылку на System.ServiceModel.dll.  
  
2.  Добавьте следующий оператор в начало исходного файла после существующих инструкций using.  
  
    ```csharp  
    using System.ServiceModel.Activities.Description;  
    ```  
  
3.  Создайте экземпляр `WorkflowServiceHost` и добавьте конечные точки для службы рабочего процесса.  
  
    ```  
  
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));  
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");  
  
    ```  
  
4.  Создайте объект `SqlWorkflowInstanceStoreBehavior` и задайте свойства объекта поведения.  
  
    ```csharp  
  
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);  
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);  
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;  
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;  
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;  
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");  
    host.Description.Behaviors.Add(instanceStoreBehavior);  
  
    ```  
  
5.  Откройте узел службы рабочего процесса.  
  
    ```vb  
  
    host.Open();  
  
    ```  
  
> [!IMPORTANT]
>  Образец [Встроенная конфигурация](../../../docs/framework/windows-workflow-foundation/samples/built-in-configuration.md) в разделе [Сохраняемость](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) можно использовать как пример включения сохраняемости для служб рабочих процессов с помощью класса `SqlWorkflowInstanceStoreBehavior`.  
  
### Использование свойства DurableInstancingOptions  
 После применения поведения `SqlWorkflowInstanceStoreBehavior` хранилищу `DurableInstancingOptions.InstanceStore` на `WorkflowServiceHost` задается значение объекта `SqlWorkflowInstanceStore`, созданного с использованием значений конфигурации.Эти же действия можно выполнить программно, чтобы задать свойство <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> узла `WorkflowServiceHost` без использования класса `SqlWorkflowInstanceStoreBehavior`, как показано в следующем примере кода.  
  
```  
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;  
```  
  
## Включение сохраняемости для размещенных на WAS служб рабочих процессов, которые используют WorkflowServiceHost, с помощью файла конфигурации  
 Можно включить сохраняемость для резидентных или размещенных на WAS служб рабочих процессов с помощью файла конфигурации.Служба рабочих процессов, размещенная на WAS, использует WorkflowServiceHost, так же как это делают резидентные службы рабочих процессов.  
  
 `SqlWorkflowInstanceStoreBehavior` — поведение службы, которое позволяет удобно изменять свойства [Хранилище экземпляров рабочих процессов SQL](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md) с помощью конфигурации XML.Для служб рабочих процессов, размещенных на WAS, используется файл Web.config.В следующем примере конфигурации показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью элемента поведения `sqlWorkflowInstanceStore` в файле конфигурации.  
  
```  
  
<serviceBehaviors>  
    <behavior name="">  
        <sqlWorkflowInstanceStore   
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                    instanceEncodingOption="GZip | None"  
                    instanceCompletionAction="DeleteAll | DeleteNothing"  
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"  
                    hostLockRenewalPeriod="00:00:30"   
                    runnableInstancesDetectionPeriod="00:00:05">  
  
        <sqlWorkflowInstanceStore/>  
    </behavior>  
</serviceBehaviors>  
  
```  
  
 Если не заданы значения свойства `connectionString` или `connectionStringName`, хранилище экземпляров рабочих процессов SQL использует строку подключения по умолчанию `DefaultSqlWorkflowInstanceStoreConnectionString`.  
  
 После применения поведения `SqlWorkflowInstanceStoreBehavior` хранилищу `DurableInstancingOptions.InstanceStore` на `WorkflowServiceHost` задается значение объекта `SqlWorkflowInstanceStore`, созданного с использованием значений конфигурации.Эти же действия можно выполнить программно для использования `SqlWorkflowInstanceStore` с `WorkflowServiceHost` \(без использования элемента поведения службы\).  
  
```  
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;  
```  
  
> [!IMPORTANT]
>  В файле Web.config не рекомендуется сохранять конфиденциальные сведения, такие как имена и пароли пользователей.При сохранении в файле Web.config конфиденциальных сведений необходимо обеспечить защиту доступа к файлу Web.config с помощью списков управления доступом файловой системы.Также можно обеспечить защиту значений конфигурации в файле конфигурации, как указано в разделе [Шифрование сведений о конфигурации с помощью функции защищенной конфигурации](http://go.microsoft.com/fwlink/?LinkId=178419).  
  
### Элементы Machine.config, связанные с функцией хранилища экземпляров рабочих процессов SQL  
 Установка [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] добавляет к файлу Machine.config следующие элементы, связанные с функцией хранилища экземпляров рабочих процессов SQL:  
  
-   Добавляет к файлу Machine.config следующий элемент расширения поведения, который обеспечивает возможность использования элемента поведения службы \<`sqlWorkflowInstanceStore`\> в файле конфигурации для настройки сохраняемости служб.  
  
    ```  
  
    <configuration>  
        <system.serviceModel>  
            <extensions>  
                <behaviorExtensions>  
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
                </behaviorExtensions>  
            </extensions>  
        <system.serviceModel>  
    <configuration>  
  
    ```