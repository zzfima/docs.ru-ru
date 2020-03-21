---
title: Как настроить сохраняемость с помощью WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 2974b6bcbb94c5b54d91025aeabe7c2d2e94c7e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185058"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Как настроить сохраняемость с помощью WorkflowServiceHost
В данном разделе описывается способ настройки функции хранилища экземпляров рабочих процессов SQL для включения сохраняемости рабочих процессов, размещенных в <xref:System.ServiceModel.Activities.WorkflowServiceHost>, с помощью файла конфигурации. Перед использованием возможности хранилища экземпляров рабочих процессов SQL необходимо создать базу данных SQL, которая используется для хранения экземпляров рабочих процессов. Для получения дополнительной информации [см.](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>Настройка хранилища экземпляров рабочих процессов SQL в конфигурации  
  
1. Свойства хранилища экземпляров рабочих процессов SQL можно настроить с помощью объекта <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> - поведения службы, позволяющего менять параметры с помощью конфигурации XML. Следующий пример конфигурации показывает, как настроить хранилище экземпляров `sqlWorkflowInstanceStore` рабочего процесса с помощью элемента <> поведения в файле конфигурации.  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     Для получения более подробной информации о том, как настроить хранилище экземпляров рабочего процесса, [см.](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md) Для получения более подробной информации `sqlWorkflowInstanceStore` об отдельных настройках для элемента <>>, [см.](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) Фабрика приложений Windows Server имеет собственное хранилище сохраняемости. Для получения дополнительной информации, см [Windows Server App Ткань Настойчивость](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).  
  
    > [!NOTE]
    > В предыдущем примере конфигурации используется упрощенная конфигурация. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a>Настройка хранилища экземпляров рабочих процессов SQL в коде  
  
1. Свойства хранилища экземпляров рабочих процессов SQL можно настроить с помощью объекта <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, определяющего поведение службы, позволяющее менять параметры с помощью кода. В следующем примере показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью элемента поведения <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> в коде.  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     Для получения более подробной информации о том, как настроить хранилище экземпляров рабочего процесса, [см.](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md) Для получения более подробной информации об отдельных настройках для элемента <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> поведения можно ознакомиться на см. [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) Фабрика приложений Windows Server имеет собственное хранилище сохраняемости. Для получения дополнительной информации, см [Windows Server App Ткань Настойчивость](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).  
  
    > [!NOTE]
    > В предыдущем примере конфигурации используется упрощенная конфигурация. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Например, как настроить настойчивость программно [см., как: Включить сохранение для рабочих процессов и служб рабочего процесса.](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)  
  
## <a name="see-also"></a>См. также раздел

- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Сохраняемость рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- [Сохраняемость Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))
