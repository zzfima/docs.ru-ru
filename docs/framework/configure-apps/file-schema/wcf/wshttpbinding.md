---
title: "&lt;wsHttpBinding&gt; | Microsoft Docs"
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
helpviewer_keywords: 
  - "wsHttpBinding, элемент"
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# &lt;wsHttpBinding&gt;
Определяет безопасную, надежную, привязку с возможностью взаимодействия, которая может использоваться для недуплексных контрактов службы.  В привязке реализованы следующие возможности: обмен сообщениями WS\-Reliable для обеспечения надежности, а также WS\-Security для обеспечения безопасности и проверки подлинности сообщений.  В качестве транспорта используется HTTP, а для кодировки сообщений — кодировка Text\/XML.  
  
## Синтаксис  
  
```  
  
<wsHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
        <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string" />  
          <message   
             algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                          clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
             establishSecurityContext="Boolean"  
             negotiateServiceCredential="Boolean" />  
        </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</wsHttpBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|allowCookies|Логическое значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.  Значение по умолчанию – false.<br /><br /> Это свойство можно использовать при взаимодействии с веб\-службами ASMX, которые используют файлы Cookie.  В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.|  
|bypassProxyOnLocal|Логическое значение, определяющее, будет ли выполняться обход прокси\-сервера для локальных адресов.  Значение по умолчанию — `false`.|  
|closeTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|hostnameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов \(URI\).  Это атрибут типа <xref:System.ServiceModel.HostnameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов \(URI\).  Значение по умолчанию — <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|  
|maxBufferPoolSize|Целое число, задающее максимальный размер буферного пула для этой привязки.  Значение по умолчанию \- 524 288 байт \(512 \* 1024\).  Многие элементы Windows Communication Foundation \(WCF\) используют буферы.  При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.  Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.  Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|maxReceivedMessageSize|Положительное целое число, задающее, в байтах, максимальный размер сообщения \(включая заголовки\), которое можно получить по каналу, настроенному с использованием этой привязки.  Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.  Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.  Значение по умолчанию — 65536.|  
|messageEncoding|Определяет кодировщик, используемый для кодировки сообщения.  Допустимы следующие значения:<br /><br /> -   Text: используется кодировщик текстовых сообщений.<br />-   Mtom: используется кодировщик MTOM 1.0 \(Message Transmission Organization Mechanism\).<br />-   Значение по умолчанию \- Text.<br /><br /> Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.|  
|имя|Строка, содержащая имя конфигурации привязки.  Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|proxyAddress|Универсальный код ресурса \(URI\), задающий адрес прокси\-сервера HTTP.  Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.  Значение по умолчанию — `null`.|  
|receiveTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|sendTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|textEncoding|Задает кодировку, используемую при отправке сообщений через привязку.  Допустимы следующие значения:<br /><br /> -   UnicodeFffeTextEncoding: кодировка Юникод \(обратный порядок байтов\).<br />-   Utf16TextEncoding: 16\-разрядная кодировка.<br />-   Utf8TextEncoding: 8\-разрядная кодировка.<br /><br /> Значение по умолчанию \- Utf8TextEncoding.<br /><br /> Это атрибут типа <xref:System.Text.Encoding>.|  
|transactionFlow|Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS\-Transactions.  Значение по умолчанию — `false`.|  
|useDefaultWebProxy|Логическое значение, определяющее, должен ли использоваться автоматически настроенный системный прокси\-сервер HTTP.  Значение по умолчанию — `true`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|Определяет параметры безопасности привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[reliableSession](http://msdn.microsoft.com/ru-ru/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|Указывает, устанавливаются ли между конечными точками канала надежные сеансы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязки\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## Заметки  
 Привязка `WSHttpBinding` аналогична привязке `BasicHttpBinding`, но при этом предоставляет больше функциональных возможностей веб\-служб.  В ней используется транспорт HTTP и обеспечивается безопасность сообщения, как и в привязке BasicHttpBinding, но вместе с тем также предоставляются транзакции, надежный обмен сообщениями и WS\-Addressing, включенные по умолчанию или доступные посредством одного управляющего параметра.  
  
## Пример  
  
```  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://foo/bar"  
                    textEncoding="utf-16"  
                    useDefaultWebProxy="false">  
                    <reliableSession ordered="false"  
                         inactivityTimeout="00:02:00"  
                         enabled="true" />  
                    <security mode="Transport">  
                         <transport clientCredentialType="Digest"  
                            proxyCredentialType="None"  
                            realm="someRealm" />  
                         <message clientCredentialType="Windows"  
                            negotiateServiceCredential="false"  
                            algorithmSuite="Aes128"   
                            defaultProtectionLevel="None" />  
                    </security>  
                </binding>  
           </wsHttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.WSHttpBinding>   
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)