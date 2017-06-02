---
title: "&lt;endpointDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;endpointDiscovery&gt;
Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.  
  
## Синтаксис  
  
```  
  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="String">  
      <endpointDiscovery enabled="Boolean">  
        <scopes>  
          <add scope="URI"/>  
        </scopes>  
        <extensions>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|enabled|Логическое значение, указывающее, включена ли для этой конечной точки возможность обнаружения.  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Коллекция URI областей для этой конечной точки.  С одной конечной точкой можно связать несколько URI областей.|  
|[\<расширения\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) \[из \<обнаружение\_конечной\_точки\>\]|Коллекция элементов XML, позволяющая указывать пользовательские метаданные, публикуемые для конечной точки.|  
|\<типы\>|Коллекция интерфейсов, которые нужно найти.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
|||  
  
## Заметки  
 Если добавить этот элемент конфигурации в конфигурацию поведения конечной точки и присвоить атрибуту `enabled` значение `true`, то будет включена возможность обнаружения.  Кроме того, можно использовать дочерний элемент [\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)[\<расширения\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) для указания пользовательских метаданных, которые требуется опубликовать вместе со стандартными обнаруживаемыми метаданными \(EPR, ContractTypeName, BindingName, Scope и ListenURI\).  
  
 Этот элемент конфигурации зависит от элемента [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md), который обеспечивает управление возможностью обнаружения на уровне службы.  Это значит, что параметры этого элемента пропускаются, если в конфигурации не указан [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md).  
  
## Пример  
 В следующем примере конфигурации определены области фильтрации и метаданные расширения, которые будут опубликованы для конечной точки.  
  
```  
  
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
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
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
  
## См. также  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>