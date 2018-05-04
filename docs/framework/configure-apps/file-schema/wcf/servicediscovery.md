---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 78f1c7be1d8285cd2fdf79af1e1220a7e48b2893
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicediscoverygt"></a>&lt;serviceDiscovery&gt;
Указывает возможность обнаружения конечных точек службы.  
  
 \<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceDiscovery >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String" 
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String" 
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Коллекция конечных точек объявления. Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.|  
|[\<конечной точки discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Коллекция конечных точек обнаружения. Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми. Можно продолжить настройку функций обнаружения таких конечных точек с помощью [ \<конечной точки discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) или [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) дочерних элементов. Используйте [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) раздел, чтобы настроить объявления, указав конфигурацию конечной точки для использования для отправки извещения (online/Hello и вне сети или Bye). Используйте [ \<конечной точки discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) раздел, чтобы вручную указать конечную точку для прослушивания сообщений обнаружения.  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
