---
title: "&lt;tcpTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;tcpTransport&gt;
Определяет транспорт TCP, который может использоваться каналом для передачи сообщений для пользовательской привязки.  
  
## Синтаксис  
  
```  
  
<tcpTransport   
    listenBacklog="Integer"  
        portSharingEnabled="Boolean"  
    teredoEnabled="Boolean"  
    transferMode=”Buffered/Streamed”  
        <connectionPoolSettings  
          groupName=”String”  
        idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|channelInitializationTimeout|Максимальное время в секундах, в течение которого канал может находиться в состоянии инициализации, прежде чем будет отключен.  Эта квота включает время соединения TCP, которое может занять проверка подлинности с помощью протокола кадрирования сообщений .Net.  Клиенту необходимо отправить некоторые исходные данные, прежде чем сервер получит достаточно сведений для аутентификации.  По умолчанию используется значение 30 секунд.|  
|listenBacklog|Максимальное количество запросов на соединение в очереди, которые могут ожидать обработки веб\-службой.  Атрибут `connectionLeaseTimeout` ограничивает время ожидания подключения клиентом до создания исключения подключения.  Это свойство уровня сокетов, которое определяет максимальное количество запросов на подключение в очереди, которые могут ожидать обработки веб\-службой.  Когда значение ListenBacklog слишком мало, служба WCF останавливает прием запросов и сбрасывает новые соединения до тех пор, пока сервер не подтвердит некоторые из соединений, помещенных в очередь. Значение по умолчанию \- 16 \* число процессоров.|  
|portSharingEnabled|Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.  Если атрибут имеет значение `false`, каждая привязка будет использовать уникальный порт.  Значение по умолчанию — `false`.<br /><br /> Этот параметр действителен только для служб.  Клиенты не затрагиваются.<br /><br /> Использование этого параметра требует включения службы общего доступа к портам TCP Windows Communication Foundation \(WCF\) путем изменения типа запуска на «Вручную» или «Авто».|  
|teredoEnabled|Логическое значение, указывающее, используется ли Teredo \(технология адресации клиентов, защищенных брандмауэром\).  Значение по умолчанию — `false`.<br /><br /> Это свойство включает использование Teredo для базового сокета TCP.  Дополнительные сведения см. в разделе [Обзор Teredo](http://go.microsoft.com/fwlink/?LinkId=95339).<br /><br /> Это свойство применимо только к [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] и [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)].  [!INCLUDE[wv](../../../../../includes/wv-md.md)] имеет параметр конфигурации Teredo на уровне компьютера, поэтому в ОС Vista это свойство пропускается.  Для Teredo необходимо, чтобы на компьютере, где работает служба, и на компьютере\-клиенте был установлен и настроен правильно для использования Teredo стек протокола Microsoft IPv6.  Дополнительные сведения о настройке Teredo см. в разделе [Обзор Teredo](http://go.microsoft.com/fwlink/?LinkId=95339).  Дополнительные сведения см. на сайте [Windows Server 2003 Technology Centers](http://go.microsoft.com/fwlink/?LinkId=49888).|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Этот транспорт использует универсальные коды ресурсов \(URI\) вида net.tcp:\/\/hostname:port\/path.  Другие элементы универсального кода ресурса \(URI\) не обязательны.  
  
 Элемент `tcpTransport` является начальной точкой для создания пользовательской привязки, реализующей транспортный протокол TCP.  Этот транспорт оптимизирован для взаимодействия между службами WCF.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>   
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Выбор транспортов](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)