---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: e5f34dca83c8d3d08d27fb72bee5af2a89ac6b9f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511918"
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
Элемент конфигурации, который служит для задания параметров веб-сокета.  
  
\<система. ServiceModel >  
\<привязки >  
\<netHttpBinding >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
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
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|\<netHttpBinding >|Определяет привязку NetHttpBinding|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать \<webSocketSettings > элемента.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки службы Windows Communication Foundation и клиентов](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
