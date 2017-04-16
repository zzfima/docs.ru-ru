---
title: "&lt;serviceDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;serviceDiscovery&gt;
Указывает возможность обнаружения конечных точек службы.  
  
## Синтаксис  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="String”  
                        kind="Type" />  
        </announcementEndpoints>  
        <discoveryEndpoints>  
              <endpoint name="String”  
                        kind="Type" />  
        </discoveryEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Коллекция конечных точек объявления.  Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.|  
|[\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Коллекция конечных точек обнаружения.  Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## Заметки  
 При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.  Затем можно настроить функции обнаружения этих конечных точек с помощью дочерних элементов [\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md).  Раздел [\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) используется для настройки объявлений. Для этого укажите конфигурацию конечной точки, которая будет использована для отправки объявлений службы \(online\/Hello и offline\/Bye\).  Раздел [\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) используется, чтобы вручную указывать конечную точку, которая прослушивается на предмет сообщений об обнаружении.  
  
## Пример  
 В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.  
  
```  
  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
  ...  
  </service>  
</services>  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="udpEndpoint"  
                        kind="udpAnnouncementEndpoint" />  
        </announcementEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## См. также  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>