---
title: Протоколы безопасности версии 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: e22150d21638cffdf804008c32285f900bb1e263
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459044"
---
# <a name="security-protocols-version-10"></a>Протоколы безопасности версии 1.0
Протоколы WS-Security предоставляют механизмы обеспечения безопасности веб-служб, охватывающие все существующие требования к безопасности обмена сообщениями на предприятии. В этом разделе описываются сведения о Windows Communication Foundation (WCF) версии 1,0 (реализованные в <xref:System.ServiceModel.Channels.SecurityBindingElement>) для следующих протоколов безопасности веб-служб.  
  
|Спецификация/документ|Ссылка|  
|-|-|  
|WSS: SOAP Message Security 1,0|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|WSS: Username Token Profile 1.0|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|WSS: X509 Token Profile 1,0|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|WSS: SAML 1.1 Token Profile 1,0|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|WSS: SOAP Message Security 1.1|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|WSS Username Token Profile 1.1|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|WSS: X.509 Token Profile 1,1|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|WSS: Kerberos Token Profile 1.1|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|WSS: SAML 1.1 Token Profile 1.1|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|WS-Secure Conversation|<https://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|WS-Trust|<https://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|Замечания по применению.<br /><br /> Использование WS-Trust для подтверждения TLS|Готовится к публикации|  
|Замечания по применению.<br /><br /> Использование WS-Trust для подтверждения SPNEGO|Готовится к публикации|  
|Замечания по применению.<br /><br /> Ссылки и идентификация конечной точки адресации веб-служб|Готовится к публикации|  
|WS-SecurityPolicy 1.1<br /><br /> (2005/07)|<https://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> как исправлено в [перечне ошибок](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) , отправленных в технический комитет OASIS WS-SX |  
  
 WCF версии 1 предоставляет 17 режимов проверки подлинности, которые можно использовать в качестве базиса для настройки безопасности веб-служб. Каждый из режимов оптимизирован для того или иного типичного набора требований к развертыванию, например следующих:  
  
- учетные данные, используемые для проверки подлинности клиента и службы;  
  
- механизмы обеспечения безопасности на уровне сообщений или транспорта;  
  
- шаблоны обмена сообщениями.  
  
|Режим проверки подлинности|Аутентификация клиента|Проверка подлинности сервера|Режим|  
|-------------------------|---------------------------|---------------------------|----------|  
|UserNameOverTransport|Имя пользователя/пароль|X509|Transport|  
|CertificateOverTransport|X509|X509|Transport|  
|KerberosOverTransport|Windows|X509|Transport|  
|IssuedTokenOverTransport|Федеративная|X509|Transport|  
|SspiNegotiatedOverTransport|Согласование Windows Sspi|Согласование Windows Sspi|Transport|  
|AnonymousForCertificate|Отсутствуют|X509|Сообщение|  
|UserNameForCertificate|Имя пользователя/пароль|X509|Сообщение|  
|MutualCertificate|X509|X509|Сообщение|  
|MutualCertificateDuplex|X509|X509|Сообщение|  
|IssuedTokenForCertificate|Федеративная|X509|Сообщение|  
|Kerberos|Windows|Windows|Сообщение|  
|IssuedToken|Федеративная|Федеративная|Сообщение|  
|SspiNegotiation|Согласование Windows Sspi|Согласование Windows Sspi|Сообщение|  
|AnonymousForSslNegotiated|Отсутствуют|X509, TLS-Nego|Сообщение|  
|UserNameForSslNegotiated|Имя пользователя/пароль|X509, TLS-Nego|Сообщение|  
|MutualSslNegotiated|X509|X509, TLS-Nego|Сообщение|  
|IssuedTokenForSslNegotiated|Федеративная|X509, TLS-Nego|Сообщение|  
  
 Конечные точки, использующие такие режимы проверки подлинности, могут выражать свои требования безопасности с помощью WS-SecurityPolicy (WS-SP). В этом документе описывается структура заголовка безопасности и инфраструктурные сообщения для каждого режима проверки подлинности, а также приводятся примеры политик и сообщений.  
  
 WCF использует WS-SecureConversation для обеспечения поддержки безопасных сеансов для защиты обмена сообщениями между приложениями.  Сведения о реализации см. ниже в подразделе "Безопасные сеансы".  
  
 В дополнение к режимам проверки подлинности, WCF предоставляет параметры для управления общими механизмами защиты, которые применяются к большинству режимов проверки подлинности на основе безопасности сообщений, например: порядок подписи и операции шифрования, наборы алгоритмов, получение ключа и Подтверждение сигнатуры.  
  
 В данном документе используются перечисленные ниже префиксы и пространства имен.  
  
|Префикс|Пространство имен|  
|------------|---------------|  
|s|<http://www.w3.org/2003/05/soap-envelope/>|
|sp|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|а|<http://www.w3.org/2005/08/addressing>|  
|wsse|Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1,0|  
|wsse11|Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1.1|  
|wsu|Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1.0 Utility|  
|ds|Подлежит определению - универсальный код ресурса (URI) W3C XMLDSig|  
|wst|Подлежит определению - универсальный код ресурса (URI) WS-Trust 2005/02|  
|wssc|Подлежит определению - универсальный код ресурса (URI) WS-SecureConversation 2005/02|  
|wsaw|Подлежит определению - пространство имен политики WS-Addressing|  
|wsp|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|mssp|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a>1. Профили маркеров  
 В спецификациях WS-Security учетные данные представляются в виде токенов безопасности. WCF поддерживает следующие типы токенов:  
  
### <a name="11-usernametoken"></a>1.1 Маркер UsernameToken  
 WCF использует профили UsernameToken10 и UsernameToken11 со следующими ограничениями:  
  
 R1101 Атрибут PasswordType элемента UsernameToken\Password ДОЛЖЕН быть либо опущен, либо иметь значение #PasswordText (по умолчанию).  
  
 Можно реализовать #PasswordDigest с помощью расширяемости. Замечено, что #PasswordDigest часто ошибочно считается достаточно безопасным механизмом защиты пароля. Однако #PasswordDigest не может служить заменой шифрованию маркера UsernameToken. Основной целью #PasswordDigest является защита от атак с повторением. В режимах проверки подлинности WCF угрозы атак с целью воспроизведения снижаются с помощью подписей сообщений.  
  
 B1102 WCF никогда не выдает nonce и создает вложенные элементы UsernameToken.  
  
 Эти подэлементы предназначены для упрощения обнаружения атак с повторением. В WCF вместо этого используются сигнатуры сообщений.  
  
 В профиле OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) введена возможность создания производного ключа из пароля.  
  
 B1103 Пароль UsernameToken НЕ ДОЛЖЕН использоваться для создания производного ключа и, следовательно, для операций шифрования.  
  
 Обоснование: пароли обычно считаются слишком слабой защитой, для того чтобы использовать их в операциях шифрования.  
  
### <a name="12-x509-token"></a>1.2 Маркер X509  
 WCF поддерживает сертификаты X509v3 в качестве типа учетных данных и соответствует X509TokenProfile 1.0 и X509TokenProfile 1.1 со следующими ограничениями:  
  
 R1201 Атрибут ValueType элемента BinarySecurityToken должен иметь значение #X509v3, если он содержит сертификат X509v3.  
  
 Профили WSS X509 Token Profile 1.0 и 1.1 также определяют типы значений #X509PKIPathv1 и #PKCS7. WCF не поддерживает эти типы.  
  
 R1202 Если в сертификате X509 имеется расширение SubjectKeyIdentifier (SKI), для внешних ссылок на маркер должен использоваться wsse:KeyIdentifier, со значением #X509SubjectKeyIdentifier атрибута ValueType и содержащий значение расширения SKI сертификата в кодировке base64.  
  
 Ссылки SKI имеют множество реализаций и зарекомендовали себя как внешний ссылочный тип с широкими возможностями совместимости.  
  
 R1203 Внешняя ссылка на маркер безопасности X509 НЕ ДОЛЖНА использовать ds:X509IssuerSerial.  
  
 R1204 Если используется профиль X509TokenProfile1.1, внешняя ссылка на маркер безопасности X509 ДОЛЖНА использовать отпечаток, введенный в протоколе WS-Security 1.1.  
  
 WCF поддерживает X509IssuerSerial. Однако существуют проблемы взаимодействия с X509IssuerSerial: WCF использует строку для сравнения двух значений X509IssuerSerial. Поэтому, если один из способов переупорядочивает компоненты имени субъекта и отправляет в службу WCF ссылку на сертификат, он может быть не найден.  
  
### <a name="13-kerberos-token"></a>1.3 Маркер Kerberos  
 WCF поддерживает Керберостокенпрофиле 1.1 в целях проверки подлинности Windows со следующими ограничениями:  
  
 R1301 Маркер Kerberos должен содержать значение GSS в оболочке Kerberos v4 AP_REQ, как определено в GSS_API и спецификации Kerberos, и должен иметь атрибут ValueType со значением #GSS_Kerberosv5_AP_REQ.  
  
 WCF использует GSS, инкапсулированные Kerberos AP-REQ, а не несамостоятельный AP-REQ. Это рекомендуется в целях безопасности.  
  
### <a name="14-saml-v11-token"></a>1.4 Маркер SAML 1.1  
 В WCF поддерживаются профили маркеров WSS SAML 1,0 и 1,1 для маркеров SAML v 1.1. Возможна реализация других версий форматов маркеров SAML.  
  
### <a name="15-security-context-token"></a>1.5 Маркер контекста безопасности  
 WCF поддерживает маркер контекста безопасности (SCT), появившийся в WS-SecureConversation. Маркер контекста безопасности служит для представления контекста безопасности, установленного в спецификации SecureConversation, а также протоколов двоичного согласования TLS и SSPI, описываемых ниже.  
  
## <a name="2-common-message-security-parameters"></a>2. Общие параметры безопасности сообщений  
  
### <a name="21-timestamp"></a>2.1 TimeStamp  
 Наличие отметки времени определяется с помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> класса <xref:System.ServiceModel.Channels.SecurityBindingElement>. WCF всегда сериализует wsse: TimeStamp с wsse: Created и wsse: Expires. Если используется подписывание, wsse:TimeStamp всегда подписывается.  
  
### <a name="22-protection-order"></a>2.2. Порядок защиты  
 WCF поддерживает порядок защиты сообщений "подписывать перед шифрованием" и "шифровать перед подписью" (политика безопасности 1,1). По ряду причин рекомендуется использовать порядок «подпись перед шифрованием», в том числе по следующим причинам: если не используется механизм WS-Security 1.1 SignatureConfirmation, сообщения, защищенные в порядке «шифрование перед подписью», подвержены атакам подмены подписи и при подписывании зашифрованного содержимого сложнее производить аудит.  
  
### <a name="23-signature-protection"></a>2.3 Защита сигнатуры  
 Если используется порядок "шифрование перед сигнатурой", рекомендуется защищать сигнатура, чтобы предотвратить атаки методом подбора для угадывания зашифрованного содержимого или ключа сигнатуры (особенно при использовании пользовательского маркера с ненадежным ключевым материалом).  
  
### <a name="24-algorithm-suite"></a>2.4 Набор алгоритмов  
 WCF поддерживает все наборы алгоритмов, перечисленные в политике безопасности 1,1.  
  
### <a name="25-key-derivation"></a>2.5 Формирование ключей  
 WCF использует "ключ наследования для симметричных ключей", как описано в разделе WS-SecureConversation.  
  
### <a name="26-signature-confirmation"></a>2.6 Подтверждение сигнатуры  
 Подтверждение сигнатуры может использоваться в качестве защиты от атак типа «злоумышленник в середине», чтобы защитить набор подписей.  
  
### <a name="27-security-header-layout"></a>2.7 Структура заголовка безопасности  
 Каждый режим проверки подлинности описывает определенную структуру заголовка безопасности. Элементы в заголовке безопасности полуупорядочены. Чтобы определить порядок дочерних элементов заголовка безопасности, в спецификации WS-Security Policy определены следующие режимы структуры заголовка безопасности:  
  
|||  
|-|-|  
|Strict|Элементы добавляются в заголовок безопасности в соответствии с правилами нумерованной структуры, описанными в разделе 7.7.1 спецификаций Security Policy, на основе общего принципа "объявить перед использованием".|  
|Lax|Элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP Message Security.|  
|LaxTimestampFirst|Аналогично Lax, но первым элементом в заголовке безопасности должен быть элемент wsse:Timestamp.|  
|LaxTimestampLast|Аналогично Lax, но последним элементом в заголовке безопасности должен быть элемент wsse:Timestamp.|  
  
 WCF поддерживает все четыре режима для макета заголовка безопасности. В приведенных ниже структурах заголовков безопасности и примерах сообщений для режимов проверки подлинности используется режим "Strict".  
  
## <a name="2-common-message-security-parameters"></a>2. Общие параметры безопасности сообщений  
 В этом подразделе приведены примеры политик для каждого режима проверки подлинности, а также примеры, показывающие структуру заголовка безопасности в сообщениях, которыми обмениваются клиент и служба.  
  
### <a name="61-transport-protection"></a>6.1 Защита транспорта  
 WCF предоставляет пять режимов проверки подлинности, использующих защищенный транспорт для защиты сообщений; Усернамеовертранспорт, Цертификатеовертранспорт, Керберосовертранспорт, Иссуедтокеновертранспорт и SspiNegotiatedOverTransport.  
  
 Эти режимы проверки подлинности построены с использованием привязок транспорта, описанных в спецификации SecurityPolicy. Для режима проверки подлинности UserNameOverTransport маркер UsernameToken является подписанным поддерживающим маркером. Для других режимов проверки подлинности этот маркер является подписанным подтверждающим маркером. В приложениях C.1.2 и C.1.3 спецификации SecurityPolicy подробно описана структура заголовка безопасности. В приведенных ниже примерах заголовки безопасности для определенного режима проверки подлинности показаны со структурой Strict.  
  
 Свойство Derived Keys для маркеров во всех случаях имеет значение "false".  
  
 Различные свойства привязок транспорта имеют следующие значения:  
  
 Отметка времени: true  
  
 Структура заголовка безопасности: Strict  
  
 Набор алгоритмов: Basic256  
  
#### <a name="611-usernameovertransport"></a>6.1.1 UsernameOverTransport  
 В этом режиме проверка подлинности клиента осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера, всегда отправляемого от инициатора получателю. Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне. Используется привязка транспорта.  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />   
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Структура заголовка безопасности  
  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a>6.1.2 CertificateOverTransport  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю. Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне. Используется привязка транспорта.  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />   
              <sp:WssX509V3Token10 />   
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Структура заголовка безопасности  
  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a>6.1.3 IssuedTokenOverTransport  
 В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности (STS) и подтверждает знание общего ключа. Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю. Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне. Используется привязка транспорта.  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>   
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />   
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Структура заголовка безопасности  
  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a>6.1.4 KerberosOverTransport  
 В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos. Маркер Kerberos доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера. Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне. Используется привязка транспорта.  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />   
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Структура заголовка безопасности  
  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a>6.1.5 SspiNegotiatedOverTransport  
 В этом режиме для проверки подлинности клиента и сервера используется протокол согласования. Если это возможно, используется протокол Kerberos, в противном случае - протокол NTLM. Итоговый маркер контекста безопасности доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю. Служба проходит дополнительную проверку подлинности на транспортном уровне с использованием сертификата X.509. Используется привязка транспорта. "SPNEGO" (согласование) описывает, как WCF использует протокол согласования с двоичным кодом SSPI с WS-Trust. В этом разделе приведены примеры заголовков безопасности после установления маркера контекста безопасности с помощью подтверждения SPNEGO.  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />   
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a>Примеры заголовков безопасности  
 После установления маркера контекста безопасности с помощью подтверждения SPNEGO при использовании двоичного согласования WS-Trust заголовки безопасности в сообщениях приложения имеют следующую структуру.  
  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a>6.2 Использование сертификатов X.509 для проверки подлинности службы  
 В этом разделе рассматриваются следующие режимы проверки подлинности: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate и IssuedTokenForCertificate.  
  
#### <a name="621-mutualcertificate-wss10"></a>6.2.1 MutualCertificate WSS1.0  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве маркера инициатора. Служба также проходит проверку подлинности с использованием сертификата X.509.  
  
 Используется асимметричная привязка со следующими значениями свойств.  
  
 Маркер инициатора: сертификат X.509 клиента, задан режим включения …/IncludeToken/AlwaysToRecipient  
  
 Маркер получателя: сертификат X.509 сервера, задан режим включения …/IncludeToken/Never  
  
 Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Примеры заголовков безопасности: EncryptBeforeSign  
  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a>6.2.2 MutualCertificateDuplex  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве маркера инициатора. Служба также проходит проверку подлинности с использованием сертификата X.509.  
  
 Используется асимметричная привязка со следующими значениями свойств.  
  
 Маркер инициатора: сертификат X.509 клиента, задан режим включения …/IncludeToken/AlwaysToRecipient  
  
 Маркер получателя: сертификат X.509 сервера, задан режим включения …/IncludeToken/AlwaysToInitiator  
  
 Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос и ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос и ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a>6.2.3 Использование SymmetricBinding с проверкой подлинности службы X.509  
 Спецификация "WSS10" обеспечивает ограниченную поддержку сценариев с маркерами X509. Например, в этой версии не было способа обеспечить защиту сообщений сигнатурой и шифрованием, используя только маркер X509 службы. В спецификации "WSS11" вводится использование EncryptedKey в качестве симметричного маркера. Теперь временный ключ, зашифрованный для сертификата X.509 службы, может использоваться для защиты как сообщений запроса, так и сообщений ответа. Эта схема используется в режимах проверки подлинности, описанных ниже в разделе 6.4.  
  
 В спецификации WS-SecurityPolicy эта схема описывается с помощью привязки SymmetricBinding с маркером X509 службы в качестве маркера защиты.  
  
 В режимах проверки подлинности AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 и IssuedTokenForCertificate используется аналогичный экземпляр sp:SymmetricBinding со следующими значениями свойств.  
  
 Токен защиты: сертификат X.509 сервера, задан режим включения …/IncludeToken/Never  
Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
 Перечисленные выше режимы проверки подлинности различаются только используемыми поддерживающими маркерами. В режиме AnonymousForCertificate поддерживающие маркеры отсутствуют, в режиме MutualCertificate (WSS 1.1) сертификат X509 клиента используется как подтверждающие поддерживающие маркеры, в режиме UserNameForCertificate маркер UserName используется как подписанный поддерживающий маркер, а в режиме IssuedTokenForCertificate выданный маркер используется как подтверждающий поддерживающий маркер.  
  
 Политика  
  
 Симметричная привязка  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireThumbprintReference />   
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
          <sp:RequireSignatureConfirmation />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a>6.2.4 AnonymousForCertificate  
 В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509. Используется экземпляр симметричной привязки, как описано в разделе 6.4.2.  
  
 Политика  
  
 Сведения о привязке см. в пункте «Политика» раздела 6.2.3  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a>6.2.5 UserNameForCertificate  
 В этом режиме проверка подлинности клиента в службе осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера. Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509. Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.  
  
 Политика  
  
 Сведения о привязке см. в пункте «Политика» раздела 6.2.3  
  
 Подписанный поддерживающий маркер  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a>6.2.6 MutualCertificate (WSS 1.1)  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера. Служба также проходит проверку подлинности с использованием сертификата X.509. Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.  
  
 Политика  
  
 Сведения о привязке см. в пункте «Политика» раздела 6.2.3  
  
 Подтверждающий поддерживающий маркер  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a>6.2.7 IssuedTokenForCertificate  
 В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа. Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера. Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509. Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.  
  
 Политика  
  
 Сведения о привязке см. в пункте «Политика» раздела 6.2.3  
  
 Подтверждающий поддерживающий маркер  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />   
       <sp:RequireInternalReference />   
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a>6.3 Kerberos  
 В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos. Этот же билет обеспечивает проверку подлинности сервера. Используется симметричная привязка со следующими свойствами.  
  
 Токен защиты: билет kerberos, задан режим включения …/IncludeToken/Once  
Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:WssGssKerberosV5ApReqToken11 />   
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a>6.4 IssuedToken  
 В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого клиент предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа. Служба не проходит как таковую проверку подлинности на стороне клиента, но служба маркеров безопасности шифрует общий ключ как часть выдаваемого маркера, чтобы только служба могла расшифровать этот ключ. Используется симметричная привязка со следующими свойствами.  
  
 Токен защиты: выданный токен, задан режим включения .../IncludeToken/AlwaysToRecipient  
Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>   
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireInternalReference />   
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a>6.5 Использование SslNegotiated для проверки подлинности службы  
 В этом разделе рассматривается группа режимов проверки подлинности, в которых используется симметричная привязка с маркером защиты, являющимся маркером контекста безопасности в соответствии со спецификацией WS-SecureConversation (WS-SC), значение ключа которого согласовывается путем выполнения протокола TLS с помощью сообщений RST/RSTR спецификации WS-Trust (WS-T). Сведения о реализации подтверждения TLS с помощью спецификации WS-Trust приведены в спецификации TLSNEGO. В приведенных ниже примерах сообщений предполагается, что маркер контекста безопасности со связанным контекстом безопасности уже установлен путем подтверждения.  
  
 Используется симметричная привязка со следующими свойствами.  
  
 Токен защиты: SslContextToken, задан режим включения .../IncludeToken/Never  
Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a>6.5.1 Политика для проверки подлинности службы SslNegotiated  
 Политики для всех режимов проверки подлинности в этом разделе аналогичны и различаются только определенными используемыми подписанными поддерживающими или подтверждающими маркерами.  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>   
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a>6.5.2 AnonymousForSslNegotiated  
 В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509. Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.  
  
 Политика  
  
 Сведения о привязке см. в пункте «Политика» раздела 6.5.1.  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a>6.5.3 UserNameForSslNegotiated  
 В этом режиме проверка подлинности клиента осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера. Служба проходит проверку подлинности с использованием сертификата X.509. Используется экземпляр симметричной привязки, как описано в разделе 6.5.1.  
  
 Политика  
  
 Сведения о привязке см. в разделе 6.5.1  
  
 Подписанный поддерживающий маркер  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a>6.5.4 IssuedTokenForSslNegotiated  
 В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа. Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера. Служба проходит проверку подлинности с использованием сертификата X.509. Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.  
  
 Политика  
  
 Сведения о привязке см. в разделе 6.5.1  
  
 Подтверждающий поддерживающий маркер  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>   
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />   
        <sp:RequireInternalReference />   
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a>6.5.5 MutualSslNegotiated  
 В этом режиме проверка подлинности клиента и службы осуществляется с использованием сертификатов X.509. Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.  
  
 Политика  
  
 Сведения о привязке см. в разделе 6.5.1  
  
 Подтверждающий поддерживающий маркер  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a>6.6 SspiNegotiated  
 В этом режиме для проверки подлинности клиента и сервера используется протокол согласования. Если это возможно, используется протокол Kerberos, в противном случае - протокол NTLM. Используется симметричная привязка со следующими свойствами.  
  
 Токен защиты: SpnegoContextToken, задан режим включения .../IncludeToken/AlwaysToRecipient  
Защита маркера: False  
  
 Сигнатуры всего заголовка и тела: True  
  
 Порядок защиты: SignBeforeEncrypt  
  
 Шифрование подписи: True  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a>6.7 SecureConversation  
 Используется симметричная привязка, в которой маркером защиты является маркер контекста безопасности в соответствии со спецификацией WS-SecureConversation (WS-SC). Согласование маркера контекста безопасности производится с использованием спецификации WS-Trust (WS-Trust) или WS-SecureConversation (WS-SC) в соответствии с вложенной привязкой, которая сама является симметричной привязкой, использующей протокол согласования. При возможности в протоколе согласования для проверки подлинности клиента и сервера используется протокол Kerberos. Если использование протокола Kerberos невозможно, используется резервный протокол NTLM.  
  
 Политика  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />   
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />   
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />   
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />   
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />   
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />   
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />   
                          <sp:EncryptSignature />   
                          <sp:OnlySignEntireHeadersAndBody />   
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />   
                          <sp:MustSupportRefIssuerSerial />   
                          <sp:MustSupportRefThumbprint />   
                          <sp:MustSupportRefEncryptedKey />   
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />   
                          <sp:RequireClientEntropy />   
                          <sp:RequireServerEntropy />   
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a>Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature  
 Запрос  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a>Примеры заголовков безопасности: EncryptBeforeSign  
 Запрос  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Ответ  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
