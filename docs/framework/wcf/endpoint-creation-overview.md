---
title: "Общие сведения о создании конечных точек"
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
helpviewer_keywords: endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa20edd8fa43fb1e6a28f7b1ec18f83fedd96bca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-creation-overview"></a>Общие сведения о создании конечных точек
Вся связь со [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] службы осуществляется с помощью *конечные точки* службы. Конечные точки обеспечивают доступ клиентов к функциональным возможностям службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. В данном разделе приводится описание структуры конечной точки и способов определения конечной точки в конфигурации и в коде.  
  
## <a name="the-structure-of-an-endpoint"></a>Структура конечной точки  
 Каждая конечная точка содержит адрес, показывающий, где можно найти конечную точку, привязку, показывающую, как клиент может связаться с конечной точкой, и контракт, определяющий доступные методы.  
  
-   **Адрес**. Адрес однозначно определяет конечную точку и указывает потенциальным потребителям на место расположения службы. Он представлен в объектной модели [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] адресом <xref:System.ServiceModel.EndpointAddress>, содержащим универсальный код ресурса (URI) и свойства адреса, включающие идентификацию, некоторые элементы языка описания веб-служб (WSDL) и коллекцию необязательных заголовков. Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Задание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   **Привязка**. Привязка задает способ связи клиента с конечной точкой. Привязка задает способ связи конечной точки с внешним миром, включая используемый транспортный протокол (например, TCP или HTTP), используемое кодирование сообщений (например, текстовое или двоичное) и необходимые требования безопасности (например, безопасность сообщений SSL или SOAP). [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
-   **Контракт службы**. Контракт службы показывает, какие функциональные возможности предоставляет клиенту конечная точка. Контракт указывает операции, которые может вызвать клиент, форму сообщения и тип входных параметров или данных, требуемых для вызова операции, а также тип обработки или ответного сообщения, которые может ожидать клиент. Три базовых типа контрактов соответствуют базовым шаблонам обмена сообщениями (MEP): датаграмма (односторонняя связь), запрос-ответ и дуплексная связь (двунаправленная). Контракт службы также может задействовать контракты данных и контракты сообщений, чтобы при обращении требовались определенные типы данных и форматы сообщений. [!INCLUDE[crabout](../../../includes/crabout-md.md)]как определить контракт службы см. в разделе [проектирование контрактов службы](../../../docs/framework/wcf/designing-service-contracts.md). Обратите внимание, что клиент также может потребоваться для реализации определяемого службой контракта, называемого контрактом обратного вызова, чтобы получить сообщения от службы в дуплексном шаблоне обмена сообщениями. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Дуплексные службы](../../../docs/framework/wcf/feature-details/duplex-services.md).  
  
 Конечную точку службы можно задать императивно с помощью кода или декларативно с помощью конфигурации. Если конечные точки не заданы, то среда выполнения предоставляет конечные точки по умолчанию, добавляя одну конечную точку по умолчанию для каждого базового адреса в каждом контракте службы, реализованном в службе. Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы. Обычно более целесообразно задать конечные точки службы в конфигурации, а не в коде. Если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции и повторного развертывания приложения.  
  
> [!NOTE]
>  При добавлении конечной точки службы, выполняющей олицетворение, необходимо использовать либо один из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>, либо метод <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29>, чтобы правильно загрузить контракт в новый объект <xref:System.ServiceModel.Description.ServiceDescription>.  
  
## <a name="defining-endpoints-in-code"></a>Определение конечных точек в коде  
 В следующем примере показано, как задать конечную точку в коде.  
  
-   Определите контракт для `IEcho` тип службы, который принимает имя и выведите на экран с ответом, чей «Hello \<имя >!».  
  
-   Реализуйте службу `Echo` типа, определенного контрактом `IEcho`.  
  
-   Задайте адрес конечной точки для службы: http://localhost:8000/Echo.  
  
-   Настройте службу `Echo` с помощью привязки <xref:System.ServiceModel.WSHttpBinding>.  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  Узел службы создается с базовым адресом, а затем остальная часть адреса, относящаяся к базовому адресу, задается как часть конечной точки. Такое секционирование адреса обеспечивает более удобное определение нескольких конечных точек для служб в узле.  
  
> [!NOTE]
>  Свойства объекта <xref:System.ServiceModel.Description.ServiceDescription> в приложении службы нельзя изменять после вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> для объекта <xref:System.ServiceModel.ServiceHostBase>. Некоторые члены, такие как свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> и методы `AddServiceEndpoint` для объектов <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.ServiceHost>, создают исключение, если их изменить на этом этапе. Другие члены можно изменять без появления исключения, но результат при этом будет неопределенным.  
>   
>  Аналогично, на стороне клиента нельзя изменять значения <xref:System.ServiceModel.Description.ServiceEndpoint> после вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> для объекта <xref:System.ServiceModel.ChannelFactory>. Если после этого изменить свойство <xref:System.ServiceModel.ChannelFactory.Credentials%2A>, создается исключение. Изменение других значений описания клиента происходит без ошибок, но результат изменения в этом случае является неопределенным.  
>   
>  Как для службы, так и для клиента, рекомендуется изменять описание до вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.  
  
## <a name="defining-endpoints-in-configuration"></a>Определение конечных точек в конфигурации  
 При создании приложения часто нужно отложить решения для администратора, который выполняет развертывание приложения. Например, часто невозможно узнать заранее, каким будет адрес службы (универсальный код ресурса (URI)). Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы. Такая гибкость достигается благодаря конфигурации. Дополнительные сведения см. в разделе [Настройка службы](../../../docs/framework/wcf/configuring-services.md).  
  
> [!NOTE]
>  Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с `/config:` *filename*`[,`*filename* `]` переключиться в Быстрое создание файлов конфигурации.  
  
## <a name="using-default-endpoints"></a>Использование конечных точек по умолчанию  
 Если конечные точки не заданы в коде или в конфигурации, то среда выполнения создает конечные точки по умолчанию, добавляя одну конечную точку по умолчанию для каждого базового адреса в каждом контракте службы, реализованном в службе. Базовый адрес можно указывать в коде или в конфигурации, а конечные точки по умолчанию добавляются, когда вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open> в объекте <xref:System.ServiceModel.ServiceHost>. Этот пример аналогичен примеру из предыдущего раздела, однако конечные точки не указаны, и поэтому добавляются конечные точки по умолчанию.  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 Если конечные точки предоставляются явно, то конечные точки по умолчанию можно добавить, вызвав метод <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> класса <xref:System.ServiceModel.ServiceHost> перед вызовом <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. [!INCLUDE[crabout](../../../includes/crabout-md.md)]конечные точки по умолчанию см. в разделе [упрощенной конфигурации](../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>См. также  
 [Реализация контрактов служб](../../../docs/framework/wcf/implementing-service-contracts.md)
