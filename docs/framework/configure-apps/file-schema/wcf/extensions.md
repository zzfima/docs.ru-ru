---
title: '&lt;Расширения&gt;'
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: 9589eaf8ee133f0be670782574dfd30272f29b45
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556354"
---
# <a name="ltextensionsgt"></a><span data-ttu-id="899d2-102">&lt;Расширения&gt;</span><span class="sxs-lookup"><span data-stu-id="899d2-102">&lt;extensions&gt;</span></span>
<span data-ttu-id="899d2-103">Этот элемент конфигурации содержит коллекцию элементов XML, в которой находятся пользовательские метаданные, публикуемые вместе со стандартными обнаруживаемыми метаданными (EPR, ContractTypeName, BindingName, Scope и ListenURI).</span><span class="sxs-lookup"><span data-stu-id="899d2-103">This configuration element contains a collection of XML elements that contain custom metadata to be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span> <span data-ttu-id="899d2-104">Далее приводится пример использования этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="899d2-104">The following is an example of using this configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="899d2-105">См. также</span><span class="sxs-lookup"><span data-stu-id="899d2-105">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
