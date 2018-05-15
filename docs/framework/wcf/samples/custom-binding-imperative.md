---
title: Императивные пользовательские привязки
ms.date: 03/30/2017
ms.assetid: 6e13bf96-5de0-4476-b646-5f150774418d
ms.openlocfilehash: b675246279e262d73c9120411889ff27d10ae4f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="custom-binding-imperative"></a><span data-ttu-id="3bb9a-102">Императивные пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="3bb9a-102">Custom Binding Imperative</span></span>
<span data-ttu-id="3bb9a-103">В образце показано, как писать императивный код для определения и использования пользовательских привязок, без использования файла конфигурации или клиента Windows Communication Foundation (WCF) создан.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-103">The sample demonstrates how to write imperative code to define and use custom bindings without using a configuration file or a Windows Communication Foundation (WCF) generated client.</span></span> <span data-ttu-id="3bb9a-104">Этот образец объединяет возможности, предоставляемые транспортом HTTP, и канал надежного сеанса, создавая надежную привязку на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-104">This sample combines the features provided by the HTTP transport and the reliable session channel to create a reliable HTTP-based binding.</span></span> <span data-ttu-id="3bb9a-105">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bb9a-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3bb9a-107">Со стороны клиента и со стороны службы создается пользовательская привязка, содержащая два элемента привязки (надежный сеанс и HTTP):</span><span class="sxs-lookup"><span data-stu-id="3bb9a-107">On both the client and the service, a custom binding is created that contains two binding elements (Reliable Session and HTTP):</span></span>  

```csharp
ReliableSessionBindingElement reliableSession = new ReliableSessionBindingElement();  
reliableSession.Ordered = true;  
  
HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
httpTransport.AuthenticationScheme = System.Net.AuthenticationSchemes.Anonymous;  
httpTransport.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
  
CustomBinding binding = new CustomBinding(reliableSession, httpTransport);  
```
  
 <span data-ttu-id="3bb9a-108">На стороне службы привязка используется за счет добавления к ServiceHost конечной точки:</span><span class="sxs-lookup"><span data-stu-id="3bb9a-108">On the service, the binding is used by adding an endpoint to the ServiceHost:</span></span>  

```csharp
serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, "");  
```

 <span data-ttu-id="3bb9a-109">На стороне клиента привязка используется за счет <xref:System.ServiceModel.ChannelFactory> для создания канала к службе:</span><span class="sxs-lookup"><span data-stu-id="3bb9a-109">On the client, the binding is used by a <xref:System.ServiceModel.ChannelFactory> to create a channel to the service:</span></span>  

```csharp
EndpointAddress address = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = channelFactory.CreateChannel();  
```

 <span data-ttu-id="3bb9a-110">Затем этот канал используется для взаимодействия со службой:</span><span class="sxs-lookup"><span data-stu-id="3bb9a-110">This channel is then used to interact with the service:</span></span>  

```csharp
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```

 <span data-ttu-id="3bb9a-111">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-111">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3bb9a-112">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-112">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3bb9a-113">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3bb9a-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3bb9a-114">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3bb9a-114">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3bb9a-115">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3bb9a-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="3bb9a-116">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3bb9a-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3bb9a-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3bb9a-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3bb9a-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3bb9a-119">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3bb9a-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Custom\Imperative`  
  
## <a name="see-also"></a><span data-ttu-id="3bb9a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3bb9a-121">See Also</span></span>  
 [<span data-ttu-id="3bb9a-122">Пользовательская привязка</span><span class="sxs-lookup"><span data-stu-id="3bb9a-122">Custom Binding</span></span>](http://msdn.microsoft.com/library/657e8143-beb0-472d-9cfe-ed1a19c2ab08)
