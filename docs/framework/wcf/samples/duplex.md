---
title: "Дуплекс"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14aae02b36798b90633981cb1d68d10a0cbf29fc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="duplex"></a><span data-ttu-id="3a896-102">Дуплекс</span><span class="sxs-lookup"><span data-stu-id="3a896-102">Duplex</span></span>
<span data-ttu-id="3a896-103">Этот образец демонстрирует, как определить и реализовать дуплексный контракт.</span><span class="sxs-lookup"><span data-stu-id="3a896-103">The Duplex sample demonstrates how to define and implement a duplex contract.</span></span> <span data-ttu-id="3a896-104">Дуплексная связь имеет место, когда клиент устанавливает сеанс со службой и предоставляет службе канал, по которому служба может отправлять сообщения обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="3a896-104">Duplex communication occurs when a client establishes a session with a service and gives the service a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="3a896-105">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="3a896-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="3a896-106">Дуплексный контракт определяется в виде пары интерфейсов - основной интерфейс от клиента к службе и интерфейс обратного вызова от службы к клиенту.</span><span class="sxs-lookup"><span data-stu-id="3a896-106">A duplex contract is defined as a pair of interfaces—a primary interface from the client to the service and a callback interface from the service to the client.</span></span> <span data-ttu-id="3a896-107">В этом образце интерфейс `ICalculatorDuplex` позволяет клиенту выполнять математические операции, вычисляя результат в ходе сеанса.</span><span class="sxs-lookup"><span data-stu-id="3a896-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating the result over a session.</span></span> <span data-ttu-id="3a896-108">Служба возвращает результаты в интерфейсе `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="3a896-108">The service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="3a896-109">Для дуплексного контракта требуется сеанс, поскольку необходимо установить контекст для корреляции набора сообщений, передаваемых между клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="3a896-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a896-110">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="3a896-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3a896-111">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="3a896-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="3a896-112">Дуплексный контракт определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a896-112">The duplex contract is defined as follows:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,  
                 CallbackContract=typeof(ICalculatorDuplexCallback))]  
public interface ICalculatorDuplex  
{  
    [OperationContract(IsOneWay = true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
}  
  
public interface ICalculatorDuplexCallback  
{  
    [OperationContract(IsOneWay = true)]  
    void Result(double result);  
    [OperationContract(IsOneWay = true)]  
    void Equation(string eqn);  
}  
```  
  
 <span data-ttu-id="3a896-113">Класс `CalculatorService` реализует основной интерфейс `ICalculatorDuplex`.</span><span class="sxs-lookup"><span data-stu-id="3a896-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="3a896-114">Служба использует режим экземпляра <xref:System.ServiceModel.InstanceContextMode.PerSession> для поддержания результата для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="3a896-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="3a896-115">Закрытое свойство `Callback` используется для доступа к каналу обратного вызова к клиенту.</span><span class="sxs-lookup"><span data-stu-id="3a896-115">A private property named `Callback` is used to access the callback channel to the client.</span></span> <span data-ttu-id="3a896-116">Служба использует обратный вызов для отправки сообщений обратно клиенту через интерфейс обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3a896-116">The service uses the callback for sending messages back to the client through the callback interface.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorDuplex  
{  
    double result = 0.0D;  
    string equation;  
  
    public CalculatorService()  
    {  
        equation = result.ToString();  
    }  
  
    public void Clear()  
    {  
        Callback.Equation(equation + " = " + result.ToString());  
        equation = result.ToString();  
    }  
  
    public void AddTo(double n)  
    {  
        result += n;  
        equation += " + " + n.ToString();  
        Callback.Result(result);  
    }  
    ...  
    ICalculatorDuplexCallback Callback  
    {  
        get  
        {  
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="3a896-117">Для получения сообщений от службы клиент обязан предоставить класс, который реализует интерфейс обратного вызова дуплексного контракта.</span><span class="sxs-lookup"><span data-stu-id="3a896-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="3a896-118">В этом образце для реализации интерфейса `CallbackHandler` определен класс `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="3a896-118">In the sample, a `CallbackHandler` class is defined to implement the `ICalculatorDuplexCallback` interface.</span></span>  
  
```  
public class CallbackHandler : ICalculatorDuplexCallback  
{  
   public void Result(double result)  
   {  
      Console.WriteLine("Result({0})", result);  
   }  
  
   public void Equation(string equation)  
   {  
      Console.WriteLine("Equation({0}", equation);  
   }  
}  
```  
  
 <span data-ttu-id="3a896-119">Прокси-объект, формируемый для дуплексного контракта, при создании требует предоставления объекта <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="3a896-119">The proxy that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> to be provided upon construction.</span></span> <span data-ttu-id="3a896-120">Этот объект <xref:System.ServiceModel.InstanceContext> используется в качестве сайта для объекта, реализующего интерфейс обратного вызова и обрабатывающего сообщения, которые отправляются службой обратно.</span><span class="sxs-lookup"><span data-stu-id="3a896-120">This <xref:System.ServiceModel.InstanceContext> is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="3a896-121">Класс <xref:System.ServiceModel.InstanceContext> создается с экземпляром класса `CallbackHandler`.</span><span class="sxs-lookup"><span data-stu-id="3a896-121">An <xref:System.ServiceModel.InstanceContext> is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="3a896-122">Этот объект обрабатывает сообщения, отправляемые службой клиенту в интерфейсе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3a896-122">This object handles messages sent from the service to the client on the callback interface.</span></span>  
  
```  
// Construct InstanceContext to handle messages on callback interface.  
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());  
  
// Create a client.  
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);  
  
Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");  
Console.WriteLine();  
  
// Call the AddTo service operation.  
double value = 100.00D;  
client.AddTo(value);  
  
// Call the SubtractFrom service operation.  
value = 50.00D;  
client.SubtractFrom(value);  
  
// Call the MultiplyBy service operation.  
value = 17.65D;  
client.MultiplyBy(value);  
  
// Call the DivideBy service operation.  
value = 2.00D;  
client.DivideBy(value);  
  
// Complete equation.  
client.Clear();  
  
Console.ReadLine();  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 <span data-ttu-id="3a896-123">Конфигурация изменена таким образом, чтобы предоставлялась привязка, которая поддерживает как сеансовую, так и дуплексную связь.</span><span class="sxs-lookup"><span data-stu-id="3a896-123">The configuration has been modified to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="3a896-124">Привязка `wsDualHttpBinding` поддерживает сеансовую и дуплексную связь, предоставляя двойные соединения HTTP (по одному для каждого направления).</span><span class="sxs-lookup"><span data-stu-id="3a896-124">The `wsDualHttpBinding` supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span> <span data-ttu-id="3a896-125">На стороне службы единственным отличием в конфигурации является используемая привязка.</span><span class="sxs-lookup"><span data-stu-id="3a896-125">On the service, the only difference in configuration is the binding that is used.</span></span> <span data-ttu-id="3a896-126">На стороне клиента необходимо настроить адрес, который будет использоваться сервером для подключения к клиенту, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3a896-126">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
  <endpoint name=""  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="wsDualHttpBinding"   
            bindingConfiguration="DuplexBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
</client>  
  
<bindings>  
  <!-- Configure a binding that support duplex communication. -->  
  <wsDualHttpBinding>  
    <binding name="DuplexBinding"   
             clientBaseAddress="http://localhost:8000/myClient/">  
    </binding>  
  </wsDualHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="3a896-127">При выполнении образца видны сообщения, возвращаемые клиенту в интерфейсе обратного вызова, отправляемом службой.</span><span class="sxs-lookup"><span data-stu-id="3a896-127">When you run the sample, you see the messages that are returned to the client on the callback interface that is sent from the service.</span></span> <span data-ttu-id="3a896-128">Отображается каждый промежуточный результат с последующим отображением всей формулы после завершения всех операций.</span><span class="sxs-lookup"><span data-stu-id="3a896-128">Each intermediate result is displayed, followed by the entire equation upon the completion of all operations.</span></span> <span data-ttu-id="3a896-129">Чтобы закрыть клиент, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3a896-129">Press ENTER to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3a896-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3a896-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3a896-131">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a896-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3a896-132">Чтобы создать выпуск решения C#, C++ или Visual Basic .NET, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a896-132">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="3a896-133">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a896-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3a896-134">При запуске клиента в конфигурации между компьютерами, не забудьте заменить «localhost» в обоих `address` атрибут [конечной точки](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент и `clientBaseAddress` атрибут [ \< Привязка >](../../../../docs/framework/misc/binding.md) элемент [ \<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) элемент с именем соответствующего компьютера, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3a896-134">When running the client in a cross-machine configuration, be sure to replace "localhost" in both the `address` attribute of the [endpoint](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element and the `clientBaseAddress` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown in the following:</span></span>  
  
    ```xml  
    <client>  
    <endpoint name = ""  
    address="http://service_machine_name/servicemodelsamples/service.svc"  
    ... />  
    </client>  
    ...  
    <wsDualHttpBinding>  
    <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">  
    </binding>  
    </wsDualHttpBinding>  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="3a896-135">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a896-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3a896-136">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3a896-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3a896-137">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a896-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3a896-138">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3a896-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`  
  
## <a name="see-also"></a><span data-ttu-id="3a896-139">См. также</span><span class="sxs-lookup"><span data-stu-id="3a896-139">See Also</span></span>
