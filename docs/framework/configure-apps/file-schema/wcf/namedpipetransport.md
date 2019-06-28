---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 819639eabf0332a34d6a7250159d24e42552f874
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423092"
---
# <a name="namedpipetransport"></a>\<namedPipeTransport >
Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.  
  
\<system.serviceModel>  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<namePipeTransport>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|ChannelInitializationTimeout|Возвращает или задает <xref:System.TimeSpan> , определяет максимальное время канал может находиться в состоянии инициализации перед отключением.|  
|ConnectionBufferSize|Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.|  
|hostNameComparisonMode|Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).|  
|manualAddressing|Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.|  
|maxBufferPoolSize|Получает или задает максимальный размер в байтах, буферных пулов, используемых транспортом.|  
|maxBufferSize|Возвращает или задает максимальный размер используемого буфера. Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.|  
|maxOutputDelay|Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.|  
|maxPendingAccepts|Возвращает или задает максимальное число каналов, служба может иметь ожидающих на прослушивателе для обработки входящих подключений к службе.|  
|maxPendingConnections|Возвращает или задает максимальное число подключений, ожидающих распределения в службе.|  
|maxReceivedMessageSize|Возвращает и задает максимально допустимый размер сообщения, в байтах, которые могут быть получены.|  
|transferMode|Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.|  
|[\<connectionPoolSettings > из \<namedPipeTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|Задает дополнительные параметры пула подключений для привязки именованного канала.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path. Другие элементы универсального кода ресурса (URI) не обязательны.  
  
Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS. Этот транспорт используется для взаимодействия служб WCF на компьютере.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Выбор транспорта](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
