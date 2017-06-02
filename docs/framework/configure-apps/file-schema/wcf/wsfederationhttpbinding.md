---
title: "&lt;wsFederationHttpBinding&gt; | Microsoft Docs"
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
  - "wsFederationBinding, элемент"
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# &lt;wsFederationHttpBinding&gt;
Определяет привязку, которая поддерживает спецификацию WS\-Federation.  
  
## Синтаксис  
  
```  
  
<wsFederationHttpBinding>  
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
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
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
</wsFederationBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|bypassProxyOnLocal|Логическое значение, определяющее, будет ли выполняться обход прокси\-сервера для локальных адресов.  Значение по умолчанию — `false`.|  
|closeTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|hostnameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов \(URI\).  Это атрибут типа <xref:System.ServiceModel.HostnameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов \(URI\).  Значение по умолчанию — <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|  
|maxBufferPoolSize|Целое число, задающее максимальный размер буферного пула для этой привязки.  Значение по умолчанию \- 524 288 байт \(512 \* 1024\).  Многие элементы Windows Communication Foundation \(WCF\) используют буферы.  При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.  Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.  Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|maxReceivedMessageSize|Положительное целое число, задающее, в байтах, максимальный размер сообщения \(включая заголовки\), которое можно получить по каналу, настроенному с использованием этой привязки.  Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.  Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.  Значение по умолчанию — 65536.|  
|messageEncoding|Определяет кодировщик, используемый для кодировки сообщения.  Допустимы следующие значения:<br /><br /> -   Text: используется кодировщик текстовых сообщений.<br />-   Mtom: используется кодировщик MTOM 1.0 \(Message Transmission Organization Mechanism\).<br /><br /> Значение по умолчанию \- Text.<br /><br /> Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.|  
|имя|Строка, содержащая имя конфигурации привязки.  Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|privactyNoticeAt|Строка, задающая универсальный код ресурса \(URI\), определяющий расположение примечания о конфиденциальности.|  
|privactyNoticeVersion|Целое число, определяющее версию текущего уведомления о конфиденциальности.|  
|proxyAddress|Универсальный код ресурса \(URI\), задающий адрес прокси\-сервера HTTP.  Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.  Значение по умолчанию — `null`.|  
|receiveTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:10:00.|  
|sendTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|textEncoding|Задает кодировку, используемую при отправке сообщений через привязку.  Допустимы следующие значения:<br /><br /> -   BigEndianUnicode: кодировка Юникод \(обратный порядок байтов\).<br />-   Unicode: 16\-разрядная кодировка.<br />-   UTF8: 8\-разрядная кодировка.<br /><br /> Значение по умолчанию \- UTF8.  Это атрибут типа <xref:System.Text.Encoding>.|  
|transactionFlow|Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS\-Transactions.  Значение по умолчанию — `false`.|  
|useDefaultWebProxy|Логическое значение, указывающее, должен ли использоваться автоматически настроенный системный прокси\-сервер HTTP.  Если данный атрибут имеет значение `true`, прокси\-адрес должен быть равен `null` \(то есть не задан\).  Значение по умолчанию — `true`.|  
  
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
 Федерация \- это возможность совместного использования удостоверений в нескольких системах в целях проверки подлинности и авторизации.  Эти удостоверения могут ссылаться на пользователей или на компьютеры.  Федеративный протокол HTTP поддерживает безопасность SOAP и безопасность в смешанном режиме, но не поддерживает использование исключительно безопасности транспорта.  Эта привязка обеспечивает поддержку системой [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] протокола WS\-Federation.  Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP.  
  
 Привязки состоят из стека элементов привязки.  Стек элементов привязки в  
  
 `wsFederationHttpBinding` идентичен тому, что содержится в `wsHttpBinding`  
  
 если [\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) присвоено значение по умолчанию <xref:System.ServiceModel.WSFederationHttpSecurityMode>.  
  
 Привязка `wsFederationHttpBinding` управляет сведениями о параметрах безопасности сообщений в [\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).  Обратите внимание, что элемент [\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) обеспечивает доступ на получение только в качестве системы безопасности, используемой привязкой, и его нельзя изменить после создания привязки.  
  
 Привязка `wsFederationHttpBinding` также предоставляет атрибут privactyNoticeAt для установки и извлечения универсального кода ресурса \(URI\), определяющего расположение примечания о конфиденциальности.  
  
 Обеспечение безопасности политики особенно важно в федеративных сценариях.  Для защиты политики от злоумышленников рекомендуется использовать определенную систему безопасности, например протокол HTTPS.  
  
 В федеративных сценариях с использованием этой привязки политика службы потенциально содержит важные сведения, например ключ для шифрования выдаваемого маркера \(SAML\), тип утверждений, помещаемых в маркер, и так далее.  Если политика подделана, атакующий может обнаружить ключ выданного маркера, что приводит к дальнейшим подделкам, раскрытию сведений и другим вредоносным действиям.  Чтобы предупредить злонамеренные действия, политика должна быть получена от службы безопасным способом \(например, с помощью протокола HTTPS\).  
  
 Дополнительные сведения об этой привязке см. в разделе [Практическое руководство. Создание WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).  
  
## Пример  
  
```  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="saml"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</wsFederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.WSFederationHttpBinding>   
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>   
 [Практическое руководство. Создание WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)