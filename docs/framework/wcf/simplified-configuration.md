---
title: "Упрощенная конфигурация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334dfce44b1f0a7b6b38f509f2f0a346ef90630f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="simplified-configuration"></a><span data-ttu-id="f449d-102">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="f449d-102">Simplified Configuration</span></span>
<span data-ttu-id="f449d-103">Настройка служб [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] может оказаться сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="f449d-103">Configuring [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] services can be a complex task.</span></span> <span data-ttu-id="f449d-104">Разных параметров много, и не всегда легко понять, какие настройки необходимы.</span><span class="sxs-lookup"><span data-stu-id="f449d-104">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="f449d-105">Хотя файлы конфигурации и увеличивают гибкость служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], они также являются источником многих трудно обнаруживаемых проблем.</span><span class="sxs-lookup"><span data-stu-id="f449d-105">While configuration files increase the flexibility of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="f449d-106"> устраняет эти проблемы, предоставляя способ уменьшить размер и упростить конфигурацию службы.</span><span class="sxs-lookup"><span data-stu-id="f449d-106"> addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="f449d-107">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="f449d-107">Simplified Configuration</span></span>  
 <span data-ttu-id="f449d-108">В файлах конфигурации служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] раздел <`system.serviceModel`> содержит элемент <`service`> для каждой размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="f449d-108">In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="f449d-109">Элемент <`service`> содержит коллекцию элементов <`endpoint`>, которыми задаются конечные точки, открытые для каждой службы, и по желанию набор поведений службы.</span><span class="sxs-lookup"><span data-stu-id="f449d-109">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="f449d-110">Элементы <`endpoint`> указывают адрес, привязку и контракт, открытые в конечной точке, и по желанию конфигурацию привязки и поведения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f449d-110">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="f449d-111">В разделе <`system.serviceModel`> также содержится элемент <`behaviors`>, с помощью которого можно указать поведение служб или конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f449d-111">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="f449d-112">В следующем примере демонстрируется раздел <`system.serviceModel`> файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f449d-112">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
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
  
 <span data-ttu-id="f449d-113">Платформа [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] упрощает настройку службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] за счет отмены требования элемента <`service`>.</span><span class="sxs-lookup"><span data-stu-id="f449d-113">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] makes configuring a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="f449d-114">Если вы не добавили раздел <`service`> или добавили какие-либо конечные точки в раздел <`service`>, а применяемая служба не задает конечные точки программно, то в службу автоматически будет добавлен набор конечных точек по умолчанию, по одной на каждый базовый адрес службы и на каждый контракт, используемый службой.</span><span class="sxs-lookup"><span data-stu-id="f449d-114">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="f449d-115">В каждой из этих конечных точек адрес конечной точки соответствует базовому адресу, привязка определяется схемой базового адреса, а контракт - службой.</span><span class="sxs-lookup"><span data-stu-id="f449d-115">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="f449d-116">Если не нужно задавать конечные точки или поведения служб или изменять какие-либо параметры привязки, то указывать файл конфигурации служб не нужно вообще.</span><span class="sxs-lookup"><span data-stu-id="f449d-116">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="f449d-117">Если служба реализует два контракта, а на узле включен транспорт по протоколам HTTP и TCP, то узел службы создаст четыре точки по умолчанию: по одной на каждый контракт для каждого транспорта.</span><span class="sxs-lookup"><span data-stu-id="f449d-117">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="f449d-118">Чтобы создать по умолчанию конечные точки, узел службы должен знать, какие привязки использовать.</span><span class="sxs-lookup"><span data-stu-id="f449d-118">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="f449d-119">Эти параметры заданы в разделе <`protocolMappings`> внутри раздела <`system.serviceModel`>.</span><span class="sxs-lookup"><span data-stu-id="f449d-119">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="f449d-120">Раздел <`protocolMappings`> содержит список схем транспортных протоколов, распределенных по типам привязки.</span><span class="sxs-lookup"><span data-stu-id="f449d-120">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="f449d-121">Узел службы использует переданные ему базовые адреса, чтобы определить, какую привязку использовать.</span><span class="sxs-lookup"><span data-stu-id="f449d-121">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="f449d-122">В следующем примере используется элемент <`protocolMappings`>.</span><span class="sxs-lookup"><span data-stu-id="f449d-122">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f449d-123">Изменение элементов конфигурации по умолчанию, например привязок или поведений, может повлиять на службы, определенные на нижних уровнях иерархии конфигурации, поскольку они могут использовать эти привязки или поведения.</span><span class="sxs-lookup"><span data-stu-id="f449d-123">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="f449d-124">Поэтому пользователь, изменяющий привязки и поведения по умолчанию, должен знать, что эти изменения могут повлиять на другие службы в иерархии.</span><span class="sxs-lookup"><span data-stu-id="f449d-124">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f449d-125">Службы, размещенные в службах IIS или WAS, используют в качестве базового адреса виртуальный каталог.</span><span class="sxs-lookup"><span data-stu-id="f449d-125">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="f449d-126">В предыдущем примере конечная точка с базовым адресом, начинающимся с «http», использует привязку <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f449d-126">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="f449d-127">Конечная точка с базовым адресом, начинающимся с «net.tcp», использует привязку <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f449d-127">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="f449d-128">Параметры можно переопределить в локальном файле App.config или Web.config.</span><span class="sxs-lookup"><span data-stu-id="f449d-128">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="f449d-129">Каждый элемент внутри раздела <`protocolMappings`> должен задавать схему и привязку.</span><span class="sxs-lookup"><span data-stu-id="f449d-129">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="f449d-130">Дополнительно он может иметь атрибут `bindingConfiguration`, задающий конфигурацию привязки внутри раздела файла конфигурации <`bindings`>.</span><span class="sxs-lookup"><span data-stu-id="f449d-130">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="f449d-131">Если параметры `bindingConfiguration` не заданы, то используется анонимная конфигурация привязки нужного типа.</span><span class="sxs-lookup"><span data-stu-id="f449d-131">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="f449d-132">Поведения службы настроены для конечных точек по умолчанию с помощью анонимных разделов <`behavior`> в разделах <`serviceBehaviors`>.</span><span class="sxs-lookup"><span data-stu-id="f449d-132">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="f449d-133">Каждый неименованный элемент <`behavior`> в разделе <`serviceBehaviors`> используется для настройки поведений служб.</span><span class="sxs-lookup"><span data-stu-id="f449d-133">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="f449d-134">Например, следующий файл конфигурации позволяет публиковать метаданные всех служб в узле.</span><span class="sxs-lookup"><span data-stu-id="f449d-134">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
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
  
 <span data-ttu-id="f449d-135">Поведения конечных точек настроены при помощи анонимных разделов <`behavior`> в разделах <`serviceBehaviors`>.</span><span class="sxs-lookup"><span data-stu-id="f449d-135">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="f449d-136">В следующем примере приведен файл конфигурации, эквивалентный файлу, приведенному в начале данного раздела, с упрощенной моделью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f449d-136">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <bindings>  
       <basicHttpBinding>  
          <binding maxBufferSize="100"  
                   maxReceiveBufferSize="100" />  
       </basicHttpBinding>  
    </bindings>    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->  
    <!-- The service behavior with name="" will be picked up by the service -->  
    <protocolMapping>  
      <add scheme="http"     binding="basicHttpBinding" / </protocolMapping>  
  </system.serviceModel>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="f449d-137">Эта функция относится только к конфигурации службы WCF, а не к конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="f449d-137">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="f449d-138">В большинстве случаев конфигурация клиента WCF создается с помощью средства, например svcutil.exe, или путем добавления ссылки на службу из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f449d-138">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="f449d-139">Если пользователь вручную настраивает клиент WCF необходимо добавить \<клиента > элемент конфигурации и указать все конечные точки, необходимо вызвать.</span><span class="sxs-lookup"><span data-stu-id="f449d-139">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f449d-140">См. также</span><span class="sxs-lookup"><span data-stu-id="f449d-140">See Also</span></span>  
 [<span data-ttu-id="f449d-141">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="f449d-141">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [<span data-ttu-id="f449d-142">Настройка привязок для служб</span><span class="sxs-lookup"><span data-stu-id="f449d-142">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [<span data-ttu-id="f449d-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f449d-143">Configuring System-Provided Bindings</span></span>](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f449d-144">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="f449d-144">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="f449d-145">Настройка приложений Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f449d-145">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [<span data-ttu-id="f449d-146">Настройка служб WCF в коде</span><span class="sxs-lookup"><span data-stu-id="f449d-146">Configuring WCF Services in Code</span></span>](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
