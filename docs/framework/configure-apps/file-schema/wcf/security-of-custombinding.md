---
title: "&lt;security&gt; для &lt;customBinding&gt; | Microsoft Docs"
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
ms.assetid: 243a5148-bbd1-447f-a8a5-6e7792c0a3f1
caps.latest.revision: 24
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 24
---
# &lt;security&gt; для &lt;customBinding&gt;
Задает параметры безопасности для пользовательской привязки.  
  
## Синтаксис  
  
```  
  
<security   
   allowSerializedSigningTokenOnReply="Boolean"  
   authenticationMode="AuthenticationMode"  
      defaultAlgorithmSuite="SecurityAlgorithmSuite"  
   includeTimestamp="Boolean"  
      requireDerivedKeys="Boolean"  
   keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"   
messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"  
      messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"  
   requireDerivedKeys="Boolean"  
   requireSecurityContextCancellation="Boolean"  
   requireSignatureConfirmation="Boolean"  
      securityHeaderLayout=  
              "Strict/Lax/LaxTimestampFirst/LaxTimestampLast"  
   includeTimestamp="Boolean">  
   <issuedTokenParameters />  
   <localClientSettings />  
   <localServiceSettings />  
   <secureConversationBootstrap />  
</security>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|allowSerializedSigningTokenOnReply|Необязательно.  Логическое значение, определяющее, может ли в ответе использоваться сериализованный маркер.  Значение по умолчанию — `false`.  При использовании двойной привязки для всех параметров, имеющих значение по умолчанию `true`, пропускаются любые заданные параметры.|  
|authenticationMode|Необязательно.  Указывает режим проверки подлинности, используемый между инициатором и отвечающим устройством.  Список значений приведен ниже.<br /><br /> Значение по умолчанию — `sspiNegotiated`.|  
|defaultAlgorithmSuite|Необязательно.  Задает алгоритмы шифрования сообщений и ключей.  Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.  Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности \(WS\-SecurityPolicy\).<br /><br /> Допустимые значения приведены ниже.  Значение по умолчанию — `Basic256`.<br /><br /> Этот атрибут используется при работе с другой платформой, которая использует набор алгоритмов, отличный от набора по умолчанию.  При внесении изменений в параметры настройки необходимо знать о сильных и слабых сторонах соответствующих алгоритмов.  Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|includeTimestamp|Логическое значение, определяющее, включается ли в каждое сообщение отметка времени.  Значение по умолчанию — `true`.|  
|keyEntropyMode|Указывает способ вычисления ключей для защиты сообщений.  Ключи могут быть основаны только на данных ключа клиента, только на данных ключа службы или на сочетании обоих типов данных.  Допустимы следующие значения:<br /><br /> -   `ClientEntropy`: сеансовый ключ основывается на данных ключа, предоставленных клиентом.<br />-   `ServerEntropy`: сеансовый ключ основывается на данных ключа, предоставленных сервером.<br />-   `CombinedEntropy`: сеансовый ключ основывается на данных ключа, предоставленных клиентом и службой.<br /><br /> Значение по умолчанию — `CombinedEntropy`.<br /><br /> Это атрибут типа <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|messageProtectionOrder|Определяет порядок, в котором к сообщению применяются алгоритмы безопасности уровня сообщения.  Допустимы следующие значения:<br /><br /> -   `SignBeforeEncrypt`: сначала подпись, затем шифрование.<br />-   `SignBeforeEncryptAndEncryptSignature`: сначала подпись, затем шифрование, затем шифрование сигнатуры.<br />-   `EncryptBeforeSign`: сначала шифрование, затем подпись.<br /><br /> Значение по умолчанию зависит от используемой версии WS\-Security.  Значение по умолчанию \- `SignBeforeEncryptAndEncryptSignature`, если используется WS\-Security 1,1.  Значение по умолчанию \- `SignBeforeEncrypt`, если используется WS\-Security 1.0.<br /><br /> Это атрибут типа <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|messageSecurityVersion|Необязательно.  Задает используемую версию WS\-Security.  Допустимы следующие значения:<br /><br /> -   WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11<br />-   WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br />-   WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br /><br /> Значение по умолчанию \- WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11, которое может быть выражено в формате XML просто как `Default`.  Это атрибут типа <xref:System.ServiceModel.MessageSecurityVersion>.|  
|requireDerivedKeys|Логическое значение, которое указывает, могут ли ключи быть производными от исходных ключей проверки.  Значение по умолчанию — `true`.|  
|requireSecurityContextCancellation|Необязательно.  Логическое значение, определяющее, следует ли отменять и завершать контекст безопасности, когда он больше не нужен.  Значение по умолчанию — `true`.|  
|requireSignatureConfirmation|Необязательно.  Логическое значение, определяющее, включено ли подтверждение сигнатуры WS\-Security.  Если установлено значение `true`, то сигнатуры сообщений подтверждаются респондентом.  Если пользовательская привязка настроена для использования взаимных сертификатов или выданных маркеров \(привязки WSS 1.1\), то этот атрибут имеет значение по умолчанию `true`.  В противном случае значением по умолчанию будет `false`.<br /><br /> Подтверждение сигнатуры используется для подтверждения того, что служба отвечает, получив запрос полностью.|  
|securityHeaderLayout|Необязательно.  Определяет порядок расположения элементов в заголовке безопасности.  Допустимы следующие значения:<br /><br /> -   `Strict`: элементы добавляются в заголовок безопасности в соответствии с общим принципом «объявить перед использованием».<br />-   `Lax`: элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP.<br />-   `LaxWithTimestampFirst`: элементы добавляются в заголовок безопасности в любом порядке, соответствующем требованиям безопасности сообщений WSS: SOAP, за исключением того, что первым элементом должен быть wsse:Timestamp.<br />-   `LaxWithTimestampLast`: элементы добавляются в заголовок безопасности в любом порядке, соответствующем требованиям безопасности сообщений WSS: SOAP, за исключением того, что последним элементом должен быть wsse:Timestamp.<br /><br /> Значение по умолчанию — `Strict`.<br /><br /> Это элемент типа <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
## Атрибут authenticationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Строковое|`AnonymousForCertificate`<br /><br /> `AnonymousForSslNegotiated`<br /><br /> `CertificateOverTransport`<br /><br /> `IssuedToken`<br /><br /> `IssuedTokenForCertificate`<br /><br /> `IssuedTokenForSslNegotiated`<br /><br /> `IssuedTokenOverTransport`<br /><br /> `Kerberos`<br /><br /> `KerberosOverTransport`<br /><br /> `MutualCertificate`<br /><br /> `MutualCertificateDuplex`<br /><br /> `MutualSslNegotiated`<br /><br /> `SecureConversation`<br /><br /> `SspiNegotiated`<br /><br /> `UserNameForCertificate`<br /><br /> `UserNameForSslNegotiated`<br /><br /> `UserNameOverTransport`<br /><br /> `SspiNegotiatedOverTransport`|  
  
## Атрибут defaultAlgorithm  
  
|Значение|Описание|  
|--------------|--------------|  
|Basic128|Используется шифрование Aes128, Sha1 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic192|Используется шифрование Aes192, Sha1 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic256|Используется шифрование Aes256, Sha1 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic256Rsa15|Используется Aes256 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|Basic192Rsa15|Используется Aes192 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|TripleDes|Используется шифрование TripleDes, Sha1 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic128Rsa15|Используется Aes128 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|TripleDesRsa15|Используется TripleDes для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|Basic128Sha256|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic192Sha256|Используется Aes192 для шифрования сообщения, Sha256 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic256Sha256|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|TripleDesSha256|Используется TripleDes для шифрования сообщения, Sha256 для хэша и Rsa\-oaep\-mgf1p для шифрования ключа.|  
|Basic128Sha256Rsa15|Используется Aes128 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|Basic192Sha256Rsa15|Используется Aes192 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|Basic256Sha256Rsa15|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|TripleDesSha256Rsa15|Используется TripleDes для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<issuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Определяет текущий выданный маркер.  Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)|Задает параметры безопасности локального клиента для этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)|Задает параметры безопасности локальной службы для этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
|[\<secureConversationBootstrap\>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] применении этого элемента см. в разделах [Режимы проверки подлинности SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) и [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
## Пример  
 В следующем примере показано, как настроить параметры безопасности с помощью настраиваемой привязки.  Здесь показано, как использовать пользовательскую привязку для включения безопасности на уровне сообщений вместе с безопасным транспортом.  Это полезно, когда требуется передавать сообщения между клиентом и службой с помощью безопасного транспорта с одновременным обеспечением безопасности на уровне сообщений.  Эта конфигурация не поддерживается привязками, предоставляемыми системой.  
  
 Конфигурация службы определяет настраиваемую привязку, которая поддерживает обмен данными по протоколу TCP с защитой протоколом TLS\/SSL и системой безопасности сообщений Windows.  Пользовательская привязка использует сертификат службы для проверки подлинности службы на уровне транспорта и для защиты сообщений при передаче между клиентом и службой.  Это возможно благодаря элементу привязки [\<sslStreamSecurity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md).  Сертификат службы настраивается с помощью поведения службы.  
  
 Кроме того, пользовательская привязка использует безопасность сообщений с типом учетных данных Windows, который является типом учетных данных по умолчанию.  Это возможно благодаря элементу привязки [security](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  Если доступен механизм проверки подлинности Kerberos, то проверка подлинности как клиента, так и службы выполняется с использованием безопасности уровня сообщений.  Если механизм проверки подлинности Kerberos недоступен, используется проверка подлинности NTLM.  NTLM выполняет проверку подлинности клиента при подключении к службе, но не выполняет проверку подлинности службы при подключении к клиенту.  Элемент привязки [security](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) настраивается на использование authenticationType `SecureConversation`, что приводит к созданию сеанса безопасности как на стороне, клиента, так и на стороне службы.  Это требуется для обеспечения работы дуплексного контракта службы.  Дополнительные сведения о выполнении этого примера см. в разделе [Безопасность пользовательской привязки](../../../../../docs/framework/wcf/samples/custom-binding-security.md).  
  
```  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <!-- use following base address -->  
            <add baseAddress="net.tcp://localhost:8000/ServiceModelSamples/Service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                    binding="customBinding"  
                    bindingConfiguration="Binding1"   
                    contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
        <!-- the mex endpoint is exposed at net.tcp://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexTcpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="SecureConversation"  
                     requireSecurityContextCancellation="true">  
          </security>  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <sslStreamSecurity requireClientCertificate="false"/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.SecurityElement>   
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Безопасность пользовательской привязки](../../../../../docs/framework/wcf/samples/custom-binding-security.md)