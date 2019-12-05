---
title: Пример для начала работы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: 59f9edf67c03fb7d8670058eca8ea672a6f64c02
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837874"
---
# <a name="getting-started-sample"></a><span data-ttu-id="4e537-102">Пример для начала работы</span><span class="sxs-lookup"><span data-stu-id="4e537-102">Getting Started Sample</span></span>

<span data-ttu-id="4e537-103">В начало работы примере демонстрируется реализация типичной службы и стандартного клиента с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4e537-103">The Getting Started sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="4e537-104">Этот образец является основой для всех остальных базовых образцов технологий.</span><span class="sxs-lookup"><span data-stu-id="4e537-104">This sample is the basis for all other basic technology samples.</span></span>

> [!NOTE]
> <span data-ttu-id="4e537-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="4e537-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e537-106">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e537-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4e537-107">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4e537-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="4e537-108">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="4e537-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4e537-109">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4e537-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

<span data-ttu-id="4e537-110">Служба описывает операции, выполняемые ею в контракте службы, который она открыто предоставляет как метаданные.</span><span class="sxs-lookup"><span data-stu-id="4e537-110">The service describes the operations it performs in a service contract that it exposes publicly as metadata.</span></span> <span data-ttu-id="4e537-111">Служба также содержит код для реализации операций.</span><span class="sxs-lookup"><span data-stu-id="4e537-111">The service also contains the code to implement the operations.</span></span>

<span data-ttu-id="4e537-112">Клиент содержит определение контракта службы и прокси-класс для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="4e537-112">The client contains a definition of the service contract and a proxy class for accessing the service.</span></span> <span data-ttu-id="4e537-113">Код прокси-сервера создается на основе метаданных службы с помощью [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4e537-113">The proxy code is generated from the service metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

<span data-ttu-id="4e537-114">В Windows Vista служба размещается в службе активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="4e537-114">On Windows Vista, the service is hosted in the Windows Activation Service (WAS).</span></span> <span data-ttu-id="4e537-115">В [!INCLUDE[wxp](../../../../includes/wxp-md.md)] и [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] она размещается в службах IIS и ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4e537-115">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], it is hosted by Internet Information Services (IIS) and ASP.NET.</span></span> <span data-ttu-id="4e537-116">Размещение службы в IIS или WAS позволяет активировать службу автоматически при первом доступе к ней.</span><span class="sxs-lookup"><span data-stu-id="4e537-116">Hosting a service in IIS or WAS allows the service to be activated automatically when it is accessed for the first time.</span></span>

> [!NOTE]
> <span data-ttu-id="4e537-117">Если вы предпочитаете приступить к работе с примером, в котором размещена служба, в консольном приложении, а не IIS, см. пример с помощью [узла для самостоятельного размещения](../../../../docs/framework/wcf/samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="4e537-117">If you would prefer to get started with a sample that hosts the service in a console application instead of IIS, see the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>

<span data-ttu-id="4e537-118">Служба и клиент указывают данные для доступа в параметрах файла конфигурации, что обеспечивает гибкость при развертывании.</span><span class="sxs-lookup"><span data-stu-id="4e537-118">The service and client specify access details in configuration file settings, which provide flexibility at the time of deployment.</span></span> <span data-ttu-id="4e537-119">Эти данные включают определение конечной точки, задающей адрес, привязку и контракт.</span><span class="sxs-lookup"><span data-stu-id="4e537-119">This includes an endpoint definition that specifies an address, binding, and contract.</span></span> <span data-ttu-id="4e537-120">Привязка определяет транспорт и детали обеспечения безопасности, касающиеся доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="4e537-120">The binding specifies transport and security details for how the service is to be accessed.</span></span>

<span data-ttu-id="4e537-121">Служба настраивает среду выполнения на публикацию ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="4e537-121">The service configures a run-time behavior to publish its metadata.</span></span>

<span data-ttu-id="4e537-122">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="4e537-122">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="4e537-123">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление).</span><span class="sxs-lookup"><span data-stu-id="4e537-123">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="4e537-124">Клиент осуществляет вызовы заданной математической операции, а служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="4e537-124">The client makes requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="4e537-125">Служба реализует контракт `ICalculator`, определенный в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4e537-125">The service implements an `ICalculator` contract that is defined in the following code.</span></span>

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="4e537-126">Реализация службы вычисляет и возвращает соответствующий результат, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4e537-126">The service implementation calculates and returns the appropriate result, as shown in the following example code.</span></span>

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="4e537-127">Служба предоставляет конечную точку для взаимодействия с ней; конечная точка определяется в файле конфигурации (Web.config). См. следующий образец конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e537-127">The service exposes an endpoint for communicating with the service, defined using a configuration file (Web.config), as shown in the following sample configuration.</span></span>

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

<span data-ttu-id="4e537-128">Служба предоставляет конечную точку по базовому адресу, который предоставляется узлом IIS или WAS.</span><span class="sxs-lookup"><span data-stu-id="4e537-128">The service exposes the endpoint at the base address provided by the IIS or WAS host.</span></span> <span data-ttu-id="4e537-129">Привязка настраивается с использованием стандартного объекта <xref:System.ServiceModel.WSHttpBinding>, обеспечивающего взаимодействие по протоколу HTTP и стандартному протоколу веб-служб для адресации и безопасности.</span><span class="sxs-lookup"><span data-stu-id="4e537-129">The binding is configured with a standard <xref:System.ServiceModel.WSHttpBinding>, which provides HTTP communication and standard Web service protocols for addressing and security.</span></span> <span data-ttu-id="4e537-130">Контрактом является интерфейс `ICalculator`, реализуемый службой.</span><span class="sxs-lookup"><span data-stu-id="4e537-130">The contract is the `ICalculator` implemented by the service.</span></span>

<span data-ttu-id="4e537-131">Как настроено, доступ к службе можно получить на `http://localhost/servicemodelsamples/service.svc` клиентом на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e537-131">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="4e537-132">Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="4e537-132">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span>

<span data-ttu-id="4e537-133">По умолчанию платформа не предоставляет никаких метаданных.</span><span class="sxs-lookup"><span data-stu-id="4e537-133">The framework does not expose metadata by default.</span></span> <span data-ttu-id="4e537-134">Таким образом, служба включает <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и предоставляет конечную точку обмена метаданными (MEX) на `http://localhost/servicemodelsamples/service.svc/mex`.</span><span class="sxs-lookup"><span data-stu-id="4e537-134">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> and exposes a metadata exchange (MEX) endpoint at `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="4e537-135">Это демонстрируется в следующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e537-135">The following configuration demonstrates this.</span></span>

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

<span data-ttu-id="4e537-136">Клиент обменивается данными с использованием заданного типа контракта с помощью клиентского класса, созданного [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4e537-136">The client communicates using a given contract type by using a client class that is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="4e537-137">Этот созданный клиент содержится в файлах generatedClient.cs или generatedClient.vb.</span><span class="sxs-lookup"><span data-stu-id="4e537-137">This generated client is contained in the file generatedClient.cs or generatedClient.vb.</span></span> <span data-ttu-id="4e537-138">Это средство извлекает метаданные для заданной службы и создает клиент, который будет использоваться клиентским приложением для взаимодействия по заданному контракту.</span><span class="sxs-lookup"><span data-stu-id="4e537-138">This utility retrieves metadata for a given service and generates a client for use by the client application to communicate using a given contract type.</span></span> <span data-ttu-id="4e537-139">Размещенная служба должна быть доступна для создания кода клиента, поскольку служба используется для извлечения обновленных метаданных.</span><span class="sxs-lookup"><span data-stu-id="4e537-139">The hosted service must be available to generate the client code, because the service is used to retrieve the updated metadata.</span></span>

 <span data-ttu-id="4e537-140">Чтобы создать типизированный прокси, выполните следующую команду из командной строки SDK в каталоге клиента.</span><span class="sxs-lookup"><span data-stu-id="4e537-140">Run the following command from the SDK command prompt in the client directory to generate the typed proxy:</span></span>

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

<span data-ttu-id="4e537-141">Чтобы создать клиент на языке Visual Basic, введите следующую команду в командной строке SDK.</span><span class="sxs-lookup"><span data-stu-id="4e537-141">To generate client in Visual Basic type the following from the SDK command prompt:</span></span>

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

<span data-ttu-id="4e537-142">С помощью созданного клиента можно получить доступ к заданной конечной точке службы, настроив соответствующий адрес и привязку.</span><span class="sxs-lookup"><span data-stu-id="4e537-142">By using the generated client, the client can access a given service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="4e537-143">Как и служба, клиент использует файл конфигурации (App.config), чтобы задать конечную точку для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4e537-143">Like the service, the client uses a configuration file (App.config) to specify the endpoint with which it wants to communicate.</span></span> <span data-ttu-id="4e537-144">Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4e537-144">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following example.</span></span>

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

<span data-ttu-id="4e537-145">Реализация клиента создает клиент и использует интерфейс, чтобы начать взаимодействие со службой, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4e537-145">The client implementation instantiates the client and uses the typed interface to begin communicating with the service, as shown in the following example code.</span></span>

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

<span data-ttu-id="4e537-146">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="4e537-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4e537-147">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="4e537-147">Press ENTER in the client window to shut down the client.</span></span>

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

<span data-ttu-id="4e537-148">В образце "Начало работы" показан стандартный способ создания службы и клиента.</span><span class="sxs-lookup"><span data-stu-id="4e537-148">The Getting Started sample shows the standard way to create a service and client.</span></span> <span data-ttu-id="4e537-149">Другой [базовый](../../../../docs/framework/wcf/samples/basic-sample.md) пример сборки этого образца для демонстрации конкретных функций продукта.</span><span class="sxs-lookup"><span data-stu-id="4e537-149">The other [Basic](../../../../docs/framework/wcf/samples/basic-sample.md) build on this sample to demonstrate specific product features.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4e537-150">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="4e537-150">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="4e537-151">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4e537-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="4e537-152">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4e537-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="4e537-153">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4e537-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e537-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e537-154">See also</span></span>

- [<span data-ttu-id="4e537-155">Практическое руководство. Размещение службы WCF в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="4e537-155">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="4e537-156">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="4e537-156">How to: Host a WCF Service in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
