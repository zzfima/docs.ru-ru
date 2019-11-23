---
title: Настройка служб WCF в коде
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: c6bcf08511470d28e1087108d95e477683b0338b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320633"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="1be3c-102">Настройка служб WCF в коде</span><span class="sxs-lookup"><span data-stu-id="1be3c-102">Configuring WCF Services in Code</span></span>
<span data-ttu-id="1be3c-103">Windows Communication Foundation (WCF) позволяет разработчикам настраивать службы с помощью файлов конфигурации или кода.</span><span class="sxs-lookup"><span data-stu-id="1be3c-103">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="1be3c-104">Файлы конфигурации используются, если необходимо настроить службу после ее развертывания.</span><span class="sxs-lookup"><span data-stu-id="1be3c-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="1be3c-105">При использовании файлов конфигурации ИТ-работнику требуется только обновить файл конфигурации без необходимости выполнять повторную компиляцию.</span><span class="sxs-lookup"><span data-stu-id="1be3c-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="1be3c-106">Файлы конфигурации, однако, могут быть сложными и требовать больших усилий при обслуживании.</span><span class="sxs-lookup"><span data-stu-id="1be3c-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="1be3c-107">Отсутствует поддержка отладки файлов конфигурации, и ссылки на элементы конфигурации осуществляются по именам, что усложняет работу и способствует совершению ошибок при создании файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1be3c-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="1be3c-108">WCF также позволяет настраивать службы в коде.</span><span class="sxs-lookup"><span data-stu-id="1be3c-108">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="1be3c-109">В более ранних версиях WCF (4,0 и более ранних версий) Настройка служб в коде была непростой в собственных сценариях, класс <xref:System.ServiceModel.ServiceHost> позволял вам настроить конечные точки и поведения до вызова ServiceHost. Open.</span><span class="sxs-lookup"><span data-stu-id="1be3c-109">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="1be3c-110">Однако в сценариях с размещением в Интернете нет прямого доступа к классу <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1be3c-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="1be3c-111">Чтобы настроить службу, размещенную в сети, приходилось создавать класс `System.ServiceModel.ServiceHostFactory`, который создавал <xref:System.ServiceModel.Activation.ServiceHostFactory> и выполнял необходимые настройки.</span><span class="sxs-lookup"><span data-stu-id="1be3c-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="1be3c-112">Начиная с .NET 4,5, WCF предоставляет более простой способ настройки автономных и размещенных в Интернете служб в коде.</span><span class="sxs-lookup"><span data-stu-id="1be3c-112">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="1be3c-113">Метод Configure</span><span class="sxs-lookup"><span data-stu-id="1be3c-113">The Configure method</span></span>  
 <span data-ttu-id="1be3c-114">Просто определите открытый статический метод с именем `Configure` со следующей сигнатурой в классе реализации службы.</span><span class="sxs-lookup"><span data-stu-id="1be3c-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="1be3c-115">Метод принимает экземпляр <xref:System.ServiceModel.ServiceConfiguration>, что позволяет разработчикам добавлять конечные точки и расширения функциональности.</span><span class="sxs-lookup"><span data-stu-id="1be3c-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="1be3c-116">Этот метод вызывается WCF перед открытием узла службы.</span><span class="sxs-lookup"><span data-stu-id="1be3c-116">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="1be3c-117">Если он задан, то никакие параметры конфигурации службы, определенные в файле app.config или web.config, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="1be3c-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="1be3c-118">В следующем фрагменте кода показано, как определить метод `Configure` и добавить конечную точку службы, поведение конечной точки и расширения функциональности служб.</span><span class="sxs-lookup"><span data-stu-id="1be3c-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return $"You entered: {value}";
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="1be3c-119">Чтобы включить для службы протокол (например, HTTPS), следует явно добавить конечную точку, использующую протокол, или автоматически добавить конечные точки с помощью привязки ServiceConfiguration.EnableProtocol, которая добавляет конечную точку для каждого базового адреса, совместимого с использованием определенного протокола и каждого контракта службы.</span><span class="sxs-lookup"><span data-stu-id="1be3c-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="1be3c-120">В следующем примере кода показывается, как использовать метод ServiceConfiguration.EnableProtocol:</span><span class="sxs-lookup"><span data-stu-id="1be3c-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 <span data-ttu-id="1be3c-121">Параметры в разделе <`protocolMappings`> используются только в том случае, если конечные точки приложения не добавляются в <xref:System.ServiceModel.ServiceConfiguration> программным способом. При необходимости можно загрузить конфигурацию службы из файла конфигурации приложения по умолчанию, вызвав <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>, а затем изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="1be3c-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="1be3c-122">Класс <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> также позволяет загрузить конфигурацию из централизованной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1be3c-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="1be3c-123">В следующем примере кода показано, как это реализовать.</span><span class="sxs-lookup"><span data-stu-id="1be3c-123">The following code illustrates how to implement this:</span></span>  
  
```csharp
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="1be3c-124">Обратите внимание, что <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> игнорирует параметры <`host`> в теге <`service`>.`system.serviceModel`</span><span class="sxs-lookup"><span data-stu-id="1be3c-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="1be3c-125">По сути <`host`> — это конфигурация узла, а не конфигурация службы, которая загружается перед выполнением метода Configure.</span><span class="sxs-lookup"><span data-stu-id="1be3c-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be3c-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="1be3c-126">See also</span></span>

- [<span data-ttu-id="1be3c-127">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="1be3c-127">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="1be3c-128">Настройка поведения клиентов</span><span class="sxs-lookup"><span data-stu-id="1be3c-128">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
- [<span data-ttu-id="1be3c-129">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="1be3c-129">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="1be3c-130">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="1be3c-130">Configuration</span></span>](./samples/configuration-sample.md)
- [<span data-ttu-id="1be3c-131">Активация на основе конфигурации в IIS и WAS</span><span class="sxs-lookup"><span data-stu-id="1be3c-131">Configuration-Based Activation in IIS and WAS</span></span>](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="1be3c-132">Конфигурация и поддержка метаданных</span><span class="sxs-lookup"><span data-stu-id="1be3c-132">Configuration and Metadata Support</span></span>](./extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="1be3c-133">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="1be3c-133">Configuration</span></span>](./diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="1be3c-134">Практическое руководство. Указание привязки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="1be3c-134">How to: Specify a Service Binding in Configuration</span></span>](how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="1be3c-135">Практическое руководство. Создание конечной точки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="1be3c-135">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="1be3c-136">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1be3c-136">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="1be3c-137">Практическое руководство. Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="1be3c-137">How to: Specify a Client Binding in Configuration</span></span>](how-to-specify-a-client-binding-in-configuration.md)
