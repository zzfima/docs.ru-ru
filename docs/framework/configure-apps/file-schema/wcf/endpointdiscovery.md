---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: effceee30abdaa1725b8c8718df22632961871e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266420"
---
# <a name="endpointdiscovery"></a>\<endpointDiscovery>
Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.  
  
\<system.ServiceModel>  
\<варианты поведения >  
\<endpointBehaviors>  
\<поведение >  
\<endpointDiscovery>  
  
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
|enabled|Логическое значение, указывающее, включена ли возможность обнаружения этой конечной точки. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<области >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Коллекция URI областей для этой конечной точки. С одной конечной точкой можно связать несколько URI областей.|  
|[\<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [из \<endpointDiscovery >]|Коллекция элементов XML, позволяющая указывать пользовательские метаданные, публикуемые для конечной точки.|  
|\<типы >|Коллекция интерфейсов, которые нужно найти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
|||  
  
## <a name="remarks"></a>Примечания  
 Если добавить этот элемент конфигурации в конфигурацию поведения конечной точки и присвоить атрибуту `enabled` значение `true`, то будет включена возможность обнаружения. Кроме того, можно использовать [ \<области >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)дочерний элемент для указания пользовательских областей URI, который может использоваться для фильтрации конечных точек службы во время выполнения запроса, а также [ \<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) дочерний элемент для указания пользовательских метаданных, которые требуется опубликовать вместе со стандартными обнаруживаемыми метаданными (EPR, ContractTypeName, BindingName, Scope и ListenURI).  
  
 Этот элемент конфигурации зависит от [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) элемент, который управляет уровнем обслуживания для обнаружения. Это означает, что параметры этого элемента пропускаются, если [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) не присутствует в конфигурации.  
  
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
