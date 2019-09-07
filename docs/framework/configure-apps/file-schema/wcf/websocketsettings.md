---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 80784f40130e572ae374bd9b26e701360dbfcaa5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399137"
---
# <a name="websocketsettings"></a>\<Вебсоккетсеттингс >
Элемент конфигурации, который служит для задания параметров веб-сокета.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Вебсоккетсеттингс >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|createNotificationOnConnection|Определяет, следует ли отправлять уведомления при соединении.|  
|disablePayloadMasking|Определяет, отключено ли маскирование веб-сокета.|  
|keepAliveInterval|Определяет интервал поддержки активности канала.|  
|maxPendingConnections|Определяет максимальное число подключений, ожидающих распределения в службе.|  
|receiveBufferSize|Определяет размер буфера приема.|  
|sendBufferSize|Определяет размер буфера отправки.|  
|subProtocol|Определяет подпротокол веб-сокета.|  
|transportUsage|Указывает, когда использовать веб-сокеты.|  
  
## <a name="transportusage-attribute"></a>Атрибут transportUsage  
  
|Значение|Описание|  
|-----------|-----------------|  
|WhenDuplex|Использовать протокол веб-сокета, если контракт является дуплексным.|  
|Всегда|Всегда использовать протокол веб-сокетов независимо от контракта.|  
|Никогда|Никогда не использовать протокол веб-сокетов.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|\<netHttpBinding >|Определяет привязку NetHttpBinding|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, \<как использовать элемент > вебсоккетсеттингс.  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
