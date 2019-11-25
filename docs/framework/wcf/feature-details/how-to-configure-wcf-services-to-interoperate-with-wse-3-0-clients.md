---
title: Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: bd9f2bec94ca45f76590f64366428a00edd5d6ea
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141745"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0

Службы Windows Communication Foundation (WCF) являются совместимыми с расширениями веб-служб 3,0 для клиентов Microsoft .NET (WSE), если службы WCF настроены для использования версии WS-Addressing в августе 2004.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Включение службы WCF для взаимодействия с клиентами WSE 3.0

1. Определите пользовательскую привязку для службы WCF.

    Чтобы указать, что для кодирования сообщений используется версия спецификации WS-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.

    1. Добавьте дочерний [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в [привязки\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации службы.

    2. Укажите имя привязки, добавив [> привязку\<](../../configure-apps/file-schema/wcf/bindings.md) в [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) и установив атрибут `name`.

    3. Укажите режим проверки подлинности и версию спецификаций WS-Security, которые используются для защиты сообщений, совместимых с WSE 3,0, добавив дочерний [\<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) в [\<привязки >](../../configure-apps/file-schema/wcf/bindings.md).

        Чтобы задать режим проверки подлинности, установите атрибут `authenticationMode` [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0. Следующая таблица сопоставляет режимы проверки подлинности в WCF с готовыми утверждениями безопасности в WSE 3,0.

        |Режим проверки подлинности WCF|Готовое к использованию утверждение безопасности WSE 3.0|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \* одного из основных различий между утверждениями безопасности `mutualCertificate10Security` и `mutualCertificate11Security` является версия спецификации WS-Security, которую WSE использует для защиты сообщений SOAP. Для `mutualCertificate10Security` используется версия WS-Security 1.0, а для `mutualCertificate11Security` - версия WS-Security 1.1. Для WCF версия спецификации WS-Security указывается в атрибуте `messageSecurityVersion` [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).

        Чтобы задать версию спецификации WS-Security, используемую для защиты сообщений SOAP, установите атрибут `messageSecurityVersion` [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.

    4. Укажите, что в WCF используется версия спецификации WS-Addressing 2004 августа, добавив [\<текстмессажеенкодинг >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) и установив для `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.

        > [!NOTE]
        > При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.

2. Укажите, что служба использует пользовательскую привязку.

    1. Установите атрибут `binding` элемента [> конечной точки\<](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) в значение `customBinding`.

    2. Задайте атрибуту `bindingConfiguration` элемента [\<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) значение, указанное в атрибуте `name` [\<привязки >](../../configure-apps/file-schema/wcf/bindings.md) для пользовательской привязки.

## <a name="example"></a>Пример

Следующий пример кода задает, что служба `Service.HelloWorldService` использует для взаимодействия с клиентами WSE 3.0 пользовательскую привязку. Пользовательская привязка задает, что для кодирования пересылаемых сообщений используется версия спецификация WS-Addressing от августа 2004 г. и набор спецификаций WS-Security 1.1. Защита сообщений обеспечивается с помощью режима проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.

```xml
<configuration>
  <system.serviceModel>
    <services>
      <service
        behaviorConfiguration="ServiceBehavior"
        name="Service.HelloWorldService">
        <endpoint binding="customBinding" address=""
          bindingConfiguration="ServiceBinding"
          contract="Service.IHelloWorld"></endpoint>
      </service>
    </services>

    <bindings>
      <customBinding>
        <binding name="ServiceBinding">
          <security authenticationMode="AnonymousForCertificate"
                  messageProtectionOrder="SignBeforeEncrypt"
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"
                  requireDerivedKeys="false">
          </security>
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>
          <httpTransport/>
        </binding>
      </customBinding>
    </bindings>
    <behaviors>
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">
        <serviceCredentials>
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>
        </serviceCredentials>
      </behavior>
    </behaviors>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>См. также

- [Практическое руководство. Изменение привязки, предоставляемой системой](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
