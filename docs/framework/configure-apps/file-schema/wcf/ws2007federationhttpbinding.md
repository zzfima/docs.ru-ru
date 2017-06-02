---
title: "&lt;ws2007FederationHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;ws2007FederationHttpBinding&gt;
Безопасная привязка с возможностью взаимодействия, которая является производной от [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) и поддерживает федеративную безопасность.  
  
## Синтаксис  
  
```  
  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                issuedTokenType="string"  
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</ws2007FederationHttpBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`bypassProxyOnLocal`|Значение, определяющее, будет ли выполняться обход прокси\-сервера для локальных адресов.  Значение по умолчанию — `false`.|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|`hostnameComparisonMode`|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов \(URI\).  Это атрибут типа <xref:System.ServiceModel.HostnameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов \(URI\).  Значение по умолчанию — <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|  
|`maxBufferPoolSize`|Максимальный размер буферного пула для этой привязки.  Значение по умолчанию \- 524 288 байт \(512 \* 1024\).  Многие элементы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] используют буферы.  При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.  Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.  Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|`maxReceivedMessageSize`|Максимальный размер сообщения \(в байтах\), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.  Отправитель сообщения, которое превысит это ограничение, получает ошибку SOAP.  Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.  Значение по умолчанию — 65536.|  
|`messageEncoding`|Определяет кодировщик, используемый для кодировки сообщения.  Допустимы следующие значения:<br /><br /> -   Text: используется кодировщик текстовых сообщений.<br />-   Mtom: используется кодировщик MTOM 1.0 \(Message Transmission Organization Mechanism\).<br /><br /> Значение по умолчанию \- Text.<br /><br /> Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.|  
|`name`|Имя конфигурации привязки.  Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|`privactyNoticeAt`|Универсальный код ресурса \(URI\), определяющий расположение примечания о конфиденциальности.|  
|`privactyNoticeVersion`|Версия текущего примечания о конфиденциальности.|  
|`proxyAddress`|Универсальный код ресурса \(URI\), задающий адрес прокси\-сервера HTTP.  Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.  Значение по умолчанию — `null`.|  
|`receiveTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:10:00.|  
|`sendTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|`textEncoding`|Задает кодировку, используемую при отправке сообщений через привязку.  Допустимы следующие значения:<br /><br /> -   BigEndianUnicode: кодировка Юникод \(обратный порядок байтов\).<br />-   Unicode: 16\-разрядная кодировка.<br />-   UTF8: 8\-разрядная кодировка.<br /><br /> Значение по умолчанию \- UTF8.  Это атрибут типа <xref:System.Text.Encoding>.|  
|`transactionFlow`|Значение, определяющее, поддерживает ли привязка потоки WS\-Transactions.  Значение по умолчанию — `false`.|  
|`useDefaultWebProxy`|Значение, указывающее, должен ли использоваться автоматически настроенный системный прокси\-сервер HTTP.  Если данный атрибут имеет значение `true`, прокси\-адрес должен быть равен `null` \(то есть не задан\).  Значение по умолчанию — `true`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|Определяет параметры безопасности сообщения.  Это элемент типа <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[reliableSession](http://msdn.microsoft.com/ru-ru/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|Указывает, устанавливаются ли между конечными точками канала надежные сеансы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязки\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## Заметки  
 Федерация \- это возможность совместного использования удостоверений между несколькими предприятиями или доверенными доменами в целях проверки подлинности и авторизации.  Для сопоставления представления идентификации между доверенными доменами используется протокол WS\-Trust.  Федеративная привязка HTTP поддерживает безопасность SOAP, а также безопасность в смешанном режиме, но она не поддерживает безопасность транспорта.  Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
## Пример  
  
```  
<configuration>  
<system.ServiceModel>  
<bindings>  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://www.contoso.com"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.WS2007FederationHttpBinding>   
 <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>   
 [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)