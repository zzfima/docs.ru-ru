---
title: "Размещение службы рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Размещение службы рабочего процесса
Для обработки входящих сообщений служба рабочих процессов должна быть размещена.Службы рабочих процессов используют инфраструктуру обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и поэтому также требуют размещения.Подобно службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], службы рабочего процесса могут размещаться в любом управляемом приложении, в службах IIS или в службах активации процесса Windows \(WAS\).Кроме того, службы рабочего процесса могут размещаться в фабрике приложений Windows Server.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] фабрике приложений Windows Server см. в разделах [Документация по фабрике приложений Windows Server](http://go.microsoft.com/fwlink/?LinkId=193037), [Функции размещения фабрики приложений](http://go.microsoft.com/fwlink/?LinkId=196494) и [Основы размещения в фабрике приложений](http://go.microsoft.com/fwlink/?LinkId=196495).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о различных способах размещения служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Размещение служб](../../../../docs/framework/wcf/hosting-services.md).  
  
## Размещение в управляемом приложении  
 Размещение службы рабочего процесса в управляемом приложении производится с помощью класса <xref:System.ServiceModel.Activities.WorkflowServiceHost>.Конструктор <xref:System.ServiceModel.Activities.WorkflowServiceHost> позволяет указать одноэлементный экземпляр службы рабочих процессов, определить службу рабочих процессов или действие, которое использует действия обмена сообщениями рабочих процессов.После вызова метода <xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A> служба переходит в режим ожидания передачи входящих сообщений.  
  
## Размещение в службах IIS или WAS  
 При размещении службы рабочих процессов в службах IIS или WAS создается виртуальный каталог, который служит для размещения файлов и определяет режим работы службы.При размещении службы рабочих процессов в службах IIS или WAS существует несколько возможностей.  
  
-   Разместите XAMLX\-файл, определяющий службу рабочих процессов, в виртуальном каталоге IIS\/WAS вместе с файлом Web.config, который определяет режимы работы службы, конечные точки и другие элементы конфигурации.  
  
-   Поместите XAMLX\-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS\/WAS.XAMLX\-файл определяет доступ к конечным точкам.Конечные точки указываются в элементе `WorkflowService.Endpoints`, как показано в следующем примере.  
  
    ```  
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
      <WorkflowService.Endpoints>  
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">  
          <Endpoint.Binding>  
            <BasicHttpBinding />  
          </Endpoint.Binding>  
        </Endpoint>  
      </WorkflowService.Endpoints>  
    <!-- ... -->  
    </WorkflowService>  
  
    ```  
  
    > [!NOTE]
    >  В XAMLX\-файле определить параметры поведения нельзя, поэтому для этого необходимо использовать файл Web.config.  
  
-   Поместите XAMLX\-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS\/WAS.Кроме того, в виртуальном каталоге может быть размещен SVC\-файл.В этом файле можно указать пользовательскую фабрику узла веб\-службы, применить пользовательское поведение или загрузить конфигурацию из альтернативного расположения.  
  
-   Разместите сборку в виртуальном каталоге IIS\/WAS, который содержит действие, использующее действия обмена сообщениями WCF.  
  
 XAMLX\-файл, определяющий службу рабочих процессов, должен содержать корневой элемент \<`Service`\> или корневой элемент, содержащий любой тип, производный от <xref:System.Workflow.ComponentModel.Activity>.При использовании шаблона действий [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] создается XAMLX\-файл.При использовании шаблона службы WCF Workflow Service создается XAMLX\-файл.  
  
## Размещение служб рабочего процесса в фабрике приложений Windows Server  
 Размещение службы рабочего процесса в фабрике приложений Windows Server осуществляется аналогично ее размещению на веб\-сервере IIS\/WAS.Единственное отличие состоит в том, что установлена фабрика приложений Windows Server.Фабрика приложений Windows Server добавляет в диспетчер IIS дополнительные средства, такие как командлеты powershell.Эти средства упрощают развертывание, управление и наблюдение за службами рабочего процесса и службами WCF..[!INCLUDE[crabout](../../../../includes/crabout-md.md)] фабрике приложений Windows Server см. в разделе [Фабрика приложений Windows Server](http://go.microsoft.com/fwlink/?LinkId=193037)  
  
## Ссылки на пользовательские действия  
 Ссылки на пользовательские действия необходимо добавить в раздел \<`Assemblies`\> в \<`System.Web.Compilation`\>, чтобы они могли быть загружены в домен приложения, а десериализатор XAML смог найти необходимые типы.Эти параметры могут быть указаны на уровне приложения или в корневом файле Web.config, если необходимо применять их ко всем приложениям компьютера.  
  
## Развертывание  
 Для облегчения задачи развертывания создается инструмент веб\-развертывания.Инструмент позволяет переносить приложения между IIS 6.0 и IIS 7.0, выполнять синхронизацию ферм серверов, а также упаковывать, архивировать и развертывать веб\-приложения.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Средство развертывания MS](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## См. также  
 [Внутренние особенности размещения службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)   
 [Настройка WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)