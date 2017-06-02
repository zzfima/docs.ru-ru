---
title: "&lt;webSocketSettings&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;webSocketSettings&gt;
Элемент конфигурации, который служит для задания параметров веб\-сокета.  
  
## Синтаксис  
  
```  
  
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
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|createNotificationOnConnection|Определяет, следует ли отправлять уведомления при соединении.|  
|disablePayloadMasking|Определяет, отключено ли маскирование веб\-сокета.|  
|keepAliveInterval|Определяет интервал поддержки активности канала.|  
|maxPendingConnections|Определяет максимальное число подключений, ожидающих распределения в службе.|  
|receiveBufferSize|Определяет размер буфера приема.|  
|sendBufferSize|Определяет размер буфера отправки.|  
|subProtocol|Определяет подпротокол веб\-сокета.|  
|transportUsage|Указывает, когда использовать веб\-сокеты.|  
  
## Атрибут transportUsage  
  
|Значение|Описание|  
|--------------|--------------|  
|WhenDuplex|Использовать протокол веб\-сокета, если контракт является дуплексным.|  
|Всегда|Всегда использовать протокол веб\-сокетов независимо от контракта.|  
|Никогда|Никогда не использовать протокол веб\-сокетов.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|\<netHttpBinding\>|Определяет привязку NetHttpBinding|  
  
## Пример  
 В следующем примере показано использование элемента \<webSocketSettings\>.  
  
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
  
## См. также  
 <xref:System.ServiceModel.Channels.Binding>   
 <xref:System.ServiceModel.Channels.BindingElement>   
 <xref:System.ServiceModel.BasicHttpBinding>   
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)