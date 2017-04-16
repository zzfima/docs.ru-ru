---
title: "&lt;announcementEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;announcementEndpoint&gt;
Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом объявления.  Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы.  Служба [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] указывает конечные точки объявления в элементе [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) и использует AnnouncementClient для выполнения объявлений.  Клиент, ожидающий объявления от другой службы, фактически выступает в качестве службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]; таким образом, необходимо настроить конечные точки объявления для этого клиента в разделе [\<службы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md).  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <announcementEndpoint>   
          <standardEndpoint  
                  discoveryVersion=”WSDiscovery11/WSDiscoveryApril2005”  
                  maxAnnouncementDelay=”Timespan”   
                  name="String" />   
       </announcementEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|discoveryVersion|Строка, указывающая одну из двух версий протокола WS\-Discovery.  Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.  Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.DiscoveryVersion>.|  
|maxAnnouncementDelay|Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.  Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.  Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.|  
|имя|Строка, указывающая имя конфигурации стандартной конечной точки.  Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Коллекция стандартных конечных точек, одно или несколько свойств которых \(адрес, привязка, контракт\) являются фиксированными.|  
  
## Пример  
 В следующем примере показано прослушивание клиентом сообщений с объявлениями по протоколам http и peernet.  
  
```  
  
<services>  
  <service name="ServiceAnnouncementListener">  
              <endpoint name="httpAnnouncementEndpoint"  
                        kind="announcementEndpoint"  
                        binding="basicHttpBinding"  
                        address="announcements" />  
              <endpoint name="peerNetAnnouncementEndpoint"  
                        kind="announcementEndpoint"  
                        binding="peerTcpBinding"  
                        address="net.p2p://discoveryMesh/multicast"  
                        bindingConfiguration="discoveryPeerTcpBindingConfig" />  
  ...  
  </service>  
</services>  
  
<standardEndpoints>  
  <announcementEndpoint>  
     <standardEndpoint name="httpAnnouncementEndpoint"                         
                       version="WSDiscoveryApril2005" />  
     <standardEndpoint name="peerNetAnnouncementEndpoint"                         
                       version="WSDiscoveryApril2005" />  
   </announcementEndpoint>  
</standardEndpoints>  
  
```  
  
## См. также  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>