---
title: "Обращение к службам с использованием клиента WCF"
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
helpviewer_keywords: clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8698e0657de31d78699df478da5e716bf831fc4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-services-using-a-wcf-client"></a>Обращение к службам с использованием клиента WCF
Следующим шагом после создания службы является создание клиентского прокси-класса [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Клиентское приложение использует клиентский прокси-класс [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для взаимодействия со службой. Клиентские приложения обычно импортируют метаданные службы, чтобы создать код клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], который можно будет использовать для вызова службы.  
  
 Список основных шагов по созданию клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] включает следующие операции.  
  
1.  Скомпилируйте код службы.  
  
2.  Создайте клиентский прокси-класс [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
3.  Создайте экземпляр клиентского прокси-класса WCF.  
  
 Прокси клиента WCF можно создать вручную с помощью Service Model Metadata Utility Tool (SvcUtil.exe) дополнительная информация [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Клиентский прокси-класс WCF также можно создать в Visual Studio с помощью возможности «Добавить ссылку на службу». Для создания клиентского прокси-класса WCF любым методом выбранная служба должна быть запущена. Если служба размещается резидентно, то необходимо запустить узел. Если служба размещена на веб-сервере IIS/WAS, то больше ничего делать не нужно.  
  
## <a name="servicemodel-metadata-utility-tool"></a>Средство ServiceModel Metadata Utility Tool  
 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство командной строки для создания кода из метаданных. Ниже приведен пример базовой команды Svcutil.exe.  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 Средство Svcutil.exe можно также использовать с файлами языков WSDL (язык описания веб-служб) и XSD (язык определения схемы XML) в файловой системе.  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 В результате будет получен файл, содержащий код клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], который клиентское приложение может использовать для вызова службы.  
  
 Кроме того, с помощью этого средства можно создавать файлы конфигурации.  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 Если задано только одно имя файла, это имя выходного файла. Если задано два имени файла, то первый файл является исходным файлом конфигурации, содержимое которого объединяется с создаваемой конфигурацией и записывается во второй файл. [!INCLUDE[crabout](../../../includes/crabout-md.md)]конфигурации, в разделе [Настройка привязок для служб](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Незащищенные запросы метаданных представляют определенную угрозу, подобно незащищенным сетевым запросам. Если нет уверенности, что конечная точка, с которой осуществляется взаимодействие, является той точкой, за которую она себя выдает, получаемая информация может представлять собой метаданные вредоносной службы.  
  
## <a name="add-service-reference-in-visual-studio"></a>Функция «Добавить ссылку на службу» в Visual Studio  
 Запустив службу, щелкните правой кнопкой мыши проект, который будет содержать прокси клиента WCF и выберите **добавить ссылку на службу**. В **добавить диалоговое окно ссылок на службы** типа в URL-адрес службы, которую требуется вызвать и нажмите **Go** кнопки. В диалоговом окне отобразится список доступных служб по указанному адресу. Дважды щелкните службу, контракты и операции, доступные в разделе укажите пространство имен для сформированного кода и нажмите кнопку **ОК** кнопки.  
  
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
  
 Служебное средство ServiceModel Metadata Utility Tool и функция «Добавить ссылку на службу» в Visual Studio создают следующий клиентский класс [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Класс наследует универсальному классу <xref:System.ServiceModel.ClientBase%601> и реализует интерфейс `ICalculator`. Кроме того, это средство создает интерфейс `ICalculator` (не показан в этом примере).  
  
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
 Чтобы воспользоваться клиентом [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], создайте экземпляр клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и вызывайте его методы, как показано в следующем примере кода.  
  
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
 Многие исключения, создаваемые клиентом [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], вызываются исключениями, которые возникают на стороне службы. Ниже приведены некоторые примеры.  
  
-   <xref:System.Net.Sockets.SocketException>: существующее подключение было принудительно закрыто удаленным узлом.  
  
-   <xref:System.ServiceModel.CommunicationException>: базовое подключение было неожиданно закрыто.  
  
-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: подключение к сокету было прервано. Это может быть вызвано ошибкой при обработке сообщения, истечением времени ожидания на удаленном узле или проблемой с соответствующим сетевым ресурсом.  
  
 Если происходят исключения этих типов, лучшим решением проблемы является включение трассировки на стороне службы и определение исключения, которое там произошло. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Трассировка, в разделе [трассировки](../../../docs/framework/wcf/diagnostics/tracing/index.md) и [с помощью трассировки для устранения неполадок приложения](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Как: доступ к службам с дуплексным контрактом](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Как: асинхронный вызов операций службы](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)  
 [Как: доступ к службам с односторонним контрактом и контрактах типа запрос ответ](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)  
 [Как: доступ к WSE 3.0 службы](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)  
 [Основные сведения о созданном коде клиента](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)  
 [Как: улучшения запуска время клиентских приложений WCF с помощью класса XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)  
 [Указание поведения клиента во время выполнения](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [Настройка поведения клиентов](../../../docs/framework/wcf/configuring-client-behaviors.md)
