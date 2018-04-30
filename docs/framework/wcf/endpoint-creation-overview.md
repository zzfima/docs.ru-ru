---
title: Общие сведения о создании конечных точек
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
caps.latest.revision: 40
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3317bc47c03e0b100d094ba1d929a003dddab055
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="d771f-102">Общие сведения о создании конечных точек</span><span class="sxs-lookup"><span data-stu-id="d771f-102">Endpoint Creation Overview</span></span>
<span data-ttu-id="d771f-103">Вся связь со [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] службы осуществляется с помощью *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="d771f-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="d771f-104">Конечные точки обеспечивают доступ клиентов к функциональным возможностям службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d771f-104">Endpoints provide the clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span> <span data-ttu-id="d771f-105">В данном разделе приводится описание структуры конечной точки и способов определения конечной точки в конфигурации и в коде.</span><span class="sxs-lookup"><span data-stu-id="d771f-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="d771f-106">Структура конечной точки</span><span class="sxs-lookup"><span data-stu-id="d771f-106">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="d771f-107">Каждая конечная точка содержит адрес, показывающий, где можно найти конечную точку, привязку, показывающую, как клиент может связаться с конечной точкой, и контракт, определяющий доступные методы.</span><span class="sxs-lookup"><span data-stu-id="d771f-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>  
  
-   <span data-ttu-id="d771f-108">**Адрес**.</span><span class="sxs-lookup"><span data-stu-id="d771f-108">**Address**.</span></span> <span data-ttu-id="d771f-109">Адрес однозначно определяет конечную точку и указывает потенциальным потребителям на место расположения службы.</span><span class="sxs-lookup"><span data-stu-id="d771f-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="d771f-110">Он представлен в объектной модели [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] адресом <xref:System.ServiceModel.EndpointAddress>, содержащим универсальный код ресурса (URI) и свойства адреса, включающие идентификацию, некоторые элементы языка описания веб-служб (WSDL) и коллекцию необязательных заголовков.</span><span class="sxs-lookup"><span data-stu-id="d771f-110">It is represented in the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="d771f-111">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="d771f-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="d771f-112">Дополнительные сведения см. в разделе [Задание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="d771f-112">For more information, see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="d771f-113">**Привязка**.</span><span class="sxs-lookup"><span data-stu-id="d771f-113">**Binding**.</span></span> <span data-ttu-id="d771f-114">Привязка задает способ связи клиента с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="d771f-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="d771f-115">Привязка задает способ связи конечной точки с внешним миром, включая используемый транспортный протокол (например, TCP или HTTP), используемое кодирование сообщений (например, текстовое или двоичное) и необходимые требования безопасности (например, безопасность сообщений SSL или SOAP).</span><span class="sxs-lookup"><span data-stu-id="d771f-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="d771f-116">Дополнительные сведения см. в разделе [с помощью привязок для настройки службы и клиенты](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d771f-116">For more information, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
-   <span data-ttu-id="d771f-117">**Контракт службы**.</span><span class="sxs-lookup"><span data-stu-id="d771f-117">**Service contract**.</span></span> <span data-ttu-id="d771f-118">Контракт службы показывает, какие функциональные возможности предоставляет клиенту конечная точка.</span><span class="sxs-lookup"><span data-stu-id="d771f-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="d771f-119">Контракт указывает операции, которые может вызвать клиент, форму сообщения и тип входных параметров или данных, требуемых для вызова операции, а также тип обработки или ответного сообщения, которые может ожидать клиент.</span><span class="sxs-lookup"><span data-stu-id="d771f-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="d771f-120">Три базовых типа контрактов соответствуют базовым шаблонам обмена сообщениями (MEP): датаграмма (односторонняя связь), запрос-ответ и дуплексная связь (двунаправленная).</span><span class="sxs-lookup"><span data-stu-id="d771f-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="d771f-121">Контракт службы также может задействовать контракты данных и контракты сообщений, чтобы при обращении требовались определенные типы данных и форматы сообщений.</span><span class="sxs-lookup"><span data-stu-id="d771f-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="d771f-122">Дополнительные сведения о том, как определить контракт службы см. в разделе [проектирование контрактов службы](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="d771f-122">For more information about how to define a service contract, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="d771f-123">Обратите внимание, что клиент также может потребоваться для реализации определяемого службой контракта, называемого контрактом обратного вызова, чтобы получить сообщения от службы в дуплексном шаблоне обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d771f-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="d771f-124">Дополнительные сведения см. в разделе [дуплексные службы](../../../docs/framework/wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="d771f-124">For more information, see [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="d771f-125">Конечную точку службы можно задать императивно с помощью кода или декларативно с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d771f-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="d771f-126">Если конечные точки не заданы, то среда выполнения предоставляет конечные точки по умолчанию, добавляя одну конечную точку по умолчанию для каждого базового адреса в каждом контракте службы, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="d771f-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="d771f-127">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="d771f-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="d771f-128">Обычно более целесообразно задать конечные точки службы в конфигурации, а не в коде.</span><span class="sxs-lookup"><span data-stu-id="d771f-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="d771f-129">Если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции и повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="d771f-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d771f-130">При добавлении конечной точки службы, выполняющей олицетворение, необходимо использовать либо один из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>, либо метод <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29>, чтобы правильно загрузить контракт в новый объект <xref:System.ServiceModel.Description.ServiceDescription>.</span><span class="sxs-lookup"><span data-stu-id="d771f-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>  
  
## <a name="defining-endpoints-in-code"></a><span data-ttu-id="d771f-131">Определение конечных точек в коде</span><span class="sxs-lookup"><span data-stu-id="d771f-131">Defining Endpoints in Code</span></span>  
 <span data-ttu-id="d771f-132">В следующем примере показано, как задать конечную точку в коде.</span><span class="sxs-lookup"><span data-stu-id="d771f-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>  
  
-   <span data-ttu-id="d771f-133">Определите контракт для `IEcho` тип службы, который принимает имя и выведите на экран с ответом, чей «Hello \<имя >!».</span><span class="sxs-lookup"><span data-stu-id="d771f-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>  
  
-   <span data-ttu-id="d771f-134">Реализуйте службу `Echo` типа, определенного контрактом `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="d771f-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>  
  
-   <span data-ttu-id="d771f-135">Укажите адрес конечной точки http://localhost:8000/Echo для службы.</span><span class="sxs-lookup"><span data-stu-id="d771f-135">Specify an endpoint address of http://localhost:8000/Echo for the service.</span></span>  
  
-   <span data-ttu-id="d771f-136">Настройте службу `Echo` с помощью привязки <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="d771f-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
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
>  <span data-ttu-id="d771f-137">Узел службы создается с базовым адресом, а затем остальная часть адреса, относящаяся к базовому адресу, задается как часть конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d771f-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="d771f-138">Такое секционирование адреса обеспечивает более удобное определение нескольких конечных точек для служб в узле.</span><span class="sxs-lookup"><span data-stu-id="d771f-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d771f-139">Свойства объекта <xref:System.ServiceModel.Description.ServiceDescription> в приложении службы нельзя изменять после вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> для объекта <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="d771f-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="d771f-140">Некоторые члены, такие как свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> и методы `AddServiceEndpoint` для объектов <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.ServiceHost>, создают исключение, если их изменить на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="d771f-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="d771f-141">Другие члены можно изменять без появления исключения, но результат при этом будет неопределенным.</span><span class="sxs-lookup"><span data-stu-id="d771f-141">Others permit you to modify them, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="d771f-142">Аналогично, на стороне клиента нельзя изменять значения <xref:System.ServiceModel.Description.ServiceEndpoint> после вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> для объекта <xref:System.ServiceModel.ChannelFactory>.</span><span class="sxs-lookup"><span data-stu-id="d771f-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="d771f-143">Если после этого изменить свойство <xref:System.ServiceModel.ChannelFactory.Credentials%2A>, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="d771f-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="d771f-144">Изменение других значений описания клиента происходит без ошибок, но результат изменения в этом случае является неопределенным.</span><span class="sxs-lookup"><span data-stu-id="d771f-144">The other client description values can be modified without error, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="d771f-145">Как для службы, так и для клиента, рекомендуется изменять описание до вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="d771f-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="d771f-146">Определение конечных точек в конфигурации</span><span class="sxs-lookup"><span data-stu-id="d771f-146">Defining Endpoints in Configuration</span></span>  
 <span data-ttu-id="d771f-147">При создании приложения часто нужно отложить решения для администратора, который выполняет развертывание приложения.</span><span class="sxs-lookup"><span data-stu-id="d771f-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="d771f-148">Например, часто невозможно узнать заранее, каким будет адрес службы (универсальный код ресурса (URI)).</span><span class="sxs-lookup"><span data-stu-id="d771f-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="d771f-149">Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы.</span><span class="sxs-lookup"><span data-stu-id="d771f-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="d771f-150">Такая гибкость достигается благодаря конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d771f-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="d771f-151">Дополнительные сведения см. в разделе [Настройка службы](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="d771f-151">For details, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d771f-152">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с `/config:` *filename*`[,`*filename* `]` переключиться в Быстрое создание файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d771f-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>  
  
## <a name="using-default-endpoints"></a><span data-ttu-id="d771f-153">Использование конечных точек по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d771f-153">Using Default Endpoints</span></span>  
 <span data-ttu-id="d771f-154">Если конечные точки не заданы в коде или в конфигурации, то среда выполнения создает конечные точки по умолчанию, добавляя одну конечную точку по умолчанию для каждого базового адреса в каждом контракте службы, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="d771f-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="d771f-155">Базовый адрес можно указывать в коде или в конфигурации, а конечные точки по умолчанию добавляются, когда вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open> в объекте <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d771f-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d771f-156">Этот пример аналогичен примеру из предыдущего раздела, однако конечные точки не указаны, и поэтому добавляются конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d771f-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>  
  
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
  
 <span data-ttu-id="d771f-157">Если конечные точки предоставляются явно, то конечные точки по умолчанию можно добавить, вызвав метод <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> класса <xref:System.ServiceModel.ServiceHost> перед вызовом <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="d771f-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="d771f-158">Дополнительные сведения о конечных точках по умолчанию см. в разделе [упрощенной конфигурации](../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d771f-158">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d771f-159">См. также</span><span class="sxs-lookup"><span data-stu-id="d771f-159">See Also</span></span>  
 [<span data-ttu-id="d771f-160">Реализация контрактов служб</span><span class="sxs-lookup"><span data-stu-id="d771f-160">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
