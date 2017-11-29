---
title: "Описание службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1d3251d960b00d34c08826957e0db9c30bd5aae3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="service-description"></a><span data-ttu-id="10e8b-102">Описание службы</span><span class="sxs-lookup"><span data-stu-id="10e8b-102">Service Description</span></span>
<span data-ttu-id="10e8b-103">Образец "Описание службы" показывает, как служба может получать свое описание службы в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="10e8b-103">The Service Description sample demonstrates how a service can retrieve its service description information at runtime.</span></span> <span data-ttu-id="10e8b-104">Пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), с дополнительную операцию службы возвращать описательные сведения о службе.</span><span class="sxs-lookup"><span data-stu-id="10e8b-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with an additional service operation defined to return descriptive information about the service.</span></span> <span data-ttu-id="10e8b-105">Возвращаемые сведения содержат базовые адреса и конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="10e8b-105">The information that is returned lists the base addresses and endpoints for the service.</span></span> <span data-ttu-id="10e8b-106">Служба предоставляет эти сведения с помощью классов <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> и <xref:System.ServiceModel.Description.ServiceDescription>.</span><span class="sxs-lookup"><span data-stu-id="10e8b-106">The service provides this information using the <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost>, and <xref:System.ServiceModel.Description.ServiceDescription> classes.</span></span>  
  
 <span data-ttu-id="10e8b-107">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="10e8b-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10e8b-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="10e8b-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="10e8b-109">Этот образец содержит модифицированную версию контракта калькулятора под названием `IServiceDescriptionCalculator`.</span><span class="sxs-lookup"><span data-stu-id="10e8b-109">This sample has a modified version of the calculator contract called `IServiceDescriptionCalculator`.</span></span> <span data-ttu-id="10e8b-110">Контракт определяет дополнительную операцию службы с именем `GetServiceDescriptionInfo`, возвращающую клиенту многострочный текст, описывающий базовый адрес или адреса и конечную точку или точки службы.</span><span class="sxs-lookup"><span data-stu-id="10e8b-110">The contract defines an additional service operation named `GetServiceDescriptionInfo` that returns a multi-line string to the client that describes the base address or addresses and service endpoint or endpoints for the service.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 <span data-ttu-id="10e8b-111">Код реализации операции `GetServiceDescriptionInfo` использует класс <xref:System.ServiceModel.Description.ServiceDescription> для перечисления конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="10e8b-111">The implementation code for `GetServiceDescriptionInfo` uses the <xref:System.ServiceModel.Description.ServiceDescription> to list the service endpoints.</span></span> <span data-ttu-id="10e8b-112">Так как у конечных точек службы могут быть относительные адреса, он сначала перечисляет базовые адреса службы.</span><span class="sxs-lookup"><span data-stu-id="10e8b-112">Because service endpoints can have relative addresses, it first lists the base addresses for the service.</span></span> <span data-ttu-id="10e8b-113">Чтобы вернуть все эти сведения, код получает контекст операции с помощью <xref:System.ServiceModel.OperationContext.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="10e8b-113">To get all of this information, the code obtains its operation context using <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="10e8b-114">Класс <xref:System.ServiceModel.ServiceHost> и его объект <xref:System.ServiceModel.Description.ServiceDescription> извлекаются из контекста операции.</span><span class="sxs-lookup"><span data-stu-id="10e8b-114">The <xref:System.ServiceModel.ServiceHost> and its <xref:System.ServiceModel.Description.ServiceDescription> object are retrieved from the operation context.</span></span> <span data-ttu-id="10e8b-115">Чтобы перечислить конечные точки службы, код выполняет итерацию коллекции <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> узла службы.</span><span class="sxs-lookup"><span data-stu-id="10e8b-115">To list the base endpoints for the service, the code iterates through the service host's <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> collection.</span></span> <span data-ttu-id="10e8b-116">Чтобы перечислить служебные конечные точки службы, код выполняет итерацию коллекции конечных точек описания службы.</span><span class="sxs-lookup"><span data-stu-id="10e8b-116">To list the service endpoints for the service, the code iterates through the service description's endpoints collection.</span></span>  
  
```  
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 <span data-ttu-id="10e8b-117">При выполнении образца видны операции калькулятора и сведения службы, возвращаемые операцией `GetServiceDescriptionInfo`.</span><span class="sxs-lookup"><span data-stu-id="10e8b-117">When you run the sample, you see the calculator operations and then the service information returned by the `GetServiceDescriptionInfo` operation.</span></span> <span data-ttu-id="10e8b-118">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="10e8b-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="10e8b-119">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="10e8b-119">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="10e8b-120">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="10e8b-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="10e8b-121">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="10e8b-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="10e8b-122">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="10e8b-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10e8b-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="10e8b-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="10e8b-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="10e8b-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="10e8b-125">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10e8b-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="10e8b-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="10e8b-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
  
## <a name="see-also"></a><span data-ttu-id="10e8b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="10e8b-127">See Also</span></span>
