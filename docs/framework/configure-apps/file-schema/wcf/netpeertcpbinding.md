---
title: "&lt;netPeerTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "netPeerBinding, элемент"
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# &lt;netPeerTcpBinding&gt;
Определяет привязку для обмена TCP\-сообщениями через одноранговый канал.  
  
## Синтаксис  
  
```  
  
<netPeerBinding>  
    <binding name="string"  
         closeTimeout="TimeSpan"  
         openTimeout="TimeSpan"   
         receiveTimeout="TimeSpan"  
         sendTimeout="TimeSpan"  
         listenIPAddress="String"  
          maxBufferPoolSize="integer"  
         maxReceiveMessageSize="Integer"   
         port="Integer"  
         <security mode="None/Transport/Message/TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|closeTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|listenIPAddress|Строка, указывающая IP\-адрес, на котором одноранговый узел будет ожидать TCP\-сообщения.  Значение по умолчанию — `null`.|  
|maxBufferPoolSize|Целое число, задающее максимальный размер буферного пула для этой привязки.  Значение по умолчанию \- 524 288 байт \(512 \* 1024\).  Многие элементы Windows Communication Foundation \(WCF\) используют буферы.  При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.  Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.  Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|maxReceivedMessageSize|Положительное целое число, задающее, в байтах, максимальный размер сообщения \(включая заголовки\), которое можно получить по каналу, настроенному с использованием этой привязки.  Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.  Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.  Значение по умолчанию — 65536.|  
|имя|Строка, содержащая имя конфигурации привязки.  Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|порт|Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP\-сообщения однорангового канала.  Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.  Значение по умолчанию — 0.|  
|receiveTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:10:00.|  
|sendTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<resolver\>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Указывает распознаватель одноранговых узлов, используемый данной привязкой для разрешения идентификаторов сетки одноранговых узлов в IP\-адреса конечных точек узлов этой сетки.|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|Определяет параметры безопасности сообщения.  Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязки\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## Заметки  
 Эта привязка обеспечивает поддержку для создания одноранговых и многопользовательских приложений, использующих передачу данных по протоколу TCP.  Каждый одноранговый узел может содержать несколько одноранговых каналов, определенных этим типом привязки.  
  
## Пример  
 Следующий пример демонстрирует применение привязки NetPeerTcpBinding, обеспечивающей многопользовательскую связь с использованием однорангового канала.  Подробный сценарий применения этой привязки см. в разделе [Net Peer TCP](http://msdn.microsoft.com/ru-ru/31f4db66-edb2-40a6-b92a-14098e92acae).  
  
```  
<configuration>  
<system.ServiceModel>  
<bindings>  
<netPeerBinding>  
    <binding   
         closeTimeout="00:00:10"  
         openTimeout="00:00:20"   
         receiveTimeout="00:00:30"  
         sendTimeout="00:00:40"  
         maxBufferSize="1001"  
         maxConnections="123"   
         maxReceiveMessageSize="1000">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00"  
            enabled="true" />  
        <security mode="TransportWithMessageCredential">  
            <message clientCredentialType="CardSpace" />  
        </security>  
    </binding>  
</netPeerBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.NetPeerTcpBinding>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)   
 [Net Peer TCP](http://msdn.microsoft.com/ru-ru/31f4db66-edb2-40a6-b92a-14098e92acae)   
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)