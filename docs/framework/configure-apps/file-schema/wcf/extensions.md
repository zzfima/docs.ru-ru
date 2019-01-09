---
title: '&lt;Расширения&gt;'
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: 1110c9790b3afd1af5c5947b4976cbaca88fd324
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146866"
---
# <a name="ltextensionsgt"></a>&lt;Расширения&gt;
Этот элемент конфигурации содержит коллекцию элементов XML, в которой находятся пользовательские метаданные, публикуемые вместе со стандартными обнаруживаемыми метаданными (EPR, ContractTypeName, BindingName, Scope и ListenURI). Далее приводится пример использования этого элемента конфигурации.  
  
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
      <endpointDiscovery enable="true">
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
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
