---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 1ad05fd9125ecc8b3d5797e0dd335adbf808db84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933840"
---
# <a name="peertransport"></a>\<Пиртранспорт >
Определяет одноранговый транспорт для пользовательской привязки.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Пиртранспорт >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|listenIpAddress|Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения. Значение по умолчанию — `null`.|  
|maxBufferPoolSize|Положительное целое число, указывающее максимальный размер буферного пула. Значение по умолчанию — 524288.<br /><br /> Многие элементы WCF используют буферы. При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов. Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется. Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|maxReceivedMessageSize|Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки. Отправитель сообщения получает ошибку протокола SOAP, когда размер сообщения оказывается слишком большим для получателя. Получатель отклоняет сообщение и создает запись о событии в журнале трассировки. Значение по умолчанию — 65536.|  
|порт|Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала. Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>. Значение по умолчанию — 0.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-peertransport.md)|Определяет параметры безопасности для данного транспорта. Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Данный транспорт нельзя использовать с контрактами, имеющими операции запроса-ответа.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспорта](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
