---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: e6e567e8a657b4c1683ae4abfb14f96a0f272e4a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934579"
---
# <a name="udpdiscoveryendpoint"></a>\<Удпдисковерендпоинт >
Этот элемент конфигурации указывает стандартную конечную точку, которая стандартно используется для операций обнаружения через привязку для многоадресной рассылки UDP. Эта конечная точка имеет фиксированный контракт и поддерживает две версии протокола WS-Discovery. Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1).  
  
 \<системой. > ServiceModel  
\<Стандардендпоинтс >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|discoveryMode|Строка, указывающая режим протокола обнаружения. Допустимые значения: "нерегламентированный" и "управляемый". В управляемом режиме протокол использует прокси-сервер обнаружения, который выступает в качестве репозитория обнаруживаемых служб. Для режима Adhoc требуется, чтобы для поиска доступных служб протокол использовал многопоточный механизм UDP. Это значение имеет тип <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.|  
|discoveryVersion|Строка, указывающая одну из двух версий протокола WS-Discovery. Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005. Это значение имеет тип <xref:System.ServiceModel.Discovery.DiscoveryVersion>.|  
|maxResponseDelay|Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery будет ожидать перед отправкой определенных сообщений, например Probe Match или Resolve Match.<br /><br /> Если все сообщения ProbeMatches будут отправлены одновременно, может возникнуть перегрузка сети. Для ее предотвращения сообщения ProbeMatch отправляются с произвольной задержкой между сообщениями. Произвольная задержка находится в диапазоне от 0 до значения, заданного этим атрибутом. Если этот атрибут имеет значение 0, сообщения ProbeMatch отправляются одно за другим без задержки. В противном случае сообщения ProbeMatch отправляются с определенной произвольной задержкой так, что общее время на отправку всех сообщений ProbeMatch не превышает значение maxResponseDelay. Это значение действительно только для служб и не используется клиентами.|  
|multicastAddress|URI, в котором указывается адрес многоадресной рассылки, используемый для отправки и получения сообщений об обнаружении. Значением по умолчанию является многопоточный адрес, который соответствует спецификации протокола.|  
|`name`|Строка, указывающая имя конфигурации стандартной конечной точки. Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Удптранспортсеттингс >](udptransportsettings.md)|Коллекция параметров, которые позволят настроить транспорт UDP для конечной точки UDP.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Стандардендпоинтс >](standardendpoints.md)|Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано прослушивание сообщений об обнаружении через многоадресный протокол UDP.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
