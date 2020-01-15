---
title: Размещение службы рабочего процесса
ms.date: 03/30/2017
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
ms.openlocfilehash: 21e24853229d09e3f1af719573f47bb12c8fddb6
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963731"
---
# <a name="hosting-workflow-services"></a>Размещение службы рабочего процесса

Для обработки входящих сообщений служба рабочих процессов должна быть размещена. Службы рабочих процессов используют инфраструктуру обмена сообщениями WCF и поэтому также требуют размещения. Как и службы WCF, службы рабочих процессов могут размещаться в любом управляемом приложении, в службы IIS (IIS) или в службах активации Windows (WAS). Кроме того, службы рабочих процессов могут размещаться в Windows Server App Fabric. Дополнительные сведения о структуре приложений Windows Server см. в [документации по Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10)), [функциям размещения AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))и [концепциям размещения AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677371(v=azure.10)). Дополнительные сведения о различных способах размещения служб WCF см. в разделе [службы размещения](../../../../docs/framework/wcf/hosting-services.md).

## <a name="hosting-in-a-managed-application"></a>Размещение в управляемом приложении
 Размещение службы рабочего процесса в управляемом приложении производится с помощью класса <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Конструктор <xref:System.ServiceModel.Activities.WorkflowServiceHost> позволяет указать одноэлементный экземпляр службы рабочих процессов, определить службу рабочих процессов или действие, которое использует действия обмена сообщениями рабочих процессов. После вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> служба переходит в режим ожидания передачи входящих сообщений.

## <a name="hosting-under-iis-or-was"></a>Размещение в службах IIS или WAS
 При размещении службы рабочих процессов в службах IIS или WAS создается виртуальный каталог, который служит для размещения файлов и определяет режим работы службы. При размещении службы рабочих процессов в службах IIS или WAS существует несколько возможностей.

- Разместите XAMLX-файл, определяющий службу рабочих процессов, в виртуальном каталоге IIS/WAS вместе с файлом Web.config, который определяет режимы работы службы, конечные точки и другие элементы конфигурации.

- Поместите XAMLX-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS/WAS. XAMLX-файл определяет доступ к конечным точкам. Конечные точки указываются в элементе `WorkflowService.Endpoints`, как показано в следующем примере.

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

- Поместите XAMLX-файл, определяющий службу рабочего процесса, в виртуальный каталог IIS/WAS. Кроме того, в виртуальном каталоге может быть размещен SVC-файл. В этом файле можно указать пользовательскую фабрику узла веб-службы, применить пользовательское поведение или загрузить конфигурацию из альтернативного расположения.

- Разместите сборку в виртуальном каталоге IIS/WAS, который содержит действие, использующее действия обмена сообщениями WCF.

 XAMLX-файл, определяющий службу рабочего процесса, должен содержать <`Service`> корневой элемент или корневой элемент, который содержит любой тип, производный от <xref:System.Workflow.ComponentModel.Activity>. При использовании шаблона действия Visual Studio создается файл xamlx. При использовании шаблона службы рабочего процесса WCF создается файл. xamlx.

## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Размещение служб рабочего процесса в фабрике приложений Windows Server
 Размещение службы рабочего процесса в фабрике приложений Windows Server осуществляется аналогично ее размещению на веб-сервере IIS/WAS. Единственное отличие состоит в том, что установлена фабрика приложений Windows Server. Фабрика приложений Windows Server добавляет в диспетчер IIS дополнительные средства, такие как командлеты powershell. Эти средства упрощают развертывание, управление и наблюдение за службами рабочего процесса и службами WCF.

## <a name="referencing-custom-activities"></a>Ссылки на пользовательские действия
 Ссылки на настраиваемые действия должны быть добавлены в раздел <`Assemblies`> в разделе <`System.Web.Compilation`>, чтобы они загружались в домен приложения, а десериализатор XAML может научиться определять типы. Эти параметры могут быть указаны на уровне приложения или в корневом файле Web.config, если необходимо применять их ко всем приложениям компьютера.

## <a name="deployment"></a>Развертывание
 Для облегчения задачи развертывания создается инструмент веб-развертывания. Инструмент позволяет переносить приложения между IIS 6.0 и IIS 7.0, выполнять синхронизацию ферм серверов, а также упаковывать, архивировать и развертывать веб-приложения. Дополнительные сведения см. в разделе [средство MS Deployment Tool](https://go.microsoft.com/fwlink/?LinkId=178690).

## <a name="see-also"></a>См. также:

- [Внутренние особенности размещения службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)
- [Настройка WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)
