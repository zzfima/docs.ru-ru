---
title: Упрощенная конфигурация
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 4e316290c045b75896c61e36c1646440c18678e2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249634"
---
# <a name="simplified-configuration"></a><span data-ttu-id="9e5a7-102">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="9e5a7-102">Simplified Configuration</span></span>
<span data-ttu-id="9e5a7-103">Настройка служб Windows Communication Foundation (WCF) может быть сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-103">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="9e5a7-104">Разных параметров много, и не всегда легко понять, какие настройки необходимы.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-104">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="9e5a7-105">В то время как файлы конфигурации повышают гибкость служб WCF, они также являются источником многих проблем, которые трудно найти.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-105">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="9e5a7-106">устраняет эти проблемы, предоставляя способ уменьшить размер и упростить конфигурацию службы.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-106">addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="9e5a7-107">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="9e5a7-107">Simplified Configuration</span></span>  
 <span data-ttu-id="9e5a7-108">В файлах конфигурации wCF раздел `system.serviceModel` <`service`> содержит элемент <> для каждой размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-108">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="9e5a7-109">Элемент `service`> <содержит набор `endpoint` элементов> <, которые определяют конечные точки, выставленные для каждой службы, и опционально набор поведения службы.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-109">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="9e5a7-110">В `endpoint` <> элементы определяют адрес, связывание и контракт, выставленные в конечном пункте, а также опционально обязательную конфигурацию и поведение конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-110">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="9e5a7-111">Раздел `system.serviceModel` <> также `behaviors` содержит элемент> <, который позволяет указать поведение службы или конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-111">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="9e5a7-112">В следующем примере `system.serviceModel` показан <> раздел файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-112">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="9e5a7-113">Упрощает настройку службы WCF, удаляя требование к элементу <`service`>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-113">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="9e5a7-114">Если вы не добавите <`service`> раздел или `service` не добавите какие-либо конечные точки в раздел> <и ваша служба не будет программно определять какие-либо конечные точки, то в ваш сервис автоматически добавляется набор конечных точек по умолчанию, по одному для каждого базового адреса службы и для каждого контракта, реализованного вашей службой.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-114">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="9e5a7-115">В каждой из этих конечных точек адрес конечной точки соответствует базовому адресу, привязка определяется схемой базового адреса, а контракт - службой.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-115">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="9e5a7-116">Если не нужно задавать конечные точки или поведения служб или изменять какие-либо параметры привязки, то указывать файл конфигурации служб не нужно вообще.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-116">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="9e5a7-117">Если служба реализует два контракта, а на узле включен транспорт по протоколам HTTP и TCP, то узел службы создаст четыре точки по умолчанию: по одной на каждый контракт для каждого транспорта.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-117">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="9e5a7-118">Чтобы создать по умолчанию конечные точки, узел службы должен знать, какие привязки использовать.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-118">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="9e5a7-119">Эти параметры указаны в `protocolMappings` разделе> `system.serviceModel` <в разделе <>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-119">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="9e5a7-120">Раздел `protocolMappings` <> содержит список схем транспортных протоколов, отображаемых на обязательные типы.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-120">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="9e5a7-121">Узел службы использует переданные ему базовые адреса, чтобы определить, какую привязку использовать.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-121">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="9e5a7-122">В следующем примере `protocolMappings` используется элемент> <.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-122">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9e5a7-123">Изменение элементов конфигурации по умолчанию, например привязок или поведений, может повлиять на службы, определенные на нижних уровнях иерархии конфигурации, поскольку они могут использовать эти привязки или поведения.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-123">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="9e5a7-124">Поэтому пользователь, изменяющий привязки и поведения по умолчанию, должен знать, что эти изменения могут повлиять на другие службы в иерархии.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-124">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e5a7-125">Службы, размещенные в службах IIS или WAS, используют в качестве базового адреса виртуальный каталог.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-125">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="9e5a7-126">В предыдущем примере конечная точка с базовым адресом, начинающимся с «http», использует привязку <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-126">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="9e5a7-127">Конечная точка с базовым адресом, начинающимся с «net.tcp», использует привязку <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-127">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="9e5a7-128">Параметры можно переопределить в локальном файле App.config или Web.config.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-128">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="9e5a7-129">Каждый элемент `protocolMappings` в разделе <> должен указывать схему и привязку.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-129">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="9e5a7-130">В обязательном порядке `bindingConfiguration` он может указать атрибут, определяющий связывающую конфигурацию в <`bindings`> разделе файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-130">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="9e5a7-131">Если параметры `bindingConfiguration` не заданы, то используется анонимная конфигурация привязки нужного типа.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-131">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="9e5a7-132">Поведение службы настраивается для конечных точек `behavior` по умолчанию с помощью анонимных разделов <> в разделах <`serviceBehaviors`>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-132">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="9e5a7-133">Для настройки `behavior` поведения службы используются все элементы неназванных> <в <`serviceBehaviors`>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-133">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="9e5a7-134">Например, следующий файл конфигурации позволяет публиковать метаданные всех служб в узле.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-134">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="9e5a7-135">Поведение конечных точек настраивается `behavior` с помощью `serviceBehaviors` анонимных разделов> <в разделах <>.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-135">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="9e5a7-136">В следующем примере приведен файл конфигурации, эквивалентный файлу, приведенному в начале данного раздела, с упрощенной моделью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-136">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> <span data-ttu-id="9e5a7-137">Эта возможность относится только к конфигурации службы WCF, а не к конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-137">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="9e5a7-138">В большинстве случаев конфигурация клиента WCF создается с помощью средства, например svcutil.exe, или путем добавления ссылки на службу из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-138">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="9e5a7-139">Если вы вручную настраиваете клиент WCF, вам \<нужно будет добавить элемент клиента> в конфигурацию и указать все конечные точки, которые вы хотите позвонить.</span><span class="sxs-lookup"><span data-stu-id="9e5a7-139">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5a7-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9e5a7-140">See also</span></span>

- [<span data-ttu-id="9e5a7-141">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="9e5a7-141">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="9e5a7-142">Настройка привязок для служб</span><span class="sxs-lookup"><span data-stu-id="9e5a7-142">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="9e5a7-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="9e5a7-143">Configuring System-Provided Bindings</span></span>](./feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9e5a7-144">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="9e5a7-144">Configuring Services</span></span>](configuring-services.md)
- [<span data-ttu-id="9e5a7-145">Настройка wCF-сервисов</span><span class="sxs-lookup"><span data-stu-id="9e5a7-145">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="9e5a7-146">Настройка служб WCF в коде</span><span class="sxs-lookup"><span data-stu-id="9e5a7-146">Configuring WCF Services in Code</span></span>](configuring-wcf-services-in-code.md)
