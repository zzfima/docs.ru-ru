---
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972061"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Практическое руководство. Создание дуплексной федеративной привязки

Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос-ответ». Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку. В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP. Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.

Также можно создать привязку в коде. Описание создаваемого стека элементов привязки см. в разделе [как Создайте пользовательскую привязку с помощью](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)SecurityBindingElement.

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Создание дуплексной федеративной пользовательской привязки с использованием HTTP

1. В узле привязки > [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файла конфигурации создайте элемент CustomBinding >. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)

2. `name` `FederationDuplexHttpMessageSecurityBinding` [ В\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элементе CustomBinding > Создайте элемент [> привязкисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/misc/binding.md)

3. `authenticationMode` `SecureConversation` [ В\<](../../../../docs/framework/misc/binding.md) элементе Binding > Создайте элемент [> безопасностисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

4. `IssuedTokenForSslNegotiated`В элементе >`authenticationMode` безопасностисоздайте`IssuedTokenForCertificate` элемент [> секуреконверсатионбутстрап,атрибуткоторогоимеетзначениеили.\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

5. После элемента [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Security > Создайте пустой элемент > compositeDuplex. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

6. После элемента [> compositeDuplexсоздайтепустойэлемент>OneWay.\<](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)

7. После элемента [> OneWayсоздайтепустойэлемент>хттптранспорт.\<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP

1. В узле привязки > [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файла конфигурации создайте элемент CustomBinding >. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)

2. `name` `FederationDuplexTcpMessageSecurityBinding` [ В\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элементе CustomBinding > Создайте элемент [> привязкисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/misc/binding.md)

3. `authenticationMode` `SecureConversation` [ В\<](../../../../docs/framework/misc/binding.md) элементе Binding > Создайте элемент [> безопасностисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

4. `IssuedTokenForSslNegotiated`В элементе >`authenticationMode` безопасностисоздайте`IssuedTokenForCertificate` элемент [> секуреконверсатионбутстрап,атрибуткоторогоимеетзначениеили.\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

5. После элемента [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Security > Создайте пустой элемент > tcpTransport платформы. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP

1. В узле привязки > [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файла конфигурации создайте элемент CustomBinding >. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)

2. `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` [ В\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элементе CustomBinding > Создайте элемент [> привязкисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/misc/binding.md)

3. `authenticationMode` `SecureConversation` [ В\<](../../../../docs/framework/misc/binding.md) элементе Binding > Создайте элемент [> безопасностисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

4. `IssuedTokenForSslNegotiated`В элементе >`authenticationMode` безопасностисоздайте`IssuedTokenForCertificate` элемент [> секуреконверсатионбутстрап,атрибуткоторогоимеетзначениеили.\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

5. После элемента [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Security > Создайте пустой элемент > раздел sslstreamsecurity. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

6. После элемента [> разделsslstreamsecurityсоздайтепустойэлемент>tcpTransportплатформы.\<](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)

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
