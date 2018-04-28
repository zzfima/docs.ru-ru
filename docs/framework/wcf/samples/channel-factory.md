---
title: Фабрика каналов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37b5f880b18f4caac9dc452d93129922ecc33543
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="channel-factory"></a><span data-ttu-id="72db0-102">Фабрика каналов</span><span class="sxs-lookup"><span data-stu-id="72db0-102">Channel Factory</span></span>
<span data-ttu-id="72db0-103">В этом образце показано, как клиентское приложение может создать канал с помощью <xref:System.ServiceModel.ChannelFactory>, вместо использования созданного клиента.</span><span class="sxs-lookup"><span data-stu-id="72db0-103">This sample demonstrates how a client application can create a channel with the <xref:System.ServiceModel.ChannelFactory> class instead of a generated client.</span></span> <span data-ttu-id="72db0-104">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="72db0-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72db0-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="72db0-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="72db0-106">Чтобы создать канал для конечной точки службы, в этом образце используется класс <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="72db0-106">This sample uses the <xref:System.ServiceModel.ChannelFactory%601> class to create a channel to a service endpoint.</span></span> <span data-ttu-id="72db0-107">Как правило, для создания канала к конечной точке службы можно создать тип клиента с [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) и создайте экземпляр созданного типа.</span><span class="sxs-lookup"><span data-stu-id="72db0-107">Typically, to create a channel to a service endpoint you generate a client type with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) and create an instance of the generated type.</span></span> <span data-ttu-id="72db0-108">Кроме того, канал можно создать с помощью класса <xref:System.ServiceModel.ChannelFactory%601>, как показано в этом образце.</span><span class="sxs-lookup"><span data-stu-id="72db0-108">You can also create a channel by using the <xref:System.ServiceModel.ChannelFactory%601> class, as demonstrated in this sample.</span></span> <span data-ttu-id="72db0-109">Службы, созданные в следующем образце кода идентична службы в [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="72db0-109">The service created by the following sample code is identical to the service in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
```csharp  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="72db0-110">Если этот образец выполняется на нескольких компьютерах, в предыдущем фрагменте кода необходимо заменить localhost на полное имя компьютера, на котором выполняется служба.</span><span class="sxs-lookup"><span data-stu-id="72db0-110">If you are running this sample in a cross-machine scenario, you must replace "localhost" in the preceding code with the fully-qualified name of the machine that is running the service.</span></span> <span data-ttu-id="72db0-111">В этом образце для задания адреса конечной точки конфигурация не используется, поэтому это необходимо сделать в коде.</span><span class="sxs-lookup"><span data-stu-id="72db0-111">This sample does not use configuration to set the endpoint address, so this must be done in code.</span></span>  
  
 <span data-ttu-id="72db0-112">После создания канала можно вызывать операции службы, как это можно было бы делать с помощью созданного клиента.</span><span class="sxs-lookup"><span data-stu-id="72db0-112">Once the channel is created, service operations can be invoked just as with a generated client.</span></span>  
  
```csharp  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
 <span data-ttu-id="72db0-113">Чтобы закрыть канал, его необходимо сначала привести к интерфейсу <xref:System.ServiceModel.IClientChannel>.</span><span class="sxs-lookup"><span data-stu-id="72db0-113">To close the channel, it must first be cast to an <xref:System.ServiceModel.IClientChannel> interface.</span></span> <span data-ttu-id="72db0-114">Это связано с тем, что канал обычно объявляется в клиентском приложении с помощью интерфейса `ICalculator`, имеющего методы `Add` и `Subtract`, но не имеющего метода `Close`.</span><span class="sxs-lookup"><span data-stu-id="72db0-114">This is because the channel as generated is declared in the client application using the `ICalculator` interface, which has methods like `Add` and `Subtract` but not `Close`.</span></span> <span data-ttu-id="72db0-115">Метод `Close` наследуется от интерфейса <xref:System.ServiceModel.ICommunicationObject>.</span><span class="sxs-lookup"><span data-stu-id="72db0-115">The `Close` method originates on the <xref:System.ServiceModel.ICommunicationObject> interface.</span></span>  
  
```csharp  
// Close the channel.  
 ((IClientChannel)client).Close();  
```  
  
 <span data-ttu-id="72db0-116">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="72db0-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="72db0-117">Чтобы закрыть клиентское приложение, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="72db0-117">Press ENTER in the client window to shut down the client application.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="72db0-118">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="72db0-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="72db0-119">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72db0-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="72db0-120">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72db0-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="72db0-121">Обратите внимание, что этот в этом образце не включается публикация метаданных.</span><span class="sxs-lookup"><span data-stu-id="72db0-121">Note that this sample does not enable metadata publishing.</span></span> <span data-ttu-id="72db0-122">Чтобы заново создать тип клиента, необходимо включить в образце публикацию метаданных.</span><span class="sxs-lookup"><span data-stu-id="72db0-122">You must first enable metadata publishing for this sample to regenerate the client type.</span></span>  
  
3.  <span data-ttu-id="72db0-123">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72db0-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-cross-machine"></a><span data-ttu-id="72db0-124">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="72db0-124">To run the sample cross machine</span></span>  
  
1.  <span data-ttu-id="72db0-125">В следующем фрагменте кода замените localhost на полное имя компьютера, на котором выполняется служба.</span><span class="sxs-lookup"><span data-stu-id="72db0-125">Replace "localhost" in the following code with the fully-qualified name of the machine that is running the service.</span></span>  
  
    ```csharp  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="72db0-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="72db0-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="72db0-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="72db0-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="72db0-128">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="72db0-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="72db0-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="72db0-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
  
## <a name="see-also"></a><span data-ttu-id="72db0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="72db0-130">See Also</span></span>
