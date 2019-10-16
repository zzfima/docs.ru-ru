---
title: Обращение к службам с использованием клиента WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 462d9a3923009f0124c2b90b6fa86dfa9869a3c5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72316533"
---
# <a name="accessing-services-using-a-wcf-client"></a>Обращение к службам с использованием клиента WCF

После создания службы следующим шагом является создание прокси клиента WCF. Клиентское приложение использует клиентский прокси-сервер WCF для взаимодействия со службой. Клиентские приложения обычно импортируют метаданные службы для создания клиентского кода WCF, который можно использовать для вызова службы.

 Ниже приведены основные шаги для создания клиента WCF.

1. Скомпилируйте код службы.

2. Создайте прокси клиента WCF.

3. Создайте экземпляр клиентского прокси-класса WCF.

Прокси-сервер клиента WCF можно создать вручную с помощью служебной программы метаданных модели службы (SvcUtil. exe). Дополнительные сведения см. в разделе [средство служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md). Клиентский прокси-сервер WCF также может быть создан в Visual Studio с помощью функции **Добавление ссылки на службу** . Для создания клиентского прокси-класса WCF любым методом выбранная служба должна быть запущена. Если служба размещается резидентно, то необходимо запустить узел. Если служба размещена на веб-сервере IIS/WAS, то больше ничего делать не нужно.

## <a name="servicemodel-metadata-utility-tool"></a>Средство ServiceModel Metadata Utility Tool
 [Средство служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) — это программа командной строки для создания кода из метаданных. Ниже приведен пример базовой команды Svcutil.exe.

```console
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 Средство Svcutil.exe можно также использовать с файлами языков WSDL (язык описания веб-служб) и XSD (язык определения схемы XML) в файловой системе.

```console
Svcutil.exe <list of WSDL and XSD files on file system>
```

 Результатом является файл кода, содержащий клиентский код WCF, который клиентское приложение может использовать для вызова службы.

 Кроме того, с помощью этого средства можно создавать файлы конфигурации.

```console
Svcutil.exe <file1 [,file2]>
```

 Если задано только одно имя файла, это имя выходного файла. Если задано два имени файла, то первый файл является исходным файлом конфигурации, содержимое которого объединяется с создаваемой конфигурацией и записывается во второй файл. Дополнительные сведения о конфигурации см. в разделе [Настройка привязок для служб](configuring-bindings-for-wcf-services.md).

> [!IMPORTANT]
> Незащищенные запросы метаданных представляют определенную угрозу, подобно незащищенным сетевым запросам. Если нет уверенности, что конечная точка, с которой осуществляется взаимодействие, является той точкой, за которую она себя выдает, получаемая информация может представлять собой метаданные вредоносной службы.

## <a name="add-service-reference-in-visual-studio"></a>Функция «Добавить ссылку на службу» в Visual Studio

 После запуска службы щелкните правой кнопкой мыши проект, который будет содержать прокси клиента WCF, и выберите пункт **Добавить** **ссылку на службу** > . В **диалоговом окне Добавление ссылки на службу**введите URL-адрес службы, которую необходимо вызвать, и нажмите кнопку **Go (переход** ). В диалоговом окне отобразится список доступных служб по указанному адресу. Дважды щелкните службу, чтобы просмотреть доступные контракты и операции, укажите пространство имен для созданного кода и нажмите кнопку **ОК** .

## <a name="example"></a>Пример
 В следующем примере кода показан созданный контракт службы.

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

 Средство служебной программы для метаданных ServiceModel и **Добавление ссылки на службу** в Visual Studio создает следующий класс клиента WCF. Класс наследует универсальному классу <xref:System.ServiceModel.ClientBase%601> и реализует интерфейс `ICalculator`. Кроме того, это средство создает интерфейс `ICalculator` (не показан в этом примере).

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

## <a name="using-the-wcf-client"></a>Использование клиента WCF
 Чтобы использовать клиент WCF, создайте экземпляр клиента WCF, а затем вызовите его методы, как показано в следующем коде.

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

## <a name="debugging-exceptions-thrown-by-a-client"></a>Отладка создаваемых клиентом исключений

Многие исключения, вызванные клиентом WCF, вызваны исключением в службе. Ниже приведены некоторые примеры.

- <xref:System.Net.Sockets.SocketException>: существующее подключение было принудительно закрыто удаленным узлом.

- <xref:System.ServiceModel.CommunicationException>: базовое подключение было неожиданно закрыто.

- <xref:System.ServiceModel.CommunicationObjectAbortedException>: подключение к сокету было прервано. Это может быть вызвано ошибкой при обработке сообщения, истечением времени ожидания на удаленном узле или проблемой с соответствующим сетевым ресурсом.

Если происходят исключения этих типов, лучшим решением проблемы является включение трассировки на стороне службы и определение исключения, которое там произошло. Дополнительные сведения о трассировке см. в разделе [Трассировка](./diagnostics/tracing/index.md) и [Использование трассировки для устранения неполадок в приложении](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="see-also"></a>См. также

- [Практическое руководство. Создание клиента](how-to-create-a-wcf-client.md)
- [Практическое руководство. Доступ к службам с дуплексным контрактом](./feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Практическое руководство. Асинхронный вызов операций службы](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [Практическое руководство. Доступ к службам с односторонним контрактом и контрактом типа "запрос-ответ"](./feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [Практическое руководство. Доступ к службе WSE 3.0](./feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [Основные сведения о созданном коде клиента](./feature-details/understanding-generated-client-code.md)
- [Практическое руководство. Сокращение времени запуска клиентских приложений WCF с использованием XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [Указание поведения клиента во время выполнения](specifying-client-run-time-behavior.md)
- [Настройка поведения клиентов](configuring-client-behaviors.md)
