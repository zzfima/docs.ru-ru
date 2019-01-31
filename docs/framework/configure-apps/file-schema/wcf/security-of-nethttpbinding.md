---
title: <security> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283975"
---
# <a name="security-of-nethttpbinding"></a>\<Безопасность > из \<netHttpBinding >

Определяет возможности безопасности [ \<basicHttpBinding >](basichttpbinding.md).

\<system.ServiceModel>\
\<привязки > \
\<netHttpBinding > \
\<Привязка > \
\<Безопасность >

## <a name="syntax"></a>Синтаксис

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|режим|Необязательно. Задает тип используемого механизма обеспечения безопасности. Значение по умолчанию — `None`. Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.|

## <a name="mode-attribute"></a>Атрибут Mode

|Значение|Описание|
|-----------|-----------------|
|Нет|-Сообщения не защищены во время передачи.|
|Transport|Безопасность обеспечивается с помощью транспорта HTTPS. Сообщения SOAP защищаются при помощи HTTPS. Служба проходит проверку подлинности для клиента с использованием сертификата X.509. Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.|
|Сообщение|Безопасность обеспечивается с помощью средств безопасности сообщений SOAP. По умолчанию текст сообщений шифруется и подписывается. Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала. Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.|
|TransportWithMessageCredential|Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта. Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP. Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.|
|TransportCredentialOnly|Данный режим не обеспечивает целостности и конфиденциальности сообщений. Он предоставляет проверку подлинности клиента на основе http. Этот режим следует использовать с осторожностью. Он должен использоваться в средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а только проверку подлинности клиента с помощью инфраструктуры WCF.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание:|
|-------------|-----------------|
|[\<Транспорт >](transport-of-nethttpbinding.md)|Определяет параметры безопасности транспорта для базовой службы HTTP. Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.|
|[\<сообщение >](message-of-nethttpbinding.md)|Определяет параметры безопасности сообщений для базовой службы HTTP. Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|привязка|Элемент привязки [ \<basicHttpBinding >](basichttpbinding.md).|

## <a name="remarks"></a>Примечания

 По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется. Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `netHttpBinding`.

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Выбор типа учетных данных](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
