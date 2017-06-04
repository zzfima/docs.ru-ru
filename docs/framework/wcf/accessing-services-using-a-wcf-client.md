---
title: "Обращение к службам с использованием клиента WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "клиенты [WCF], использование служб"
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Обращение к службам с использованием клиента WCF
Следующим шагом после создания службы является создание клиентского прокси\-класса [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Клиентское приложение использует клиентский прокси\-класс [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для взаимодействия со службой.  Клиентские приложения обычно импортируют метаданные службы, чтобы создать код клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], который можно будет использовать для вызова службы.  
  
 Список основных шагов по созданию клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] включает следующие операции.  
  
1.  Скомпилируйте код службы.  
  
2.  Создайте клиентский прокси\-класс [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
3.  Создайте экземпляр клиентского прокси\-класса WCF.  
  
 Клиентский прокси\-класс WCF можно создать вручную с помощью программы метаданных модели службы \(SvcUtil.exe\). Дополнительные сведения см. в разделе [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  Клиентский прокси\-класс WCF также можно создать в Visual Studio с помощью функции «Добавить ссылку на службу».  Для создания клиентского прокси\-класса WCF любым методом выбранная служба должна быть запущена.  Если служба размещается резидентно, то необходимо запустить узел.  Если служба размещена на веб\-сервере IIS\/WAS, то больше ничего делать не нужно.  
  
## Средство ServiceModel Metadata Utility Tool  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) \- это программа командной строки, предназначенная для создания кода на основе метаданных.  Ниже приведен пример базовой команды Svcutil.exe.  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 Средство Svcutil.exe можно также использовать с файлами языков WSDL \(язык описания веб\-служб\) и XSD \(язык определения схемы XML\) в файловой системе.  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 В результате будет получен файл, содержащий код клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], который клиентское приложение может использовать для вызова службы.  
  
 Кроме того, с помощью этого средства можно создавать файлы конфигурации.  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 Если задано только одно имя файла, это имя выходного файла.  Если задано два имени файла, то первый файл является исходным файлом конфигурации, содержимое которого объединяется с создаваемой конфигурацией и записывается во второй файл.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] конфигурации см. в разделе [Настройка привязок для служб](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Незащищенные запросы метаданных представляют определенную угрозу, подобно незащищенным сетевым запросам. Если нет уверенности, что конечная точка, с которой осуществляется взаимодействие, является той точкой, за которую она себя выдает, получаемая информация может представлять собой метаданные вредоносной службы.  
  
## Функция «Добавить ссылку на службу» в Visual Studio  
 Запустив службу, щелкните правой кнопкой мыши проект, который будет содержать клиентский прокси\-класс WCF, и выберите пункт **Добавить ссылку на службу**.  В диалоговом окне **Добавление ссылки на службу** введите URL\-адрес службы, которую необходимо вызвать, и нажмите кнопку **Перейти**.  В диалоговом окне отобразится список доступных служб по указанному адресу.  Дважды щелкните службу, чтобы увидеть доступные для нее контракты и операции, задайте пространство имен для формируемого кода, а затем нажмите кнопку **ОК**.  
  
## Пример  
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
<ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")> _  
Public Interface ICalculator  
    <OperationContract()>  _  
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double   
    ' Other methods are not shown here.  
End Interface   
```  
  
 Служебное средство ServiceModel Metadata Utility Tool и функция «Добавить ссылку на службу» в Visual Studio создают следующий клиентский класс [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Класс наследует универсальному классу <xref:System.ServiceModel.ClientBase%601> и реализует интерфейс `ICalculator`.  Кроме того, это средство создает интерфейс `ICalculator` \(не показан в этом примере\).  
  
```csharp  
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator  
{  
    public CalculatorClient(){}  
  
    public CalculatorClient(string configurationName) :   
            base(configurationName)  
    {}  
  
    public CalculatorClient(System.ServiceModel.Binding binding) :   
            base(binding)  
    {}  
  
    public CalculatorClient(System.ServiceModel.EndpointAddress address,  
    System.ServiceModel.Binding binding) :   
            base(address, binding)  
    {}  
  
    public double Add(double n1, double n2)  
    {  
        return base.InnerChannel.Add(n1, n2);  
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
  
    Public Sub New(ByVal configurationName As String)  
        MyBase.New(configurationName)  
    End Sub  
  
    Public Sub New(ByVal binding As System.ServiceModel.Binding)  
        MyBase.New(binding)  
    End Sub  
  
    Public Sub New(ByVal address As _  
    System.ServiceModel.EndpointAddress, _  
    ByVal binding As System.ServiceModel.Binding)  
        MyBase.New(address, binding)  
    End Sub  
  
    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As _  
    Double Implements ICalculator.Add  
        Return MyBase.InnerChannel.Add(n1, n2)  
    End Function   
End Class  
  
```  
  
## Использование клиента WCF  
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
  
## Отладка создаваемых клиентом исключений  
 Многие исключения, создаваемые клиентом [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], вызываются исключениями, которые возникают на стороне службы.  Ниже приведены некоторые примеры.  
  
-   <xref:System.Net.Sockets.SocketException>: существующее подключение было принудительно закрыто удаленным узлом.  
  
-   <xref:System.ServiceModel.CommunicationException>: базовое подключение было неожиданно закрыто.  
  
-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: подключение к сокету было прервано.  Это может быть вызвано ошибкой при обработке сообщения, истечением времени ожидания на удаленном узле или проблемой с соответствующим сетевым ресурсом.  
  
 Если происходят исключения этих типов, лучшим решением проблемы является включение трассировки на стороне службы и определение исключения, которое там произошло.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] трассировке WCF см. в разделах [Трассировка](../../../docs/framework/wcf/diagnostics/tracing/index.md) и [Использование трассировки для устранения неполадок приложения](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
## См. также  
 [Как создать клиент](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Практическое руководство. Доступ к службам с дуплексным контрактом](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)   
 [Как асинхронно вызывать операции службы](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)   
 [Практическое руководство. Доступ к службам с односторонним контрактом и контрактом типа «запрос\-ответ»](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)   
 [Как обращаться к службе WSE 3.0](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)   
 [Основные сведения о созданном коде клиента](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)   
 [Как сократить время запуска клиентских приложений WCF с использованием XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)   
 [Задание поведения клиента во время выполнения](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)   
 [Настройка поведений клиентов](../../../docs/framework/wcf/configuring-client-behaviors.md)