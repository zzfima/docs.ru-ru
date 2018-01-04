---
title: "Параллельное управление версиями в WorkflowServiceHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db8f79fcdc1398b891933f5fef9f07410e5de11e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a>Параллельное управление версиями в WorkflowServiceHost
Параллельное управление версиями <xref:System.ServiceModel.Activities.WorkflowServiceHost>, введенное в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], предоставляет возможность размещения нескольких версий службы Workflow Service на одной конечной точке. Предоставляемая функциональность параллельной работы позволяет настроить службу Workflow Service таким образом, чтобы новые экземпляры службы Workflow Service создавались с использованием нового определения рабочего процесса, а запущенные экземпляры завершались с использованием существующего определения. Данный раздел содержит общие сведения о параллельном выполнении служб Workflow Services с использованием <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
> [!NOTE]
>  Для загрузки образца и просмотреть пошаговое видеоруководство управления версиями side-by-side службы рабочего процесса, в разделе [параллельное управление версиями с помощью службы рабочего процесса Xamlx руководством](http://go.microsoft.com/fwlink/?LinkId=393746).  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a>Размещение нескольких версий в службе Workflow Service  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> содержит два свойства, которые можно настроить для разрешения параллельного выполнения нескольких версий рабочего процесса: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> и <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>. <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> содержит поддерживаемые версии службы Workflow Service, а <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> используется для уникальной идентификации каждой службы Workflow Service. Для этого нужно связать <xref:System.Activities.WorkflowIdentity> со службой Workflow Service. В <xref:System.Activities.WorkflowIdentity> содержится три элемента информации для идентификации. <xref:System.Activities.WorkflowIdentity.Name%2A> и <xref:System.Activities.WorkflowIdentity.Version%2A> содержат имя и <xref:System.Version> и являются обязательными, а <xref:System.Activities.WorkflowIdentity.Package%2A> является необязательным и может использоваться для указания дополнительной строки с информацией (например, именем сборки или другими полезными сведениями). Каждая служба Workflow Service, содержащаяся в коллекции <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>, должна иметь уникальный <xref:System.Activities.WorkflowIdentity>. <xref:System.Activities.WorkflowIdentity> уникален, если какое-либо из его трех свойств отличается от другого <xref:System.Activities.WorkflowIdentity>. Объект `null` <xref:System.Activities.WorkflowIdentity> является допустимым значением для <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, но может быть только одна предыдущая версия службы workflow Service `null` <xref:System.Activities.WorkflowIdentity>.  
  
> [!IMPORTANT]
>  Экземпляр <xref:System.Activities.WorkflowIdentity> не должен содержать персональные данные (PII). <xref:System.Activities.WorkflowIdentity> состоит из 3 частей: <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) и <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>). Сведения об объекте <xref:System.Activities.WorkflowIdentity>, используемом для создания экземпляра, передаются средой выполнения всем настроенным службам отслеживания на различных этапах жизненного цикла действия. Отслеживание WF не имеет механизмов, позволяющих скрывать персональные данные (конфиденциальные пользовательские данные). Поэтому экземпляр <xref:System.Activities.WorkflowIdentity> не должен содержать никаких персональных данных, так как они будут передаваться средой выполнения в записях отслеживания и могут отображаться любому пользователю с доступом к записям отслеживания.  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a>Правила размещения нескольких версий службы Workflow Service  
 При добавлении пользователем дополнительной версии на <xref:System.ServiceModel.Activities.WorkflowServiceHost> существует несколько условий, которые необходимо выполнить для размещения службы Workflow Service с одним и тем же описанием и набором конечных точек. Если одна из дополнительных версий не выполняет эти условия, <xref:System.ServiceModel.Activities.WorkflowServiceHost> возвращает исключение при вызове `Open`. Каждое определение рабочего процесса, предоставленное узлу в качестве дополнительной версии, должно выполнять следующие требования (где основной версией является определение службы Workflow Service, предоставленное конструктору узла). Дополнительная версия рабочего процесса должна:  
  
-   иметь одинаковый <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> с основной версией службы Workflow Service.  
  
-   Не должна содержать действий <xref:System.ServiceModel.Activities.Receive> или <xref:System.ServiceModel.Activities.SendReply> в своем <xref:System.ServiceModel.Activities.WorkflowService.Body%2A>, которых нет в основной версии, и они должны соответствовать контракту операции.  
  
-   Иметь уникальный <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>. Может иметь одно и только одно определение рабочего процесса `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
 Некоторые изменения разрешены. Следующие элементы могут различаться между версиями:  
  
-   <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> может иметь Name и Package, отличные от основной версии.  
  
-   Значение <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> может отличаться от основной версии.  
  
-   <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> может отличаться от основной версии.  
  
-   <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> может отличаться от основной версии.  
  
### <a name="configuring-the-definitionidentity"></a>Настройка DefinitionIdentity  
 При создании службы рабочего процесса в конструкторе рабочих процессов <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> задается с помощью **свойства** окна. Щелкните вне корневого действия службы в конструкторе, чтобы выбрать службу рабочего процесса, а затем выберите **окно свойств** из **представление** меню. Выберите **WorkflowIdentity** из раскрывающегося списка, который появляется рядом со **DefinitionIdentity** свойства, а затем разверните и задайте необходимые <xref:System.Activities.WorkflowIdentity> свойства. В следующем примере <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> оснащен <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` и <xref:System.Activities.WorkflowIdentity.Version%2A> из `1.0.0.0`. <xref:System.Activities.WorkflowIdentity.Package%2A> является необязательным и в данном примере равняется `null`.  
  
 ![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv1.bmp "WorkflowServiceDefinitionIdentityv1")  
  
 Если служба Workflow Service размещается резидентно, <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> настраивается при построении службы Workflow Service. В следующем примере <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> настроены с одинаковыми значениями в предыдущем примере <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` и <xref:System.Activities.WorkflowIdentity.Name%2A> из `1.0.0.0`.  
  
```csharp  
WorkflowService service = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflow(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
```  
  
```vb  
Dim service As New WorkflowService  
With service  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflow  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
```  
  
 Объект <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> не является обязательным, хотя только одна версия службы рабочего процесса может иметь **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
> [!NOTE]
>  Это полезно, если служба изначально была развернута без настроенного <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, а после этого создается обновленная версия.  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a>Добавление новой версии к службе Workflow Service, размещенной на веб-сервере  
 Первым шагом в настройке новой версии службы Workflow Service в службе, размещенной на веб-сервере, является создание новой папки в папке `App_Code`, которая имеет то же имя, что и файл службы. Если файл `xamlx` службы имеет имя `MortgageWorkflow.xamlx`, необходимо присвоить папке имя `MortgageWorkflow`. Поместите копию файла `xamlx` изначальной службы в эту папку и присвойте ему другое имя, например `MortgageWorkflowV1.xamlx`. Внесите желаемые изменения в основную службу, обновите ее <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, затем разверните службу. В следующем примере <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> был обновлен с помощью <xref:System.Activities.WorkflowIdentity.Name%2A>, равного `MortageWorkflow`, и с <xref:System.Activities.WorkflowIdentity.Version%2A>, равной `2.0.0.0`.  
  
 ![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv2.bmp "WorkflowServiceDefinitionIdentityv2")  
  
 При повторном запуске службы предыдущая версия автоматически добавится в коллекцию <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>, так как она находится в указанной подпапке `App_Code`. Обратите внимание, что, если основной версией службы рабочего процесса имеет `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> предыдущие версии не будут добавлены. В одной версии `null` может быть равен <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, но, если имеется несколько таких версий, основная версия не должна быть с `null`, равным <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, в противном случае предыдущие версии не будут добавлены в коллекцию <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a>Добавление новой версии к службе Workflow Service, размещенной резидентно  
 При добавлении новой версии в резидентную службу Workflow Service <xref:System.ServiceModel.Activities.WorkflowServiceHost> настраивается с основной версией службы Workflow Service, а предыдущие версии должны быть явным образом добавлены в коллекцию <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>. В следующем примере <xref:System.ServiceModel.Activities.WorkflowServiceHost> настраивается с основной службой Workflow Service, которая использует определение рабочего процесса `MortgageWorkflowV2`, и в коллекцию `MortgageWorkflowV1` добавляется служба Workflow Service, настроенная с определением рабочего процесса <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>. Каждая служба Workflow Service настраивается с уникальным <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, отражающим версию определения рабочего процесса.  
  
```csharp  
// Create the primary version of the workflow service.  
WorkflowService serviceV2 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV2(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(2, 0, 0, 0)  
    }  
};  
  
// Configure the WorkflowServiceHost with the current version  
// of the workflow service. This code requires Administrator  
// privileges to function correctly. If running from Visual  
// Studio, Visual Studio must be run with Administrator privileges.  
WorkflowServiceHost host = new WorkflowServiceHost(serviceV2,   
    new Uri("http://localhost:8080/MortgageWorkflowService"));  
  
// Create the previous version of the workflow service.  
WorkflowService serviceV1 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV1(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
  
// Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1);  
```  
  
```vb  
'Create the primary version of the workflow service  
Dim serviceV2 As New WorkflowService  
With serviceV2  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV2  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(2, 0, 0, 0) _  
    }  
End With  
  
'Configure the WorkflowServiceHost with the current version  
'of the workflow service. This code requires Administrator  
'privileges to function correctly. If running from Visual  
'Studio, Visual Studio must be run with Administrator privileges.  
  
Dim host As New WorkflowServiceHost(serviceV2, _  
    New Uri("http://localhost:8080/MortgageWorkflowService"))  
  
'Create the previous version of the workflow service.  
Dim serviceV1 As New WorkflowService  
With serviceV1  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV1  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
  
'Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1)  
```
