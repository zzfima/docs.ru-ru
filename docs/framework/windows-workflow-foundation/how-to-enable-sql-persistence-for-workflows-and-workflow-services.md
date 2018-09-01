---
title: Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: 55869c3c8a957de98962378cc1a93e7058e24e38
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43386738"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a>Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов

В данном разделе описано, как настроить возможность хранилища экземпляров рабочих процессов SQL для включения сохраняемости рабочих процессов и служб рабочих процессов программно и с помощью файла конфигурации.  
  
Windows Server App Fabric упрощает процесс настройки сохраняемости. Дополнительные сведения см. в разделе [конфигурация сохраняемости фабрики приложения](https://go.microsoft.com/fwlink/?LinkId=201204)  
  
Перед использованием возможности хранилища экземпляров рабочих процессов SQL необходимо создать базу данных, которая используется возможностью для сохранения экземпляров рабочих процессов. Программа установки [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] копирует файлы скрипта SQL, связанные с функцией хранилища экземпляров рабочих процессов SQL, в папку %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN. Выполните эти файлы скрипта в базе данных SQL Server 2005 или SQL Server 2008, которая должна использоваться в хранилище экземпляров рабочих процессов SQL для сохранения экземпляров рабочих процессов. Сначала запустите файл SqlWorkflowInstanceStoreSchema.sql, а затем файл SqlWorkflowInstanceStoreLogic.sql.

> [!NOTE]
> Чтобы очистить базу данных сохраняемости для получения вновь подготовленной базы данных, примените скрипты в каталоге %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN в следующем порядке.  
>
> 1. SqlWorkflowInstanceStoreSchema.sql
> 2. SqlWorkflowInstanceStoreLogic.sql

> [!IMPORTANT]
> Если база данных сохраняемости не создана, то при попытке узла сохранить рабочие процессы хранилище экземпляров рабочих процессов SQL вырабатывает исключение, подобное следующему.  
> 
> System.Data.SqlClient.SqlException: не удается найти хранимую процедуру System.Activities.DurableInstancing.CreateLockOwner  

В следующих разделах описывается включение сохраняемости для рабочих процессов и служб рабочих процессов с использованием хранилища экземпляров рабочих процессов SQL. Дополнительные сведения о свойствах, Store экземпляра рабочего процесса SQL см. в разделе [свойства экземпляра рабочего процесса SQL Store](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md).  

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a>Включение сохраняемости для резидентных рабочих процессов, которые используют WorkflowApplication

Можно включить сохраняемость для резидентных рабочих процессов, которые программно используют <xref:System.Activities.WorkflowApplication> с помощью объектной модели <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>. Шаги, необходимые для выполнения этой задачи, содержатся в следующей процедуре.  

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a>Включение сохраняемости для резидентных рабочих процессов

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
   > В строке подключения могут указываться различные имена серверов в зависимости от выпуска SQL Server.  
  
4. Вызовите метод <xref:System.Activities.WorkflowApplication.Persist%2A> объекта <xref:System.Activities.WorkflowApplication>, чтобы сохранить рабочий процесс, или метод <xref:System.Activities.WorkflowApplication.Unload%2A>, чтобы сохранить и выгрузить рабочий процесс. Можно также обрабатывать событие <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>, вызванное объектом <xref:System.Activities.WorkflowApplication>, и возвращать соответствующий элемент (<xref:System.Activities.PersistableIdleAction.Persist> или <xref:System.Activities.PersistableIdleAction.Unload>) действия <xref:System.Activities.PersistableIdleAction>.  
  
   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> См. в разделе [сохранение приложения рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/persisting-a-workflow-application.md) пример в [сохраняемости](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) пример включения сохраняемости для рабочих процессов с помощью <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>и [как: Создание и запуск длительно Запуск рабочего процесса](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) шаге [Приступая к работе](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) для пошаговой инструкцией.  

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a>Включение сохраняемости для резидентных служб рабочих процессов, которые используют WorkflowServiceHost

Можно включить сохраняемость для резидентных служб рабочих процессов, которые программно используют <xref:System.ServiceModel.WorkflowServiceHost> с помощью класса <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> или класса <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.  

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a>Использование класса SqlWorkflowInstanceStoreBehavior  

В следующем списке перечислены этапы использования класса <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> для включения сохраняемости для резидентных служб рабочих процессов.  

##### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a>Включение сохраняемости с помощью SqlWorkflowInstanceStoreBehavior

1.  Добавьте ссылку на System.ServiceModel.dll.  
  
2.  Добавьте следующий оператор в начало исходного файла после существующих инструкций using.  
  
    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3.  Создайте экземпляр `WorkflowServiceHost` и добавьте конечные точки для службы рабочего процесса.  
  
    ```csharp
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

    ```csharp
    host.Open();
    ```

> [!IMPORTANT]
> См. в разделе [встроенной конфигурации](../../../docs/framework/windows-workflow-foundation/samples/built-in-configuration.md) пример в [сохраняемости](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) пример включения сохраняемости для служб рабочих процессов с помощью `SqlWorkflowInstanceStoreBehavior` класса.  

### <a name="using-the-durableinstancingoptions-property"></a>Использование свойства DurableInstancingOptions

После применения поведения `SqlWorkflowInstanceStoreBehavior` хранилищу `DurableInstancingOptions.InstanceStore` на `WorkflowServiceHost` задается значение объекта `SqlWorkflowInstanceStore`, созданного с использованием значений конфигурации. Эти же действия можно выполнить программно, чтобы задать свойство <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> узла `WorkflowServiceHost` без использования класса `SqlWorkflowInstanceStoreBehavior`, как показано в следующем примере кода.  

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;  
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a>Включение сохраняемости для размещенных на WAS служб рабочих процессов, которые используют WorkflowServiceHost, с помощью файла конфигурации

Можно включить сохраняемость для резидентных или размещенных на WAS служб рабочих процессов с помощью файла конфигурации. Служба рабочих процессов, размещенная на WAS, использует WorkflowServiceHost, так же как это делают резидентные службы рабочих процессов.  
  
`SqlWorkflowInstanceStoreBehavior`, Поведение службы, которое позволяет удобно изменять [Store экземпляра рабочего процесса SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) свойств с помощью конфигурации XML. Для служб рабочих процессов, размещенных на WAS, используется файл Web.config. В следующем примере конфигурации показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью элемента поведения `sqlWorkflowInstanceStore` в файле конфигурации.  
  
```xml  
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
  
После применения поведения `SqlWorkflowInstanceStoreBehavior` хранилищу `DurableInstancingOptions.InstanceStore` на `WorkflowServiceHost` задается значение объекта `SqlWorkflowInstanceStore`, созданного с использованием значений конфигурации. Эти же действия можно выполнить программно для использования `SqlWorkflowInstanceStore` с `WorkflowServiceHost` (без использования элемента поведения службы).  
  
```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```
  
> [!IMPORTANT]
> В файле Web.config не рекомендуется сохранять конфиденциальные сведения, такие как имена и пароли пользователей. При сохранении в файле Web.config конфиденциальных сведений необходимо обеспечить защиту доступа к файлу Web.config с помощью списков управления доступом файловой системы. Кроме того, можно защитить значения конфигурации в файле конфигурации как уже упоминалось в [шифрование конфигурации сведения с помощью защищенной конфигурации](https://go.microsoft.com/fwlink/?LinkId=178419).

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a>Элементы Machine.config, связанные с возможностью хранилища экземпляров рабочих процессов SQL

Установка [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] добавляет к файлу Machine.config следующие элементы, связанные с функцией хранилища экземпляров рабочих процессов SQL:  

-   Добавляет к файлу Machine.config следующий элемент расширения поведения, который обеспечивает возможность использования элемента поведения службы <`sqlWorkflowInstanceStore`> в файле конфигурации для настройки сохраняемости служб.

    ```xml
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
