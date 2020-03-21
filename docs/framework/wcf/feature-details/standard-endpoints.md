---
title: Стандартные конечные точки
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: 880601664d7602e279c5d022fa37c44914a58772
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184404"
---
# <a name="standard-endpoints"></a><span data-ttu-id="a4ab4-102">Стандартные конечные точки</span><span class="sxs-lookup"><span data-stu-id="a4ab4-102">Standard Endpoints</span></span>
<span data-ttu-id="a4ab4-103">Конечные точки определяются адресом, привязкой и контрактом.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-103">Endpoints are defined by specifying an address, a binding, and a contract.</span></span> <span data-ttu-id="a4ab4-104">Кроме того, для конечной точки можно задать и другие параметры - конфигурацию поведения, заголовки и URI прослушивания.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-104">Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs.</span></span>  <span data-ttu-id="a4ab4-105">Эти значения не изменяются для определенных типов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-105">For certain types of endpoints these values do not change.</span></span> <span data-ttu-id="a4ab4-106">Например, конечные точки обмена метаданными всегда используют контракт <xref:System.ServiceModel.Description.IMetadataExchange>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-106">For example, metadata exchange endpoints always use the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="a4ab4-107">Другим конечным точкам, например <xref:System.ServiceModel.Description.WebHttpEndpoint>, всегда требуется определенное поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-107">Other endpoints, such as <xref:System.ServiceModel.Description.WebHttpEndpoint> always require a specified endpoint behavior.</span></span> <span data-ttu-id="a4ab4-108">Конечную точку можно сделать более удобной для использования, определив значения по умолчанию для часто используемых свойств.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-108">The usability of an endpoint can be improved by having endpoints with default values for commonly used endpoint properties.</span></span> <span data-ttu-id="a4ab4-109">Стандартные конечные точки дают разработчику возможность определить значения свойств по умолчанию, а также создавать конечные точки, где одно или несколько свойств не изменяются.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-109">Standard endpoints enable a developer to define an endpoint that has default values or where one or more endpoint’s properties does not change.</span></span>  <span data-ttu-id="a4ab4-110">Это позволяет не указывать данные статического характера.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-110">These endpoints allow you to use such an endpoint without having to specify information of a static nature.</span></span> <span data-ttu-id="a4ab4-111">Стандартная конечная точка может использоваться в качестве конечной точки инфраструктуры и приложения.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-111">Standard endpoints can be used for infrastructure and application endpoints.</span></span>  
  
## <a name="infrastructure-endpoints"></a><span data-ttu-id="a4ab4-112">Конечные точки инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="a4ab4-112">Infrastructure Endpoints</span></span>  
 <span data-ttu-id="a4ab4-113">Служба может включать конечные точки, некоторые из свойств которых реализованы автором службы неявным образом.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-113">A service may expose endpoints with some of the properties not explicitly implemented by the service author.</span></span> <span data-ttu-id="a4ab4-114">Например, конечная точка обмена метаданными обеспечивает доступ по контракту <xref:System.ServiceModel.Description.IMetadataExchange>, однако автору службы не обязательно реализовывать этот интерфейс, он будет реализован WCF.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-114">For example, the metadata exchange endpoint exposes the <xref:System.ServiceModel.Description.IMetadataExchange> contract but as a service author you do not implement that interface, it is implemented by WCF.</span></span> <span data-ttu-id="a4ab4-115">Такие конечные точки инфраструктуры имеют значения по умолчанию для одного или более свойств, некоторые из которых могут быть неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-115">Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable.</span></span> <span data-ttu-id="a4ab4-116">Свойство <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> конечной точки обмена метаданными должно быть реализацией интерфейса <xref:System.ServiceModel.Description.IMetadataExchange>, в то время как другие свойства, например привязка, могут быть определены разработчиком.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-116">The <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> property of the metadata exchange endpoint must be <xref:System.ServiceModel.Description.IMetadataExchange>, while other properties like binding can be supplied by the developer.</span></span> <span data-ttu-id="a4ab4-117">Конечные точки инфраструктуры определяются установкой свойства <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-117">Infrastructure endpoints are identified by setting the <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> property to `true`.</span></span>  
  
## <a name="application-endpoints"></a><span data-ttu-id="a4ab4-118">Конечные точки приложения</span><span class="sxs-lookup"><span data-stu-id="a4ab4-118">Application Endpoints</span></span>  
 <span data-ttu-id="a4ab4-119">Разработчик приложения может определить свои стандартные конечные точки, определяющие значения по умолчанию для адреса, привязки или контракта.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-119">Application developers can define their own standard endpoints which specify default values for the address, binding, or contract.</span></span> <span data-ttu-id="a4ab4-120">Определение стандартной конечной точки осуществляется через наследование класса <xref:System.ServiceModel.Description.ServiceEndpoint> и задание соответствующих свойств конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-120">You define a standard endpoint by deriving a class from <xref:System.ServiceModel.Description.ServiceEndpoint> and setting the appropriate endpoint properties.</span></span> <span data-ttu-id="a4ab4-121">Могут быть предусмотрены значения по умолчанию для изменяемых свойств.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-121">You can provide default values for properties that can be changed.</span></span> <span data-ttu-id="a4ab4-122">Некоторые другие свойства будут иметь неизменяемые статические значения.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-122">Some other properties will have static values that cannot change.</span></span> <span data-ttu-id="a4ab4-123">Следующий пример демонстрирует процесс реализации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-123">The following example shows how to implement a standard endpoint.</span></span>  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 <span data-ttu-id="a4ab4-124">Чтобы использовать пользовательскую конечную точку в файле конфигурации, необходимо извлечь класс из, <xref:System.ServiceModel.Configuration.StandardEndpointElement>получить класс из, <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>и зарегистрировать новую стандартную конечную точку в разделе расширений в app.config или machine.config.  Поддержка <xref:System.ServiceModel.Configuration.StandardEndpointElement> конфигурации для стандартной конечной точки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-124">To use a user-defined custom endpoint in a configuration file you must derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointElement>, derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>, and register the new standard endpoint in the extensions section in app.config or machine.config.  The <xref:System.ServiceModel.Configuration.StandardEndpointElement> provides configuration support for the standard endpoint, as shown in the following example.</span></span>  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 <span data-ttu-id="a4ab4-125">Обеспечивает <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> тип резервного копирования для коллекции, который отображается под разделом <`standardEndpoints`> в конфигурации для стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-125">The <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> provides the backing type for the collection that appears under the <`standardEndpoints`> section in the configuration for the standard endpoint.</span></span>  <span data-ttu-id="a4ab4-126">В следующем примере показана реализация этого класса.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-126">The following example shows how to implement this class.</span></span>  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

<span data-ttu-id="a4ab4-127">В следующем примере показана регистрация стандартной конечной точки в разделе расширений.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-127">The following example shows how to register a standard endpoint in the extensions section.</span></span>

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
```  
  
## <a name="configuring-a-standard-endpoint"></a><span data-ttu-id="a4ab4-128">Настройка стандартной конечной точки</span><span class="sxs-lookup"><span data-stu-id="a4ab4-128">Configuring a Standard Endpoint</span></span>  
 <span data-ttu-id="a4ab4-129">Стандартные конечные точки могут быть добавлены через код или в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-129">Standard endpoints can be added in code or in configuration.</span></span>  <span data-ttu-id="a4ab4-130">Чтобы добавить стандартную конечную точку через код, необходимо создать экземпляр соответствующего типа стандартной конечной точки и добавить его в узел службы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a4ab4-130">To add a standard endpoint in code simply instantiate the appropriate standard endpoint type and add it to the service host as shown in the following example:</span></span>  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 <span data-ttu-id="a4ab4-131">Чтобы добавить стандартную конечную точку в конфигурацию, добавьте элемент> <`endpoint` в элемент <`service`> и любые необходимые настройки конфигурации в элементе <`standardEndpoints`>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-131">To add a standard endpoint in configuration, add an <`endpoint`> element to the <`service`> element and any needed configuration settings in the <`standardEndpoints`> element.</span></span> <span data-ttu-id="a4ab4-132">В следующем примере показано добавление <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, одной из стандартных конечных точек, поставляемых в составе платформы [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4ab4-132">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, one of the standard endpoints that ships with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 <span data-ttu-id="a4ab4-133">Тип стандартной конечной точки указан с использованием элемента вида в <`endpoint`> элемента.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-133">The type of standard endpoint is specified using the kind attribute in the <`endpoint`> element.</span></span> <span data-ttu-id="a4ab4-134">Конечная точка настроена в `standardEndpoints` элементе> <.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-134">The endpoint is configured within the <`standardEndpoints`> element.</span></span> <span data-ttu-id="a4ab4-135">В приведенном выше примере добавляется и настраивается конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-135">In the example above, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint is added and configured.</span></span> <span data-ttu-id="a4ab4-136">Элемент `udpDiscoveryEndpoint`> <содержит `standardEndpoint` <>, который устанавливает <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> свойство <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-136">The <`udpDiscoveryEndpoint`> element contains a <`standardEndpoint`> that sets the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> property of the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a><span data-ttu-id="a4ab4-137">Стандартные конечные точки, поставляемые в составе платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a4ab4-137">Standard Endpoints Shipped with the .NET Framework</span></span>  
 <span data-ttu-id="a4ab4-138">В приведенной ниже таблице перечислены стандартные конечные точки, которые поставляются в составе платформы .NET [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4ab4-138">The following table lists the standard endpoints shipped with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 `Mex Endpoint`  
 <span data-ttu-id="a4ab4-139">Стандартная конечная точка, используемая для отображения метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-139">A standard endpoint that is used to expose service metadata.</span></span>  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 <span data-ttu-id="a4ab4-140">Стандартная конечная точка, используемая службами для отправки сообщений объявления.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-140">A standard endpoint that is used by services to send announcement messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 <span data-ttu-id="a4ab4-141">Стандартная конечная точка, используемая службами для передачи сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-141">A standard endpoint that is used by services to send discovery messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 <span data-ttu-id="a4ab4-142">Стандартная конечная точка, заранее настроенная для операций обнаружения через привязку для многоадресной рассылки UDP.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-142">A standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 <span data-ttu-id="a4ab4-143">Стандартная конечная точка, используемая службами для отправки сообщений объявления через привязку UDP.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-143">A standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <span data-ttu-id="a4ab4-144">Стандартная конечная точка, которая использует WS-Discovery для динамического обнаружения адреса конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-144">A standard endpoint that uses WS-Discovery to find the endpoint address dynamically at runtime.</span></span>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 <span data-ttu-id="a4ab4-145">Стандартная конечная точка для обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-145">A standard endpoint for metadata exchange.</span></span>  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <span data-ttu-id="a4ab4-146">Стандартная конечная точка с привязкой <xref:System.ServiceModel.WebHttpBinding>, которая автоматически добавляет поведение <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-146">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior</span></span>  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <span data-ttu-id="a4ab4-147">Стандартная конечная точка с привязкой <xref:System.ServiceModel.WebHttpBinding>, которая автоматически добавляет поведение <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-147">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior.</span></span>  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <span data-ttu-id="a4ab4-148">Стандартная конечная точка с привязкой <xref:System.ServiceModel.WebHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-148">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 <span data-ttu-id="a4ab4-149">Стандартная конечная точка, позволяющая вызывать операции управления для экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-149">A standard endpoint that enables you to call control operations on workflow instances.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 <span data-ttu-id="a4ab4-150">Стандартная конечная точка, поддерживающая создание рабочих процессов и возобновление закладок.</span><span class="sxs-lookup"><span data-stu-id="a4ab4-150">A standard endpoint that supports workflow creation and bookmark resumption.</span></span>
