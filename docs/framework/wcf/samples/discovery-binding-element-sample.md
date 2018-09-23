---
title: Образец элемента привязки для обнаружения
ms.date: 03/30/2017
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
ms.openlocfilehash: d906d9a389c50095f2af5d52e3874c3e43199e68
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696213"
---
# <a name="discovery-binding-element-sample"></a><span data-ttu-id="b4d04-102">Образец элемента привязки для обнаружения</span><span class="sxs-lookup"><span data-stu-id="b4d04-102">Discovery Binding Element Sample</span></span>
<span data-ttu-id="b4d04-103">Данный образец демонстрирует использование клиентского элемента привязки обнаружения для обнаружения службы.</span><span class="sxs-lookup"><span data-stu-id="b4d04-103">This sample demonstrates how to use the discovery client binding element to discover a service.</span></span> <span data-ttu-id="b4d04-104">Эта функция позволяет разработчикам добавлять клиентский канал обнаружения к клиентскому стеку каналов, в результате чего модель программирования становится намного интуитивно понятнее.</span><span class="sxs-lookup"><span data-stu-id="b4d04-104">This feature enables developers to add a discovery client channel to their existing client channel stack, making the programming model very intuitive.</span></span> <span data-ttu-id="b4d04-105">Если соответствующий канал открыт, адрес службы разрешается в процессе обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b4d04-105">When the associated channel is opened, the address of the service is resolved using discovery.</span></span> <span data-ttu-id="b4d04-106">Данный образец состоит из следующих проектов.</span><span class="sxs-lookup"><span data-stu-id="b4d04-106">This sample consists of the following projects:</span></span>  
  
-   <span data-ttu-id="b4d04-107">**CalculatorService**: обнаруживаемой службы WCF.</span><span class="sxs-lookup"><span data-stu-id="b4d04-107">**CalculatorService**: A discoverable WCF service.</span></span>  
  
-   <span data-ttu-id="b4d04-108">**CalculatorClient**: клиентское приложение WCF, которое использует клиентский канал обнаружения для поиска и вызова службы CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="b4d04-108">**CalculatorClient**: A WCF client application that uses the discovery client channel to search for and call the CalculatorService.</span></span>  
  
-   <span data-ttu-id="b4d04-109">**DynamicCalculatorClient**: клиентское приложение WCF, которое использует динамическую конечную точку для поиска и вызова службы CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="b4d04-109">**DynamicCalculatorClient**: A WCF client application that uses a dynamic endpoint to search for and call the CalculatorService.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4d04-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b4d04-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b4d04-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b4d04-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b4d04-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="b4d04-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b4d04-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b4d04-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a><span data-ttu-id="b4d04-114">CalculatorService</span><span class="sxs-lookup"><span data-stu-id="b4d04-114">CalculatorService</span></span>  
 <span data-ttu-id="b4d04-115">Данный проект содержит простую службу калькулятора, которая реализует контракт `ICalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="b4d04-115">This project contains a simple calculator service that implements the `ICalculatorService` contract.</span></span>  
  
 <span data-ttu-id="b4d04-116">Следующий файл App.config используется для добавления поведения `<serviceDiscovery>` в набор поведений службы, а также конечной точки обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b4d04-116">The following App.config file is used to add a `<serviceDiscovery>` behavior in the service behaviors as well as the discovery endpoint.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="b4d04-117">При этом служба и ее конечные точки становятся доступными для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b4d04-117">This makes the service and its endpoints discoverable.</span></span> <span data-ttu-id="b4d04-118">Служба CalculatorService представляет собой саморазмещаемую службу, которая добавляет одну конечную точку с использованием привязки NetTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="b4d04-118">The CalculatorService is a self-hosted service that adds one endpoint using the NetTcpBinding binding.</span></span> <span data-ttu-id="b4d04-119">Кроме того, она добавляет в конечную точку поведение `EndpointDiscoveryBehavior` и указывает область, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="b4d04-119">It also adds an `EndpointDiscoveryBehavior` to the endpoint and specifies a scope as shown in the following code.</span></span>  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a><span data-ttu-id="b4d04-120">CalculatorClient</span><span class="sxs-lookup"><span data-stu-id="b4d04-120">CalculatorClient</span></span>  
 <span data-ttu-id="b4d04-121">Данный проект содержит реализацию клиента, которая отправляет сообщения службе CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="b4d04-121">This project contains a client implementation that sends messages to the CalculatorService.</span></span> <span data-ttu-id="b4d04-122">Эта программа использует метод `CreateCustomBindingWithDiscoveryElement()` для создания пользовательской привязки, которая использует клиентский канал обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b4d04-122">This program uses the `CreateCustomBindingWithDiscoveryElement()` method to create a custom binding that uses the Discovery Client Channel.</span></span>  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <span data-ttu-id="b4d04-123">После создания экземпляра <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> разработчик указывает критерии, используемые при поиске службы.</span><span class="sxs-lookup"><span data-stu-id="b4d04-123">After the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is instantiated, the developer specifies the criteria to use when searching for a service.</span></span> <span data-ttu-id="b4d04-124">В данном случае критерием обнаружения является тип `ICalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="b4d04-124">In this case, the discovery find criterion is the `ICalculatorService` type.</span></span> <span data-ttu-id="b4d04-125">Кроме того, разработчик указывает поставщика <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, который возвращает конечную точку <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>, указывающую место поиска служб.</span><span class="sxs-lookup"><span data-stu-id="b4d04-125">Additionally, the developer specifies a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> which returns a <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> that specifies where to look for the services.</span></span> <span data-ttu-id="b4d04-126">Поставщик <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> возвращает новый экземпляр конечной точки <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="b4d04-126">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> returns a new <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance.</span></span> <span data-ttu-id="b4d04-127">Дополнительные сведения см. в разделе [с помощью пользовательской привязке для клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="b4d04-127">For more information, see [Using a Custom Binding with the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 <span data-ttu-id="b4d04-128">В данном случае клиент использует многоадресный механизм UDP, определенный в протоколе обнаружения, для поиска служб в локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="b4d04-128">In this case, the client uses the UDP multicast mechanism defined by the Discovery protocol to search for services on the local subnet.</span></span> <span data-ttu-id="b4d04-129">В оставшейся части метода создается пользовательская привязка, и элемент привязки обнаружения вставляется в верхушку стека.</span><span class="sxs-lookup"><span data-stu-id="b4d04-129">The remainder of the method creates a custom binding and inserts the Discovery binding element at the top of the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4d04-130">Элемент <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> должен быть помещен в верхушку стека привязок.</span><span class="sxs-lookup"><span data-stu-id="b4d04-130">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must be placed on the top of the binding stack.</span></span> <span data-ttu-id="b4d04-131">Любой элемент <xref:System.ServiceModel.Channels.BindingElement>, расположенный выше элемента <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, должен удостовериться, что создаваемые им фабрики каналов и каналы не используют свойства `EndpointAddress` и `Via`, поскольку фактический адрес становится известным только на уровне клиентского канала обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b4d04-131">Any <xref:System.ServiceModel.Channels.BindingElement> on top of <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the channel factory or channel it creates does not use the `EndpointAddress` or `Via` properties, because the actual address is found only at the Discovery client channel.</span></span>  
  
 <span data-ttu-id="b4d04-132">После этого можно создать экземпляр `CalculatorClient`, передав ему эту пользовательскую привязку и адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b4d04-132">Next, the `CalculatorClient` can be instantiated by passing in this custom binding as well as an endpoint address.</span></span>  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 <span data-ttu-id="b4d04-133">При использовании клиентского канала обнаружения передается константный адрес конечной точки, заданный ранее.</span><span class="sxs-lookup"><span data-stu-id="b4d04-133">When using the Discovery Client Channel, the constant endpoint address specified previously is passed in.</span></span> <span data-ttu-id="b4d04-134">Во время выполнения клиентский канал обнаружения находит службу, указываемую критерием поиска, и подключается к ней.</span><span class="sxs-lookup"><span data-stu-id="b4d04-134">Now at runtime, the Discovery Client Channel finds the service specified by the find criteria and connects to it.</span></span> <span data-ttu-id="b4d04-135">Для установления соединения между службой и клиентом они также должны иметь один и тот же базовый стек привязок.</span><span class="sxs-lookup"><span data-stu-id="b4d04-135">For the service and the client to establish a connection, they must also have the same underlying binding stack.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b4d04-136">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b4d04-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="b4d04-137">Откройте решение в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4d04-137">Open the solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4d04-138">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="b4d04-138">Build the solution.</span></span>  
  
3.  <span data-ttu-id="b4d04-139">Запустите приложение службы и каждое из клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="b4d04-139">Run the service application and each of the client applications.</span></span>  
  
4.  <span data-ttu-id="b4d04-140">Заметьте, что клиенту удалось найти службу, не зная ее адреса.</span><span class="sxs-lookup"><span data-stu-id="b4d04-140">Observe that the client was able to find the service without knowing its address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d04-141">См. также</span><span class="sxs-lookup"><span data-stu-id="b4d04-141">See Also</span></span>
