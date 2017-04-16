---
title: "Как настроить сохраняемость с помощью WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Как настроить сохраняемость с помощью WorkflowServiceHost
В данном разделе описывается способ настройки функции хранилища экземпляров рабочих процессов SQL для включения сохраняемости рабочих процессов, размещенных в <xref:System.ServiceHost.Activities.WorkflowServiceHost>, с помощью файла конфигурации.  Перед использованием функции хранилища экземпляров рабочих процессов SQL необходимо создать базу данных SQL, которая используется для хранения экземпляров рабочих процессов.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### Настройка хранилища экземпляров рабочих процессов SQL в конфигурации  
  
1.  Свойства хранилища экземпляров рабочих процессов SQL можно настроить с помощью объекта <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> \- поведения службы, позволяющего менять параметры с помощью конфигурации XML.  В следующем примере конфигурации показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью элемента поведения \<`sqlWorkflowInstanceStore`\> в файле конфигурации.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] настройке хранилища экземпляра рабочего процесса SQL см. в разделе [Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] отдельных параметрах элемента поведения \<`sqlWorkflowInstanceStore`\> см. в разделе [Хранилище экземпляров рабочих процессов SQL](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  Фабрика приложений Windows Server имеет собственное хранилище сохраняемости.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Постоянное хранение Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193121)  
  
    > [!NOTE]
    >  В предыдущем примере конфигурации используется упрощенная конфигурация.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### Настройка хранилища экземпляров рабочих процессов SQL в коде  
  
1.  Свойства хранилища экземпляров рабочих процессов SQL можно настроить с помощью объекта <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, определяющего поведение службы, позволяющее менять параметры с помощью кода.  В следующем примере показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью элемента поведения <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> в коде.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] настройке хранилища экземпляра рабочего процесса SQL см. в разделе [Как включить сохраняемость SQL для рабочих процессов и служб рабочих процессов](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] отдельных параметрах элемента поведения <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> см. в разделе [Хранилище экземпляров рабочих процессов SQL](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  Фабрика приложений Windows Server имеет собственное хранилище сохраняемости.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Постоянное хранение Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193121)  
  
    > [!NOTE]
    >  В предыдущем примере конфигурации используется упрощенная конфигурация.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Пример того, как настроить сохраняемость программным способом, см. в разделе [Как включить сохраняемость для рабочих процессов и служб рабочих процессов](../../../../docs/framework/windows-workflow-foundation//how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## См. также  
 [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Сохраняемость рабочего процесса](../../../../docs/framework/windows-workflow-foundation//workflow-persistence.md)   
 [Постоянное хранение Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193121)