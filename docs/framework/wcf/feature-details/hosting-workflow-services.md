---
title: Размещение службы рабочего процесса
ms.date: 03/30/2017
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
ms.openlocfilehash: d51157863984314583c5d225bc9d8d0b6cf74874
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50186100"
---
# <a name="hosting-workflow-services"></a>Размещение службы рабочего процесса
Для обработки входящих сообщений служба рабочих процессов должна быть размещена. Службы рабочих процессов используют инфраструктуру обмена сообщениями WCF и поэтому также требуют размещения. Подобно службам WCF службы рабочего процесса могут размещаться в любом управляемом приложении, в группе Internet Information Services (IIS), или в Windows процесса активации Services (WAS). Кроме того службы рабочего процесса могут размещаться в фабрике приложений Windows Server. Дополнительные сведения о Windows Server App Fabric см. в разделе [документации по Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=193037), [AppFabric Hosting Features](https://go.microsoft.com/fwlink/?LinkId=196494), и [основы размещения AppFabric](https://go.microsoft.com/fwlink/?LinkId=196495). Дополнительные сведения о различных способах размещения WCF служб см. в разделе [размещение служб](../../../../docs/framework/wcf/hosting-services.md).

## <a name="hosting-in-a-managed-application"></a>Размещение в управляемом приложении
 Размещение службы рабочего процесса в управляемом приложении производится с помощью класса <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Конструктор <xref:System.ServiceModel.Activities.WorkflowServiceHost> позволяет указать одноэлементный экземпляр службы рабочих процессов, определить службу рабочих процессов или действие, которое использует действия обмена сообщениями рабочих процессов. После вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> служба переходит в режим ожидания передачи входящих сообщений.

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
    > В XAMLX-файле определить параметры поведения нельзя, поэтому для этого необходимо использовать файл Web.config.

-   Поместите XAMLX-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS/WAS. Кроме того, в виртуальном каталоге может быть размещен SVC-файл. В этом файле можно указать пользовательскую фабрику узла веб-службы, применить пользовательское поведение или загрузить конфигурацию из альтернативного расположения.

-   Разместите сборку в виртуальном каталоге IIS/WAS, который содержит действие, использующее действия обмена сообщениями WCF.

 Xamlx-файл, определяющий службу рабочего процесса должен содержать <`Service`> корневой элемент или корневой элемент, содержащий любой тип, производный от <xref:System.Workflow.ComponentModel.Activity>. При использовании шаблона действия Visual Studio, создается xamlx-файл. При использовании шаблона службы WCF Workflow Service создается xamlx-файл.

## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Размещение служб рабочего процесса в фабрике приложений Windows Server
 Размещение службы рабочего процесса в фабрике приложений Windows Server осуществляется аналогично ее размещению на веб-сервере IIS/WAS. Единственное отличие состоит в том, что установлена фабрика приложений Windows Server. Фабрика приложений Windows Server добавляет в диспетчер IIS дополнительные средства, такие как командлеты powershell. Эти средства упрощают развертывание, управление и наблюдение за службами рабочего процесса и службами WCF.

## <a name="referencing-custom-activities"></a>Ссылки на пользовательские действия
 Необходимо добавить ссылки на пользовательские действия <`Assemblies`> раздела <`System.Web.Compilation`>, чтобы они были загружены в домен приложения, а десериализатор XAML смог найти типы. Эти параметры могут быть указаны на уровне приложения или в корневом файле Web.config, если необходимо применять их ко всем приложениям компьютера.

## <a name="deployment"></a>Развертывание
 Для облегчения задачи развертывания создается инструмент веб-развертывания. Инструмент позволяет переносить приложения между IIS 6.0 и IIS 7.0, выполнять синхронизацию ферм серверов, а также упаковывать, архивировать и развертывать веб-приложения. Дополнительные сведения см. в разделе [средство развертывания MS](https://go.microsoft.com/fwlink/?LinkId=178690).

## <a name="see-also"></a>См. также

- [Внутренние особенности размещения службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)
- [Настройка WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)