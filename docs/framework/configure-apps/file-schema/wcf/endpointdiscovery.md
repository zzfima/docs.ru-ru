---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 5cb64c54067ba695f67d86c0026db77ebbe7d5ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919053"
---
# <a name="endpointdiscovery"></a>\<Ендпоинтдисковери >
Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.  
  
\<системой. > ServiceModel  
\<> поведения  
\<endpointBehaviors >  
\<> поведения  
\<Ендпоинтдисковери >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Логическое значение, указывающее, включена ли возможность обнаружения в этой конечной точке. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<области >](scopes.md)|Коллекция URI областей для этой конечной точки. С одной конечной точкой можно связать несколько URI областей.|  
|расширения > [из \<ендпоинтдисковери >] [ \<](extensions.md)|Коллекция элементов XML, позволяющая указывать пользовательские метаданные, публикуемые для конечной точки.|  
|\<типы >|Коллекция интерфейсов, которые нужно найти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> поведения](behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
|||  
  
## <a name="remarks"></a>Примечания  
 Если добавить этот элемент конфигурации в конфигурацию поведения конечной точки и присвоить атрибуту `enabled` значение `true`, то будет включена возможность обнаружения. Кроме того, можно использовать [ \<](scopes.md)дочерний элемент области > для указания URI настраиваемых областей, которые можно использовать для фильтрации конечных точек службы во время запроса, [ \<а также расширения >](extensions.md) дочернего элемента для указания пользовательского метаданные, которые должны быть опубликованы вместе со стандартными обнаруживаемыми метаданными (EPR, Контракттипенаме, Биндингнаме, Scope и ListenURI).  
  
 Этот элемент конфигурации зависит [ \<от элемента сервицедисковери >](servicediscovery.md) , который обеспечивает контроль уровня обслуживания для обнаружения. Это означает, что параметры этого элемента не учитываются, если [ \<сервицедисковери >](servicediscovery.md) отсутствует в конфигурации.  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации определены области фильтрации и метаданные расширения, которые будут опубликованы для конечной точки.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
