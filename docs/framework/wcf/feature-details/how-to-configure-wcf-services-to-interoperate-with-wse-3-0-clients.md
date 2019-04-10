---
title: Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 8f4407f66095f97a213d6cd987b4bd9a3ed340fa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303899"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
Службы Windows Communication Foundation (WCF) совместимы на уровне линий связи с Web Services Enhancements 3.0 для клиентов Microsoft .NET (WSE) при настройке службы WCF для использования версии спецификации WS-Addressing от августа 2004 г.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Включение службы WCF для взаимодействия с клиентами WSE 3.0  
  
1. Определите пользовательскую привязку для службы WCF.  
  
     Чтобы указать, что для кодирования сообщений используется версия спецификации WS-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.  
  
    1.  Добавить учетную запись ребенка [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) для [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации службы.  
  
    2.  Укажите имя для привязки, добавив [ \<привязки >](../../../../docs/framework/misc/binding.md) для [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) и параметр `name` атрибута.  
  
    3.  Укажите режим проверки подлинности и версию спецификации WS-Security, которые используются для защиты сообщений, совместимых с WSE 3.0, добавив дочерний элемент [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) для [ \<привязки >](../../../../docs/framework/misc/binding.md).  
  
         Чтобы задать режим проверки подлинности, задайте `authenicationMode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0. В следующей таблице сопоставлены режимы проверки подлинности в WCF для утверждения готовое к использованию безопасности в WSE 3.0.  
  
        |Режим проверки подлинности WCF|Готовое к использованию утверждение безопасности WSE 3.0|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* Одно из основных различий между `mutualCertificate10Security` и `mutualCertificate11Security` утверждения готовое к использованию безопасности — это версия спецификации WS-Security, используемой в WSE для защиты сообщений SOAP. Для `mutualCertificate10Security` используется версия WS-Security 1.0, а для `mutualCertificate11Security` - версия WS-Security 1.1. Для WCF, версия спецификации WS-Security, указанная в `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Чтобы определить версию спецификации WS-Security, который используется для защиты сообщений SOAP, задать `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Укажите, что спецификации WS-Addressing версии августа 2004 г., используется платформой WCF, добавив [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) и задайте `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2. Укажите, что служба использует пользовательскую привязку.  
  
    1.  Задайте `binding` атрибут [ \<конечной точки >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент `customBinding`.  
  
    2.  Задайте `bindingConfiguration` атрибут [ \<конечной точки >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемента к значению, указанному в `name` атрибут [ \<привязки >](../../../../docs/framework/misc/binding.md) для настраиваемого привязка.  
  
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
