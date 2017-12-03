---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71ed2fc6e4e5407cdf8c3e2334dcc0c16a00cf83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
Элемент конфигурации, который служит для задания параметров веб-сокета.  
  
\<система. ServiceModel >  
\<привязки >  
\<Привязка netHttpBinding >  
  
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
|\<Привязка netHttpBinding >|Определяет привязку NetHttpBinding|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать \<webSocketSettings > элемент.  
  
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
 [Использование привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
