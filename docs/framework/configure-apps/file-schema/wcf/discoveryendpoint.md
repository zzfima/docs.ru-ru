---
title: '&lt;DiscoveryEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: b3254a1c3d7fa581b4f7573d693261f5a224515d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524173"
---
# <a name="ltdiscoveryendpointgt"></a>&lt;DiscoveryEndpoint&gt;

Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом обнаружения. При добавлении в конфигурацию службы указывает, где необходимо следить за появлением сообщений обнаружения. При добавлении в клиентскую конфигурацию указывает, куда необходимо отправлять запросы обнаружения.  
  
\<system.serviceModel>  
\<standardEndpoints >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты

| Атрибут        | Описание |  
| ---------------- | ----------- |  
| discoveryMode    | Строка, указывающая режим протокола обнаружения. Допустимые значения: «Adhoc» и «Managed». В управляемом режиме протокол использует прокси-сервер обнаружения, который выступает в качестве репозитория обнаруживаемых служб. Для режима Adhoc требуется, чтобы для поиска доступных служб протокол использовал многопоточный механизм UDP. Дополнительные сведения о свойстве см. в разделе <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>. |  
| discoveryVersion | Строка, указывающая одну из двух версий протокола WS-Discovery. Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005. Это значение имеет тип <xref:System.ServiceModel.Discovery.DiscoveryVersion>. |  
| maxResponseDelay | Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery будет ожидать перед отправкой определенных сообщений, например Probe Match или Resolve Match.<br /><br /> Если все сообщения ProbeMatches будут отправлены одновременно, может возникнуть перегрузка сети. Для ее предотвращения сообщения ProbeMatch отправляются с произвольной задержкой между сообщениями. Произвольная задержка находится в диапазоне от 0 до значения, заданного этим атрибутом. Если этот атрибут имеет значение 0, сообщения ProbeMatch отправляются одно за другим без задержки. В противном случае сообщения ProbeMatch отправляются с определенной произвольной задержкой так, что общее время на отправку всех сообщений ProbeMatch не превышает значение maxResponseDelay. Это значение действительно только для служб и не используется клиентами. |  
| `name`           | Строка, указывающая имя конфигурации стандартной конечной точки. Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией. |  
  
### <a name="child-elements"></a>Дочерние элементы

Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание: |  
| ------- | ----------- |  
| [\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными. |  
  
## <a name="example"></a>Пример

В следующем примере показано прослушивание службой сообщений об обнаружении по многоадресному протоколу транспорта peer net. В этом примере явно указана версия WS-Discovery April 2005.  
  
Конфигурация стандартной конечной точки определена для каждой службы и не может совместно использоваться между службами. Если нужно использовать такую же конечную точку обнаружения для другой службы, следует добавить такую же конфигурацию в раздел этой службы.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
