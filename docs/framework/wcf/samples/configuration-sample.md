---
title: Образец конфигурации
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: 78108dc9b28657f0479e9e39ad134f03cf6c877b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714959"
---
# <a name="configuration-sample"></a><span data-ttu-id="f24b1-102">Образец конфигурации</span><span class="sxs-lookup"><span data-stu-id="f24b1-102">Configuration Sample</span></span>
<span data-ttu-id="f24b1-103">Этот образец демонстрирует, как при помощи файла конфигурации можно сделать службу доступной для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-103">This sample demonstrates the use of a configuration file to make a service discoverable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f24b1-104">Данный образец реализует возможность обнаружения в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f24b1-104">This sample implements discovery in configuration.</span></span> <span data-ttu-id="f24b1-105">Пример, в котором реализовано обнаружение в коде, см. в разделе [Basic](../../../../docs/framework/wcf/samples/basic-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f24b1-105">For a sample that implements discovery in code, see [Basic](../../../../docs/framework/wcf/samples/basic-sample.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f24b1-106">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f24b1-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f24b1-107">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f24b1-107">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="f24b1-108">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="f24b1-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f24b1-109">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f24b1-109">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a><span data-ttu-id="f24b1-110">Настройка службы</span><span class="sxs-lookup"><span data-stu-id="f24b1-110">Service Configuration</span></span>  
 <span data-ttu-id="f24b1-111">Файл конфигурации в данном образце иллюстрирует две возможности.</span><span class="sxs-lookup"><span data-stu-id="f24b1-111">The configuration file in this sample demonstrates two features:</span></span>  
  
- <span data-ttu-id="f24b1-112">Обеспечение доступности обнаружения службы через стандартную конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="f24b1-112">Making the service discoverable over a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
- <span data-ttu-id="f24b1-113">Настройка информации, связанной с обнаружением, для конечной точки приложения службы, а также настройка некоторых параметров, связанных с обнаружением, для стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f24b1-113">Adjusting discovery-related information for the service’s application endpoint and adjusting some of the discovery-related settings on the standard endpoint.</span></span>  
  
 <span data-ttu-id="f24b1-114">Чтобы включить функцию обнаружения, в файле конфигурации приложения службы необходимо произвести следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-114">To enable discovery, a few changes must be made in the application configuration file for the service:</span></span>  
  
- <span data-ttu-id="f24b1-115">Необходимо добавить конечную точку обнаружения к элементу `<service>`.</span><span class="sxs-lookup"><span data-stu-id="f24b1-115">A discovery endpoint must be added to the `<service>` element.</span></span> <span data-ttu-id="f24b1-116">Это стандартная конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="f24b1-116">This is a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span> <span data-ttu-id="f24b1-117">Это системная конечная точка, которую среда выполнения связывает со службой обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-117">This is a system endpoint that the runtime associates with the discovery service.</span></span> <span data-ttu-id="f24b1-118">Служба обнаружения использует эту конечную точку для прослушивания сообщений.</span><span class="sxs-lookup"><span data-stu-id="f24b1-118">The discovery service listens for messages on this endpoint.</span></span>  
  
- <span data-ttu-id="f24b1-119">Добавим поведение `<serviceDiscovery>` в раздел `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="f24b1-119">A `<serviceDiscovery>` behavior is added to the `<serviceBehaviors>` section.</span></span> <span data-ttu-id="f24b1-120">Это позволит обнаруживать службу во время выполнения, используя ранее упомянутую конечную точку обнаружения для прослушивания сообщений `Probe` и `Resolve`.</span><span class="sxs-lookup"><span data-stu-id="f24b1-120">This enables the service to be discovered at runtime and uses the discovery endpoint mentioned previously to listen for discovery `Probe` and `Resolve` messages.</span></span> <span data-ttu-id="f24b1-121">После выполнения этих двух добавлений служба доступна для обнаружения на указанной конечной точке обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-121">With these two additions, the service is discoverable at the discovery endpoint specified.</span></span>  
  
 <span data-ttu-id="f24b1-122">В следующем фрагменте конфигурации показана служба с указанной конечной точкой приложения и конечной точкой обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-122">The following config snippet shows a service with an application endpoint and a discovery endpoint defined:</span></span>  
  
```xml
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"   
                    kind="udpDiscoveryEndpoint"   
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
```  
  
 <span data-ttu-id="f24b1-123">Чтобы воспользоваться объявлениями, необходимо добавить конечную точку объявления.</span><span class="sxs-lookup"><span data-stu-id="f24b1-123">To take advantage of announcements, you will need to add an announcement endpoint.</span></span> <span data-ttu-id="f24b1-124">Для этого нужно изменить файл конфигурации, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f24b1-124">To do this, modify the configuration file as shown in the following code.</span></span>  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 <span data-ttu-id="f24b1-125">При добавлении конечной точки объявления к службе обнаружения создается клиент объявления по умолчанию для службы.</span><span class="sxs-lookup"><span data-stu-id="f24b1-125">Adding an announcement endpoint to the discovery service behavior creates a default announcement client for the service.</span></span> <span data-ttu-id="f24b1-126">Это гарантирует, что служба отправит объявление о режиме «в сети» или «не в сети» соответственно при открытии и закрытии службы.</span><span class="sxs-lookup"><span data-stu-id="f24b1-126">This guarantees that the service will send an online and offline announcement when the service is opened and closed respectively.</span></span>  
  
 <span data-ttu-id="f24b1-127">Можно не ограничиваться приведенными простыми шагами и изменить в файле конфигурации дополнительные поведения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-127">This configuration file goes beyond just those simple steps by modifying additional behaviors.</span></span> <span data-ttu-id="f24b1-128">Информацией, относящейся к обнаружению, можно управлять с использованием определенных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f24b1-128">It is possible to control discovery-related information by using specific endpoints.</span></span> <span data-ttu-id="f24b1-129">Таким образом пользователь может указать, доступна ли конечная точка для обнаружения, а также пометить ее атрибутом <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> и добавить пользовательские XML-метаданные.</span><span class="sxs-lookup"><span data-stu-id="f24b1-129">That is, a user can control whether an endpoint can be discovered and the user can also mark that endpoint with <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> and custom XML metadata.</span></span> <span data-ttu-id="f24b1-130">Для этого необходимо добавить в конечную точку приложения свойство `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="f24b1-130">To do this, the user must add a `behaviorConfiguration` property to the application endpoint.</span></span> <span data-ttu-id="f24b1-131">В этом случае в конечную точку приложения добавляется следующее свойство.</span><span class="sxs-lookup"><span data-stu-id="f24b1-131">In this case, the following property is added to the application endpoint.</span></span>  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 <span data-ttu-id="f24b1-132">Теперь с помощью элемента конфигурации поведения можно управлять атрибутами, связанными с обнаружением.</span><span class="sxs-lookup"><span data-stu-id="f24b1-132">Now, through the behavior configuration element, you can control discovery-related attributes.</span></span> <span data-ttu-id="f24b1-133">В этом случае в конечную точку приложения добавляются две области.</span><span class="sxs-lookup"><span data-stu-id="f24b1-133">In this case, two scopes are added to the application endpoint.</span></span>  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
```  
  
 <span data-ttu-id="f24b1-134">Дополнительные сведения об областях см. в разделе [Обнаружение Find и FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="f24b1-134">For more information about scopes, see [Discovery Find and FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span></span>  
  
 <span data-ttu-id="f24b1-135">Можно также управлять определенными сведениями о конечной точке обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-135">You can also control specific details of the discovery endpoint.</span></span> <span data-ttu-id="f24b1-136">Это выполняется с помощью объекта <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span><span class="sxs-lookup"><span data-stu-id="f24b1-136">This is done through the <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span></span> <span data-ttu-id="f24b1-137">В данном образце изменяется версия используемого протокола, а также добавляется атрибут `maxResponseDelay`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="f24b1-137">In this sample, the version of the protocol used is modified as well as adding a `maxResponseDelay` attribute as shown in the following code example.</span></span>  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 <span data-ttu-id="f24b1-138">Далее приведен полный листинг файла конфигурации, используемого в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f24b1-138">The following is the complete configuration file used in this example:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->            
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client-configuration"></a><span data-ttu-id="f24b1-139">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="f24b1-139">Client Configuration</span></span>  
 <span data-ttu-id="f24b1-140">Для включения функции обнаружения в конфигурации приложения для клиента используется конечная точка `standardEndpoint` типа `dynamicEndpoint`, как показано в следующем фрагменте.</span><span class="sxs-lookup"><span data-stu-id="f24b1-140">In the application configuration file for the client, a `standardEndpoint` of type `dynamicEndpoint` is used to utilize discovery as shown in the following config snippet.</span></span>  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
```  
  
 <span data-ttu-id="f24b1-141">Если клиент использует конечную точку типа `dynamicEndpoint`, обнаружение осуществляется средой выполнения автоматически.</span><span class="sxs-lookup"><span data-stu-id="f24b1-141">When a client is using a `dynamicEndpoint`, the runtime performs discovery automatically.</span></span> <span data-ttu-id="f24b1-142">При обнаружении используются различные параметры, например те, которые определены в разделе `discoveryClientSettings`, задающем тип используемой конечной точки обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-142">Various settings are used during discovery, such as those defined in the  `discoveryClientSettings` section, which specifies the type of discovery endpoint to use:</span></span>  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 <span data-ttu-id="f24b1-143">Критерии поиска, используемые для поиска служб:</span><span class="sxs-lookup"><span data-stu-id="f24b1-143">The find criteria used to search for services:</span></span>  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
```  
  
 <span data-ttu-id="f24b1-144">Данный образец расширяет эту возможность и изменяет используемый клиентом объект <xref:System.ServiceModel.Discovery.FindCriteria>, а также некоторые свойства стандартной конечной точки `updDiscoveryEndpoint`, применяемой для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-144">This sample extends this feature and modifies the <xref:System.ServiceModel.Discovery.FindCriteria> used by the client, as well as some properties of the standard `updDiscoveryEndpoint` used for discovery.</span></span> <span data-ttu-id="f24b1-145">Измененный объект <xref:System.ServiceModel.Discovery.FindCriteria> использует область и указанный алгоритм `scopeMatchBy`, а также пользовательские критерии завершения.</span><span class="sxs-lookup"><span data-stu-id="f24b1-145">The <xref:System.ServiceModel.Discovery.FindCriteria> are modified to use a scope and a specific `scopeMatchBy` algorithm, as well as custom termination criteria.</span></span> <span data-ttu-id="f24b1-146">Кроме того, образец также показывает, как клиент может отправлять XML-элементы с помощью сообщений `Probe`.</span><span class="sxs-lookup"><span data-stu-id="f24b1-146">Furthermore, the sample also shows how a client can send XML elements using `Probe` messages.</span></span> <span data-ttu-id="f24b1-147">Наконец, вносятся некоторые изменения в конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>. В частности, меняется версия используемого протокола и параметры UDP, как показано в приведенном далее файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f24b1-147">Lastly, some changes are made to the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, such as the version of the protocol used and UDP-specific settings as shown in the following configuration file.</span></span>  
  
```xml  
<udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
```  
  
 <span data-ttu-id="f24b1-148">Далее приведен полный листинг конфигурации клиента для этого образца.</span><span class="sxs-lookup"><span data-stu-id="f24b1-148">The following is the complete client configuration used in the sample.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>        
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>     
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f24b1-149">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="f24b1-149">To use this sample</span></span>  
  
1. <span data-ttu-id="f24b1-150">В этом примере используются конечные точки HTTP и для запуска этого образца необходимо добавить соответствующие списки ACL URL-адресов. Дополнительные сведения см. в разделе [Настройка HTTP и HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) .</span><span class="sxs-lookup"><span data-stu-id="f24b1-150">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="f24b1-151">Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="f24b1-151">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="f24b1-152">Если команда не работает, следует указать домен и имя пользователя в следующих аргументах.</span><span class="sxs-lookup"><span data-stu-id="f24b1-152">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. <span data-ttu-id="f24b1-153">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="f24b1-153">Build the solution.</span></span>  
  
3. <span data-ttu-id="f24b1-154">Выполните исполняемый файл службы из каталога сборки.</span><span class="sxs-lookup"><span data-stu-id="f24b1-154">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="f24b1-155">Выполните исполняемый файл клиента.</span><span class="sxs-lookup"><span data-stu-id="f24b1-155">Run the client executable.</span></span> <span data-ttu-id="f24b1-156">Учтите, что клиент может определить расположение службы.</span><span class="sxs-lookup"><span data-stu-id="f24b1-156">Note that the client is able to locate the service.</span></span>  
