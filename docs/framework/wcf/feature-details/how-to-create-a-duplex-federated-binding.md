---
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 3ecd9e2dbeb30bb255cbf66488b50a9b20219431
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141714"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Практическое руководство. Создание дуплексной федеративной привязки

Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос-ответ». Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку. В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP. Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.

Также можно создать привязку в коде. Описание создаваемого стека элементов привязки см. в разделе [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Создание дуплексной федеративной пользовательской привязки с использованием HTTP

1. В [\<привязках >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узле файла конфигурации создайте элемент [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. В элементе [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) создайте элемент [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) с атрибутом `name`, для которого задано значение `FederationDuplexHttpMessageSecurityBinding`.

3. В элементе [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) создайте элемент [\<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) с атрибутом `authenticationMode`, для которого задано значение `SecureConversation`.

4. В элементе [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) создайте элемент [\<секуреконверсатионбутстрап >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) с атрибутом `authenticationMode`, имеющим значение `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.

5. После элемента [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) создайте пустой элемент [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) .

6. После элемента [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) создайте пустой элемент [\<OneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) .

7. После элемента [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) создайте пустой элемент [\<хттптранспорт >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) .

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP

1. В [\<привязках >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узле файла конфигурации создайте элемент [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. В элементе [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) создайте элемент [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) с атрибутом `name`, для которого задано значение `FederationDuplexTcpMessageSecurityBinding`.

3. В элементе [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) создайте элемент [\<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) с атрибутом `authenticationMode`, для которого задано значение `SecureConversation`.

4. В элементе [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) создайте элемент [\<секуреконверсатионбутстрап >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) с атрибутом `authenticationMode`, имеющим значение `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.

5. После элемента [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) создайте пустой элемент [\<tcpTransport платформы >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) .

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP

1. В [\<привязках >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узле файла конфигурации создайте элемент [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. В элементе [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) создайте элемент [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) с атрибутом `name`, для которого задано значение `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.

3. В элементе [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) создайте элемент [\<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) с атрибутом `authenticationMode`, для которого задано значение `SecureConversation`.

4. В элементе [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) создайте элемент [\<секуреконверсатионбутстрап >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) с атрибутом `authenticationMode`, имеющим значение `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.

5. После элемента [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) создайте пустой элемент [\<раздел sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) .

6. После элемента [\<раздел sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) создайте пустой элемент [\<tcpTransport платформы >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) .

## <a name="code-sample"></a>Образец кода

### <a name="sample-with-3-bindings"></a>Образец с 3 привязками

1. Вставьте следующий код в свой файл конфигурации.

## <a name="example"></a>Пример

```xml
<bindings>
   <customBinding>
      <binding name="FederationDuplexHttpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <compositeDuplex />
          <oneWay />
          <httpTransport />
       </binding>
<!-- duplex over https is not supported -->
       <binding name="FederationDuplexTcpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <tcpTransport />
       </binding>
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />
          </security>
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->
          <sslStreamSecurity />
          <tcpTransport />
       </binding>
    </customBinding>
</bindings>
```
