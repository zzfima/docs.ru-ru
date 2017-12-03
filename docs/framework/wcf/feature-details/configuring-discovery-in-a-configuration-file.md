---
title: "Настройка обнаружения в файле конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42f86762bf40f5c8358b8772548c082844eae1ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-discovery-in-a-configuration-file"></a><span data-ttu-id="9eed5-102">Настройка обнаружения в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="9eed5-102">Configuring Discovery in a Configuration File</span></span>
<span data-ttu-id="9eed5-103">При обнаружении используются четыре основные группы параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9eed5-103">There are four major groups of configuration settings used in discovery.</span></span> <span data-ttu-id="9eed5-104">В этом разделе кратко описана каждая из них, а также приведены примеры их настройки.</span><span class="sxs-lookup"><span data-stu-id="9eed5-104">This topic will briefly describe each and show examples of how to configure them.</span></span> <span data-ttu-id="9eed5-105">В конце каждого раздела имеется ссылка на более подробную документацию о каждой области.</span><span class="sxs-lookup"><span data-stu-id="9eed5-105">Following each section will be a link to more in-depth documentation about each area.</span></span>  
  
## <a name="behavior-configuration"></a><span data-ttu-id="9eed5-106">Конфигурация поведения</span><span class="sxs-lookup"><span data-stu-id="9eed5-106">Behavior Configuration</span></span>  
 <span data-ttu-id="9eed5-107">При обнаружении используется поведение служб и конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9eed5-107">Discovery uses service behaviors and endpoint behaviors.</span></span> <span data-ttu-id="9eed5-108">Поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> позволяет обнаруживать все конечные точки службы, а также указывать конечные точки объявлений.</span><span class="sxs-lookup"><span data-stu-id="9eed5-108">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> behavior enables discovery for all of a service’s endpoints and allows you to specify announcement endpoints.</span></span>  <span data-ttu-id="9eed5-109">В следующем примере показано, как добавить поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> и указать конечную точку объявления.</span><span class="sxs-lookup"><span data-stu-id="9eed5-109">The following example shows how to add the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and specify an announcement endpoint.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
```  
  
 <span data-ttu-id="9eed5-110">Указав поведение, установите на него ссылку из элемента <`service`>, как показано в следующем образце.</span><span class="sxs-lookup"><span data-stu-id="9eed5-110">Once you specify the behavior, reference it from a <`service`> element as shown in the following sample.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
         <!-- Application Endpoint -->  
         <endpoint address="endpoint0"  
                   binding="basicHttpBinding"  
                   contract="IHelloWorldService" />  
         <!-- Discovery Endpoints -->  
         <endpoint kind="udpDiscoveryEndpoint" />  
        </service>  
    </service>  
```  
  
 <span data-ttu-id="9eed5-111">Чтобы обеспечить возможность обнаружения службы, также необходимо добавить конечную точку обнаружения. В рассмотренном выше примере добавляется стандартная конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-111">In order for a service to be discoverable, you must also add a discovery endpoint, the example above adds a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard endpoint.</span></span>  
  
 <span data-ttu-id="9eed5-112">При добавлении конечных точек объявления также необходимо добавить службу прослушивания объявления в элемент <`services`>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9eed5-112">When you add announcement endpoints you must also add an announcement listener service to the <`services`> element as shown in the following example.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
      <!-- Application Endpoint -->  
      <endpoint address="endpoint0"  
                binding="basicHttpBinding"  
                contract="IHelloWorldService" />  
      <!-- Discovery Endpoints -->  
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <!-- Announcement Listener Configuration -->  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
```  
  
 <span data-ttu-id="9eed5-113">Поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> используется для включения или выключения обнаружения определенной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9eed5-113">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is used to enable or disable discovery of a specific endpoint.</span></span>  <span data-ttu-id="9eed5-114">В следующем примере показана настройка двух конечных точек приложения для службы, одной со включенным обнаружением, другой ― с выключенным.</span><span class="sxs-lookup"><span data-stu-id="9eed5-114">The following example configures a service with two application endpoints, one with discovery enabled and one with discovery disabled.</span></span> <span data-ttu-id="9eed5-115">Для каждой конечной точки добавляется поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-115">For each endpoint an <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is added.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService"  
               behaviorConfiguration="helloWorldServiceBehavior">  
  
        <!-- Application Endpoints -->  
        <endpoint address="endpoint0"  
                 binding="basicHttpBinding"  
                 contract="IHelloWorldService"   
                 behaviorConfiguration="ep0Behavior" />  
  
        <endpoint address="endpoint1"  
                  binding="basicHttpBinding"  
                  contract="IHelloWorldService"  
                  behaviorConfiguration="ep1Behavior" />  
  
        <!-- Discovery Endpoints -->  
        <endpoint kind="udpDiscoveryEndpoint" />  
      </service>  
   </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery />  
        </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="ep0Behavior">  
          <endpointDiscovery enabled="true"/>  
        </behavior>  
        <behavior name="ep1Behavior">  
          <endpointDiscovery enabled="false"/>  
        </behavior>  
     </endpointBehaviors>  
   </behaviors>  
```  
  
 <span data-ttu-id="9eed5-116">Поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> можно также использовать для добавления пользовательских метаданных к метаданным конечной точки, возвращенным службой.</span><span class="sxs-lookup"><span data-stu-id="9eed5-116">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add custom metadata to the endpoint metadata returned by the service.</span></span> <span data-ttu-id="9eed5-117">Следующий пример показывает, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="9eed5-117">The following example shows how to do this.</span></span>  
  
```xml  
<behavior name="ep4Behavior">  
   <endpointDiscovery enabled="true">  
      <extensions>  
         <CustomMetadata>This is custom metadata.</CustomMetadata>  
         <d:Types xmlns:d="http://schemas.xmlsoap.org/ws/2005/04/discovery" xmlns:i="http://printer.example.org/2003/imaging">i:PrintBasic</d:Types>  
         <CustomMetadata netsted="true">  
            <NestedMetadata>This is a nested custom metadata.</NestedMetadata>  
         </CustomMetadata>  
      </extensions>  
   </endpointDiscovery>  
</behavior>  
```  
  
 <span data-ttu-id="9eed5-118">Поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> можно также использовать для добавления областей и типов, с помощью которых клиент выполняет поиск служб.</span><span class="sxs-lookup"><span data-stu-id="9eed5-118">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add scopes and types that clients use to search for services.</span></span> <span data-ttu-id="9eed5-119">В следующем примере показано, как задать это в файле конфигурации на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="9eed5-119">The following example shows how to do this in a client side configuration file.</span></span>  
  
```xml  
<behavior name="ep2Behavior">  
   <endpointDiscovery enabled="true">  
      <scopes>  
         <add scope="http://www.microsoft.com/building42/floor1"/>  
         <add scope="ldap:///ou=engineeringo=examplecomc=us"/>  
      </scopes>  
      <types>  
         <add name="test" namespace="http://example.microsoft.com/" />  
         <add name="additionalContract" namespace="http://example.microsoft.com/" />  
      </types>  
   </endpointDiscovery>  
</behavior>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9eed5-120"><xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> и <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> разделе [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9eed5-120"> <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> see [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span></span>  
  
## <a name="binding-element-configuration"></a><span data-ttu-id="9eed5-121">Настройка элемента привязки</span><span class="sxs-lookup"><span data-stu-id="9eed5-121">Binding Element Configuration</span></span>  
 <span data-ttu-id="9eed5-122">Настройка элемента привязки представляет наибольший интерес на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="9eed5-122">Binding element configuration is most interesting on the client side.</span></span> <span data-ttu-id="9eed5-123">С ее помощью можно указать критерии поиска, используемые для обнаружения служб из клиентского приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="9eed5-123">You can use configuration to specify the find criteria used to discover services from a WCF client application.</span></span>  <span data-ttu-id="9eed5-124">Следующий пример создает пользовательскую привязку с каналом <xref:System.ServiceModel.Discovery.DiscoveryClient> и указывает критерии поиска, включая тип и область.</span><span class="sxs-lookup"><span data-stu-id="9eed5-124">The following example creates a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClient> channel and specifies find criteria that includes a type and scope.</span></span> <span data-ttu-id="9eed5-125">Кроме того, он также указывает значения для свойств <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> и <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-125">In addition it specifies values for the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> and <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> properties.</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <!-- Binding Configuration for the Application Endpoint -->  
      <binding name="discoBindingConfiguration">  
         <discoveryClient>  
            <endpoint kind="discoveryEndpoint"  
                      address="http://localhost:8000/ConfigTest/Discovery"  
                      binding="customBinding"  
                      bindingConfiguration="httpSoap12WSAddressing10"/>  
            <findCriteria duration="00:00:10" maxResults="2">  
              <types>  
                <add name="IHelloWorldService"/>  
              </types>  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>              
            </findCriteria>  
          </discoveryClient>  
          <textMessageEncoding messageVersion="Soap11"/>  
          <httpTransport />  
        </binding>  
```  
  
 <span data-ttu-id="9eed5-126">На эту пользовательскую конфигурацию привязки должна ссылаться клиентская конечная точка.</span><span class="sxs-lookup"><span data-stu-id="9eed5-126">This custom binding configuration must be referenced by a client endpoint:</span></span>  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
    </client>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9eed5-127">найти условия в разделе [найти обнаружения и FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="9eed5-127"> find criteria see [Discovery Find and FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9eed5-128">просмотреть элементы обнаружения и привязки, [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9eed5-128"> discovery and binding elements see, [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)</span></span>  
  
## <a name="standard-endpoint-configuration"></a><span data-ttu-id="9eed5-129">Конфигурация стандартной конечной точки</span><span class="sxs-lookup"><span data-stu-id="9eed5-129">Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="9eed5-130">Стандартные конечные точки - точки, имеющие значения по умолчанию одного или нескольких свойств (адрес, привязка или контракт), либо одно или несколько свойств, значения которых нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="9eed5-130">Standard endpoints are predefined endpoints that have default values for one or more properties (address, binding, or contract) or one or more property values that cannot change.</span></span> <span data-ttu-id="9eed5-131">Платформа .NET 4 поставляется с тремя стандартными конечными точками, связанными с обнаружением: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> и <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-131">.NET 4 ships with 3 discovery related standard endpoints: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, and <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  <span data-ttu-id="9eed5-132">Конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> ― это стандартная конечная точка, настроенная для операций обнаружения через привязку для многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="9eed5-132">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="9eed5-133">Конечная точка <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> ― это стандартная конечная точка, настроенная для отправки сообщений с объявлениями по привязке UDP.</span><span class="sxs-lookup"><span data-stu-id="9eed5-133">The <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> is a standard endpoint that is pre-configured to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="9eed5-134">Конечная точка <xref:System.ServiceModel.Discovery.DynamicEndpoint> ― это стандартная конечная точка, которая использует обнаружение для динамического обнаружения адреса конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9eed5-134">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint that uses discovery to find the endpoint address of a discovered service dynamically at runtime.</span></span>  <span data-ttu-id="9eed5-135">Стандартные привязки задаются элементом <`endpoint`>, который содержит атрибут типа, указывающий тип добавляемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9eed5-135">Standard bindings are specified with an <`endpoint`> element that contains kind attribute that specified the type of standard endpoint to add.</span></span> <span data-ttu-id="9eed5-136">В следующем примере демонстрируется, как добавить <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> и <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-136">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->          
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>  
```  
  
 <span data-ttu-id="9eed5-137">Стандартные конечные точки настраиваются в элементе< `standardEndpoints`>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-137">Standard endpoints are configured in a <`standardEndpoints`> element.</span></span> <span data-ttu-id="9eed5-138">В следующем примере показано, как настроить <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> и <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-138">The following example shows how to configure the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and the <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
```xml  
<standardEndpoints>  
      <udpAnnouncementEndpoint>  
        <standardEndpoint   
            name="udpAnnouncementEndpointSettings"   
            multicastAddress="soap.udp://239.255.255.250:3703"    
            maxAnnouncementDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="1028"  
            maxPendingMessageCount="10"  
            maxMulticastRetransmitCount="3"  
            maxUnicastRetransmitCount="2"  
            socketReceiveBufferSize="131072"  
            timeToLive="2" />  
        </standardEndpoint>  
      </udpAnnouncementEndpoint>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
            name="udpDiscoveryEndpointSettings"  
            multicastAddress="soap.udp://239.255.255.252:3704"  
            maxResponseDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="2048"  
            maxPendingMessageCount="5"  
            maxReceivedMessageSize="8192"  
            maxBufferPoolSize="262144"/>  
        </standardEndpoint>  
      </udpDiscoveryEndpoint>  
```  
  
 <span data-ttu-id="9eed5-139">После добавления конфигурации стандартной конечной точки укажите ссылку на нее в элементе <`endpoint`> для каждой конечной точки, как показано в следующем образце.</span><span class="sxs-lookup"><span data-stu-id="9eed5-139">Once you’ve added the standard endpoint configuration, reference the configuration in the <`endpoint`> element for each endpoint as shown in the following sample.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->          
      <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="udpDiscoveryEndpointSettings"/>  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" endpointConfiguration="udpAnnouncementEndpointSettings" >  
   </service>  
</services>  
```  
  
 <span data-ttu-id="9eed5-140">В отличие от других стандартных конечных точек, используемых при обнаружении, указывается привязка и контракт для <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-140">Unlike the other standard endpoints used in discovery, you specify a binding and contract for <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span> <span data-ttu-id="9eed5-141">В следующем примере показано, как добавить и настроить <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="9eed5-141">The following example shows how to add and configure a <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <endpoint kind="dynamicEndpoint" binding="basicHttpBinding" contract="IHelloWorldService" endpointConfiguration="dynamicEndpointConfiguration" />  
    </client>   
   <standardEndpoints>  
      <dynamicEndpoint>  
         <standardEndpoint name="dynamicEndpointConfiguration">  
             <discoveryClientSettings>  
              <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="2">  
                 <types>  
                   <add name="IHelloWorldService"/>  
                 </types>  
                 <scopes>  
                   <add scope="http://www.microsoft.com/building42/floor1"/>  
                 </scopes>  
                 <extensions>  
                   <CustomMetadata>This is custom metadata.</CustomMetadata>          
                 </extensions>  
               </findCriteria>  
             </discoveryClientSettings>  
           </standardEndpoint>  
         </dynamicEndpoint>  
   </standardEndpoints>  
</system.ServiceModel>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9eed5-142">Стандартные конечные точки в разделе [стандартные конечные точки](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="9eed5-142"> standard endpoints see [Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)</span></span>
