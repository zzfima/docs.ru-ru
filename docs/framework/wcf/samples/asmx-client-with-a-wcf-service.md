---
title: Клиент ASMX со службой WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: a560650dba250d1ee4f0b959ead70a2915c9997f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716142"
---
# <a name="asmx-client-with-a-wcf-service"></a><span data-ttu-id="0e9eb-102">Клиент ASMX со службой WCF</span><span class="sxs-lookup"><span data-stu-id="0e9eb-102">ASMX Client with a WCF Service</span></span>

<span data-ttu-id="0e9eb-103">В этом примере показано, как создать службу с помощью Windows Communication Foundation (WCF), а затем получить доступ к службе из клиента, не являющегося клиентом WCF, например клиента ASMX.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-103">This sample demonstrates how to create a service using Windows Communication Foundation (WCF) and then access the service from a non-WCF client, such as an ASMX client.</span></span>

> [!NOTE]
> <span data-ttu-id="0e9eb-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="0e9eb-105">Этот образец содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-105">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="0e9eb-106">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="0e9eb-106">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="0e9eb-107">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (`Add`, `Subtract`, `Multiply` и `Divide`).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="0e9eb-108">Клиент ASMX осуществляет синхронные вызовы математической операции, а служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-108">The ASMX client makes synchronous requests to a math operation and the service replies with the result.</span></span>

<span data-ttu-id="0e9eb-109">Служба реализует контракт `ICalculator`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-109">The service implements an `ICalculator` contract as defined in the following code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
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

<span data-ttu-id="0e9eb-110">Объекты <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Xml.Serialization.XmlSerializer> сопоставляют типы среды CLR с XML-представлением.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-110">The <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Xml.Serialization.XmlSerializer> map CLR types to an XML representation.</span></span> <span data-ttu-id="0e9eb-111"><xref:System.Runtime.Serialization.DataContractSerializer> интерпретирует некоторые XML-представления не так, как XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-111">The <xref:System.Runtime.Serialization.DataContractSerializer> interprets some XML representations differently than XmlSerializer.</span></span> <span data-ttu-id="0e9eb-112">Генераторы прокси, отличные от WCF, такие как WSDL. exe, создают более подходящий интерфейс при использовании XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-112">Non-WCF proxy generators, such as Wsdl.exe, generate a more usable interface when the XmlSerializer is being used.</span></span> <span data-ttu-id="0e9eb-113"><xref:System.ServiceModel.XmlSerializerFormatAttribute> применяется к интерфейсу `ICalculator`, чтобы убедиться, что XmlSerializer используется для сопоставления типов CLR с XML.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> is applied to the `ICalculator` interface, to ensure that the XmlSerializer is used for mapping CLR types to XML.</span></span> <span data-ttu-id="0e9eb-114">Реализация службы выполняет вычисления и возвращает соответствующий результат.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-114">The service implementation calculates and returns the appropriate result.</span></span>

<span data-ttu-id="0e9eb-115">Служба предоставляет одну конечную точку для взаимодействия с ней; конечная точка определяется в файле конфигурации (Web.config).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-115">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="0e9eb-116">Конечная точка состоит из адреса, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="0e9eb-117">Служба предоставляет конечную точку по базовому адресу, предоставляемую узлом IIS.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-117">The service exposes the endpoint at the base address provided by the Internet Information Services (IIS) host.</span></span> <span data-ttu-id="0e9eb-118">Для атрибута `binding` задается значение basicHttpBinding, что обеспечивает взаимодействие по протоколу HTTP с использованием протокола SOAP 1.1, который совместим со спецификацией WS-I BasicProfile 1.1, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-118">The `binding` attribute is set to basicHttpBinding that provides HTTP communications using SOAP 1.1, which is compliant with WS-I BasicProfile 1.1 as shown in the following sample configuration.</span></span>

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

<span data-ttu-id="0e9eb-119">Клиент ASMX взаимодействует со службой WCF с помощью типизированного прокси-сервера, созданного служебной программой языка описания веб-служб (WSDL. exe).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-119">The ASMX client communicates with the WCF service using a typed proxy that is generated by the Web Services Description Language (WSDL) utility (Wsdl.exe).</span></span> <span data-ttu-id="0e9eb-120">Типизированный прокси содержится в файле generatedClient.cs.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-120">The typed proxy is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="0e9eb-121">Специальная программа WSDL извлекает метаданные для заданной службы и создает типизированный прокси, который будет использоваться клиентом для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-121">The WSDL utility retrieves metadata for the specified service and generates a typed proxy for use by a client to communicate.</span></span> <span data-ttu-id="0e9eb-122">По умолчанию платформа не предоставляет никаких метаданных.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-122">By default, the framework does not expose any metadata.</span></span> <span data-ttu-id="0e9eb-123">Чтобы предоставить метаданные, необходимые для создания прокси-сервера, необходимо добавить [\<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) и задать для атрибута `httpGetEnabled` значение `True`, как показано в следующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-123">To expose the metadata required to generate the proxy, you must add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) and set its `httpGetEnabled` attribute to `True` as shown in the following configuration.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="0e9eb-124">Чтобы создать типизированную учетную запись-посредник, выполните следующую команду из командной строки в каталоге клиента.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-124">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

<span data-ttu-id="0e9eb-125">С помощью созданного типизированного прокси клиент может обращаться к заданной конечной точке службы путем задания в конфигурации соответствующего адреса.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-125">By using the generated typed proxy, the client can access a given service endpoint by configuring the appropriate address.</span></span> <span data-ttu-id="0e9eb-126">Чтобы задать конечную точку для взаимодействия, клиент использует файл конфигурации (App.config).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-126">The client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span>

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

<span data-ttu-id="0e9eb-127">Реализация клиента создает экземпляр типизированного прокси, чтобы начать взаимодействие со службой.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-127">The client implementation constructs an instance of the typed proxy to begin communicating with the service.</span></span>

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
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

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="0e9eb-128">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0e9eb-129">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-129">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0e9eb-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="0e9eb-130">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="0e9eb-131">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="0e9eb-132">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="0e9eb-133">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0e9eb-134">Дополнительные сведения о передаче и возврате сложных типов данных см. в разделе [Привязка данных в Windows Formsном клиенте](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [привязка данных в Windows Presentation Foundationном клиенте](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md)и [привязка данных в клиенте ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md) .</span><span class="sxs-lookup"><span data-stu-id="0e9eb-134">For more information about passing and returning complex data types see: [Data Binding in a Windows Forms Client](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Data Binding in a Windows Presentation Foundation Client](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), and [Data Binding in an ASP.NET Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e9eb-135">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0e9eb-136">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0e9eb-136">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="0e9eb-137">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e9eb-138">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0e9eb-138">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
