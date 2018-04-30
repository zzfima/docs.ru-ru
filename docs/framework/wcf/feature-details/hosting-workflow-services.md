---
title: Размещение службы рабочего процесса
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21c4ba6a85c2da655b3d0988917165bf84ae64d1
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="hosting-workflow-services"></a>Размещение службы рабочего процесса
Для обработки входящих сообщений служба рабочих процессов должна быть размещена. Службы рабочих процессов используют инфраструктуру обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и поэтому также требуют размещения. Подобно службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], службы рабочего процесса могут размещаться в любом управляемом приложении, в службах IIS или в службах активации процесса Windows (WAS). Кроме того, службы рабочего процесса могут размещаться в фабрике приложений Windows Server. Дополнительные сведения о Windows Server App Fabric разделе [документации Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037), [функции размещения AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494), и [размещения AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495). Дополнительные сведения о различных способах узла [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служб см. в разделе [размещение служб](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="hosting-in-a-managed-application"></a>Размещение в управляемом приложении  
 Размещение службы рабочего процесса в управляемом приложении производится с помощью класса <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Конструктор <xref:System.ServiceModel.Activities.WorkflowServiceHost> позволяет указать одноэлементный экземпляр службы рабочих процессов, определить службу рабочих процессов или действие, которое использует действия обмена сообщениями рабочих процессов. Вызов <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`> приводит к служба начинает прослушивать входящие сообщения.  
  
## <a name="hosting-under-iis-or-was"></a>Размещение в службах IIS или WAS  
 При размещении службы рабочих процессов в службах IIS или WAS создается виртуальный каталог, который служит для размещения файлов и определяет режим работы службы. При размещении службы рабочих процессов в службах IIS или WAS существует несколько возможностей.  
  
-   Разместите XAMLX-файл, определяющий службу рабочих процессов, в виртуальном каталоге IIS/WAS вместе с файлом Web.config, который определяет режимы работы службы, конечные точки и другие элементы конфигурации.  
  
-   Поместите XAMLX-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS/WAS. XAMLX-файл определяет доступ к конечным точкам. Конечные точки указываются в элементе `WorkflowService.Endpoints`, как показано в следующем примере.  
  
    ```xml  
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
    >  В XAMLX-файле определить параметры поведения нельзя, поэтому для этого необходимо использовать файл Web.config.  
  
-   Поместите XAMLX-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS/WAS. Кроме того, в виртуальном каталоге может быть размещен SVC-файл. В этом файле можно указать пользовательскую фабрику узла веб-службы, применить пользовательское поведение или загрузить конфигурацию из альтернативного расположения.  
  
-   Разместите сборку в виртуальном каталоге IIS/WAS, который содержит действие, использующее действия обмена сообщениями WCF.  
  
 Xamlx-файл, определяющий службу рабочего процесса должен содержать <`Service`> корневой элемент или корневой элемент, который содержит тип, производный от <xref:System.Workflow.ComponentModel.Activity>. При использовании шаблона действий [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] создается XAMLX-файл. При использовании шаблона службы WCF Workflow Service создается XAMLX-файл.  
  
## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Размещение служб рабочего процесса в фабрике приложений Windows Server  
 Размещение службы рабочего процесса в фабрике приложений Windows Server осуществляется аналогично ее размещению на веб-сервере IIS/WAS. Единственное отличие состоит в том, что установлена фабрика приложений Windows Server. Фабрика приложений Windows Server добавляет в диспетчер IIS дополнительные средства, такие как командлеты powershell. Эти средства упрощают развертывание, управление и наблюдение за службами рабочего процесса и службами WCF. . Дополнительные сведения о Windows Server App Fabric разделе [Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037)  
  
## <a name="referencing-custom-activities"></a>Ссылки на пользовательские действия  
 Необходимо добавить ссылки на пользовательские действия <`Assemblies`> раздела <`System.Web.Compilation`>, чтобы они загружаются в домен приложения и десериализатор XAML смогут найти типы. Эти параметры могут быть указаны на уровне приложения или в корневом файле Web.config, если необходимо применять их ко всем приложениям компьютера.  
  
## <a name="deployment"></a>Развертывание  
 Для облегчения задачи развертывания создается инструмент веб-развертывания. Инструмент позволяет переносить приложения между IIS 6.0 и IIS 7.0, выполнять синхронизацию ферм серверов, а также упаковывать, архивировать и развертывать веб-приложения. Дополнительные сведения см. в разделе [MS инструмента "Развертывание"](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## <a name="see-also"></a>См. также  
 [Внутренние особенности размещения службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 [Настройка WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)
