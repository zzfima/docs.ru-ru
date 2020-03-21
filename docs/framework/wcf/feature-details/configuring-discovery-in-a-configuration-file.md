---
title: Настройка обнаружения в файле конфигурации
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: b2e604f6168e4adff36bfb0c22861124743b358d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185330"
---
# <a name="configuring-discovery-in-a-configuration-file"></a>Настройка обнаружения в файле конфигурации
При обнаружении используются четыре основные группы параметров конфигурации. В этом разделе кратко описана каждая из них, а также приведены примеры их настройки. В конце каждого раздела имеется ссылка на более подробную документацию о каждой области.  
  
## <a name="behavior-configuration"></a>Конфигурация поведения  
 При обнаружении используется поведение служб и конечных точек. Поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> позволяет обнаруживать все конечные точки службы, а также указывать конечные точки объявлений.  В следующем примере показано, как добавить поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> и указать конечную точку объявления.  
  
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
  
 Как только вы укажете поведение, ссылайтесь на него из <`service`> элемент, как показано в следующем примере.  
  
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
  
 Чтобы обеспечить возможность обнаружения службы, также необходимо добавить конечную точку обнаружения. В рассмотренном выше примере добавляется стандартная конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
 При добавлении конечных точек объявления необходимо также `services` добавить службу слушателя объявления в <> элемент, показанный в следующем примере.  
  
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
  
 Поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> используется для включения или выключения обнаружения определенной конечной точки.  В следующем примере показана настройка двух конечных точек приложения для службы, одной со включенным обнаружением, другой ― с выключенным. Для каждой конечной точки добавляется поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.  
  
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
  
 Поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> можно также использовать для добавления пользовательских метаданных к метаданным конечной точки, возвращенным службой. В приведенном ниже примере показано, как это сделать.  
  
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
  
 Поведение <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> можно также использовать для добавления областей и типов, с помощью которых клиент выполняет поиск служб. В следующем примере показано, как задать это в файле конфигурации на стороне клиента.  
  
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
  
 Для получения <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> дополнительной <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> информации и [см.](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
  
## <a name="binding-element-configuration"></a>Настройка элемента привязки  
 Настройка элемента привязки представляет наибольший интерес на стороне клиента. С ее помощью можно указать критерии поиска, используемые для обнаружения служб из клиентского приложения WCF.  Следующий пример создает пользовательскую привязку с каналом <xref:System.ServiceModel.Discovery.DiscoveryClient> и указывает критерии поиска, включая тип и область. Кроме того, он также указывает значения для свойств <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> и <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.  
  
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
  
 На эту пользовательскую конфигурацию привязки должна ссылаться клиентская конечная точка.  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
    </client>  
```  
  
 Для получения дополнительной информации о критериях поиска см. [Поиск и поиск criteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md). Для получения дополнительной информации об обнаружении и связывающих элементах см., [Обзор обнаружения WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
  
## <a name="standard-endpoint-configuration"></a>Конфигурация стандартной конечной точки  
 Стандартные конечные точки - точки, имеющие значения по умолчанию одного или нескольких свойств (адрес, привязка или контракт), либо одно или несколько свойств, значения которых нельзя изменить. Платформа .NET 4 поставляется с тремя стандартными конечными точками, связанными с обнаружением: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> и <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  Конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> ― это стандартная конечная точка, настроенная для операций обнаружения через привязку для многоадресной рассылки. Конечная точка <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> ― это стандартная конечная точка, настроенная для отправки сообщений с объявлениями по привязке UDP. Конечная точка <xref:System.ServiceModel.Discovery.DynamicEndpoint> ― это стандартная конечная точка, которая использует обнаружение для динамического обнаружения адреса конечной точки во время выполнения.  Стандартные привязки `endpoint` указаны с <> элементом, содержащим вид атрибута, который определил тип стандартной конечной точки для добавления. В следующем примере демонстрируется, как добавить <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> и <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
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
  
 Стандартные конечные точки настроены в элемент <`standardEndpoints`>. В следующем примере показано, как настроить <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> и <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
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
  
 После добавления стандартной конфигурации конечных точек `endpoint` ссылка на конфигурацию в <> элементом для каждой конечной точки, как показано в следующем примере.  
  
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
  
 В отличие от других стандартных конечных точек, используемых при обнаружении, указывается привязка и контракт для <xref:System.ServiceModel.Discovery.DynamicEndpoint>. В следующем примере показано, как добавить и настроить <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  
  
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
  
 Для получения дополнительной информации о стандартных конечных точках [см.](standard-endpoints.md)
