---
title: Обращение к службам с использованием клиента WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 6bf683cdd0a03a5d1dbc452c28e7b33911464f09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297256"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="fa8e4-102">Обращение к службам с использованием клиента WCF</span><span class="sxs-lookup"><span data-stu-id="fa8e4-102">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="fa8e4-103">После создания службы, следующим шагом является создание клиента WCF-прокси.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-103">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="fa8e4-104">Клиентское приложение использует прокси клиента WCF для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-104">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="fa8e4-105">Клиентские приложения обычно импортируют метаданные службы для создания кода клиента WCF, который может использоваться для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-105">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="fa8e4-106">Ниже приведены основные шаги для создания клиента WCF:</span><span class="sxs-lookup"><span data-stu-id="fa8e4-106">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="fa8e4-107">Скомпилируйте код службы.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-107">Compile the service code.</span></span>

2. <span data-ttu-id="fa8e4-108">Создайте прокси клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-108">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="fa8e4-109">Создайте экземпляр клиентского прокси-класса WCF.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-109">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="fa8e4-110">Клиентский прокси WCF можно создать вручную с помощью Service Model Metadata Utility Tool (SvcUtil.exe) Дополнительные сведения см. [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fa8e4-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="fa8e4-111">Клиентский прокси WCF также может возникать в Visual Studio с помощью **Add Service Reference** функции.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-111">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="fa8e4-112">Для создания клиентского прокси-класса WCF любым методом выбранная служба должна быть запущена.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="fa8e4-113">Если служба размещается резидентно, то необходимо запустить узел.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="fa8e4-114">Если служба размещена на веб-сервере IIS/WAS, то больше ничего делать не нужно.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="fa8e4-115">Средство ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="fa8e4-115">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="fa8e4-116">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) является средством командной строки для создания кода из метаданных.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="fa8e4-117">Ниже приведен пример базовой команды Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-117">The following use is an example of a basic Svcutil.exe command.</span></span>

```
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="fa8e4-118">Средство Svcutil.exe можно также использовать с файлами языков WSDL (язык описания веб-служб) и XSD (язык определения схемы XML) в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="fa8e4-119">Результатом является файл кода, содержащий код клиента WCF, который клиентское приложение может использовать для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-119">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="fa8e4-120">Кроме того, с помощью этого средства можно создавать файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-120">You can also use the tool to generate configuration files.</span></span>

```
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="fa8e4-121">Если задано только одно имя файла, это имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="fa8e4-122">Если задано два имени файла, то первый файл является исходным файлом конфигурации, содержимое которого объединяется с создаваемой конфигурацией и записывается во второй файл.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="fa8e4-123">Дополнительные сведения о конфигурации см. в разделе [Настройка привязок для служб](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="fa8e4-123">For more information about configuration, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa8e4-124">Незащищенные запросы метаданных представляют определенную угрозу таким же образом, любой незащищенным сетевым запросам: Если вы не уверены в конечную точку, взаимодействующие с говорит, что это, можно извлечь данные могут быть метаданные вредоносной службы.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="fa8e4-125">Функция «Добавить ссылку на службу» в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa8e4-125">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="fa8e4-126">Запустив службу, щелкните правой кнопкой мыши проект, который будет содержать клиентский прокси WCF и выберите **добавить** > **ссылки на службу**.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-126">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="fa8e4-127">В **Добавление диалога ссылки на службу**, введите URL-адрес для службы, которую требуется вызвать и нажмите **Go** кнопки.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-127">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="fa8e4-128">В диалоговом окне отобразится список доступных служб по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="fa8e4-129">Дважды щелкните службу, см. в разделе контрактов и операций, доступных и указать пространство имен для сформированного кода щелкните **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="fa8e4-130">Пример</span><span class="sxs-lookup"><span data-stu-id="fa8e4-130">Example</span></span>
 <span data-ttu-id="fa8e4-131">В следующем примере кода показан созданный контракт службы.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-131">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="fa8e4-132">Средство ServiceModel Metadata служебной программы и **Add Service Reference** в Visual Studio создает класс клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-132">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="fa8e4-133">Класс наследует универсальному классу <xref:System.ServiceModel.ClientBase%601> и реализует интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="fa8e4-134">Кроме того, это средство создает интерфейс `ICalculator` (не показан в этом примере).</span><span class="sxs-lookup"><span data-stu-id="fa8e4-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="fa8e4-135">Использование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="fa8e4-135">Using the WCF Client</span></span>
 <span data-ttu-id="fa8e4-136">Использование клиента WCF, создайте экземпляр клиента WCF и затем вызывать его методы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-136">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="fa8e4-137">Отладка создаваемых клиентом исключений</span><span class="sxs-lookup"><span data-stu-id="fa8e4-137">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="fa8e4-138">Многие исключения, создаваемые клиента WCF, вызваны исключения в службе.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-138">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="fa8e4-139">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-139">Some examples of this are:</span></span>

-   <span data-ttu-id="fa8e4-140"><xref:System.Net.Sockets.SocketException>: Существующее соединение было принудительно закрыто удаленным узлом.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-140"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

-   <span data-ttu-id="fa8e4-141"><xref:System.ServiceModel.CommunicationException>: Базовое подключение было неожиданно закрыто.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-141"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

-   <span data-ttu-id="fa8e4-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: Подключение через сокет прервано.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="fa8e4-143">Это может быть вызвано ошибкой при обработке сообщения, истечением времени ожидания на удаленном узле или проблемой с соответствующим сетевым ресурсом.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="fa8e4-144">Если происходят исключения этих типов, лучшим решением проблемы является включение трассировки на стороне службы и определение исключения, которое там произошло.</span><span class="sxs-lookup"><span data-stu-id="fa8e4-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="fa8e4-145">Дополнительные сведения о трассировке см. в разделе [трассировки](../../../docs/framework/wcf/diagnostics/tracing/index.md) и [с помощью трассировки для устранения неполадок приложения](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="fa8e4-145">For more information about tracing, see [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa8e4-146">См. также</span><span class="sxs-lookup"><span data-stu-id="fa8e4-146">See also</span></span>

- [<span data-ttu-id="fa8e4-147">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="fa8e4-147">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="fa8e4-148">Практическое руководство. Службы доступа с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="fa8e4-148">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="fa8e4-149">Практическое руководство. Асинхронный вызов операций службы</span><span class="sxs-lookup"><span data-stu-id="fa8e4-149">How to: Call Service Operations Asynchronously</span></span>](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="fa8e4-150">Практическое руководство. Доступ к службам с односторонним контрактом и контрактом типа запрос ответ</span><span class="sxs-lookup"><span data-stu-id="fa8e4-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="fa8e4-151">Практическое руководство. Доступ к WSE 3.0 служба</span><span class="sxs-lookup"><span data-stu-id="fa8e4-151">How to: Access a WSE 3.0 Service</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="fa8e4-152">Основные сведения о созданном коде клиента</span><span class="sxs-lookup"><span data-stu-id="fa8e4-152">Understanding Generated Client Code</span></span>](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="fa8e4-153">Практическое руководство. Улучшения запуска время клиентских приложений WCF с использованием XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="fa8e4-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="fa8e4-154">Указание поведения клиента во время выполнения</span><span class="sxs-lookup"><span data-stu-id="fa8e4-154">Specifying Client Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="fa8e4-155">Настройка поведения клиентов</span><span class="sxs-lookup"><span data-stu-id="fa8e4-155">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
