---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 77b1383c1fcd3e867e6cef0ae5507b3a2ff8a80d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371389"
---
# <a name="ws2007federationhttpbinding"></a>\<ws2007FederationHttpBinding >

Надежная и совместимая привязка, производный от [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) и поддерживает федеративную безопасность.

\<system.ServiceModel>\
\<привязки > \
\<ws2007FederationHttpBinding >

## <a name="syntax"></a>Синтаксис

```xml
<ws2007FederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
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
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`bypassProxyOnLocal`|Значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов. Значение по умолчанию — `false`.|
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|
|`hostnameComparisonMode`|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI). Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI). Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|
|`maxBufferPoolSize`|Максимальный размер буферного пула для этой привязки. Значение по умолчанию - 524 288 байт (512 * 1024). Многие элементы Windows Communication Foundation (WCF) используют буферы. При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов. Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется. Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|
|`maxReceivedMessageSize`|Максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки. Отправитель сообщения, которое превысит это ограничение, получает ошибку SOAP. Получатель отклоняет сообщение и создает запись о событии в журнале трассировки. Значение по умолчанию — 65536.|
|`messageEncoding`|Определяет кодировщик, используемый для кодировки сообщения. Допустимы следующие значения:<br /><br /> -Текст: Используйте кодировщик текстовых сообщений.<br />-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).<br /><br /> Значение по умолчанию - Text.<br /><br /> Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.|
|`name`|Имя конфигурации привязки. Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки. Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена. Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|
|`privacyNoticeAt`|Универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.|
|`privacyNoticeVersion`|Версия текущего примечания о конфиденциальности.|
|`proxyAddress`|Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP. Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`. Значение по умолчанию — `null`.|
|`receiveTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:10:00.|
|`sendTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|
|`textEncoding`|Задает кодировку, используемую при отправке сообщений через привязку. Допустимы следующие значения:<br /><br /> -BigEndianUnicode: Обратный порядок байтов кодировка Юникод.<br />-Юникод. 16-разрядная кодировка.<br />-UTF8: 8-разрядная кодировка.<br /><br /> Значение по умолчанию - UTF8. Это атрибут типа <xref:System.Text.Encoding>.|
|`transactionFlow`|Значение, определяющее, поддерживает ли привязка потоки WS-Transactions. Значение по умолчанию — `false`.|
|`useDefaultWebProxy`|Значение, указывающее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP. Если данный атрибут имеет значение `null`, прокси-адрес должен быть равен `true` (то есть не задан). Значение по умолчанию — `true`.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание:|
|-------------|-----------------|
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|Определяет параметры безопасности сообщения. Это элемент типа <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|
|[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Указывает, устанавливаются ли между конечными точками канала надежные сеансы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<привязки >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|

## <a name="remarks"></a>Примечания

Федерация - это возможность совместного использования удостоверений между несколькими предприятиями или доверенными доменами в целях проверки подлинности и авторизации. Для сопоставления представления идентификации между доверенными доменами используется протокол WS-Trust. Федеративная привязка HTTP поддерживает безопасность SOAP, а также безопасность в смешанном режиме, но она не поддерживает безопасность транспорта. Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP. Дополнительные сведения см. в разделе [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).

## <a name="example"></a>Пример

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
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

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../../../docs/framework/misc/binding.md)
