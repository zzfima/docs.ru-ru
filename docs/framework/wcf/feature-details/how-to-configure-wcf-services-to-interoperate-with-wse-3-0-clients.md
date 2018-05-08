---
title: Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 174ecd279f9380136532ce0d5105b7a71b6d88da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
Службы Windows Communication Foundation (WCF) совместимы транспортного уровня с веб-служб версии 3.0 для клиентов Microsoft .NET (WSE) службы WCF настроены для использования версии спецификации WS-Addressing августа 2004 г.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Включение службы WCF для взаимодействия с клиентами WSE 3.0  
  
1.  Определите пользовательскую привязку для службы WCF.  
  
     Чтобы указать, что для кодирования сообщений используется версия спецификации WS-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.  
  
    1.  Добавить дочерний элемент [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) для [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации службы.  
  
    2.  Укажите имя для привязки, добавляя [ \<привязки >](../../../../docs/framework/misc/binding.md) для [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) и параметр `name` атрибута.  
  
    3.  Укажите режим проверки подлинности и версии спецификации WS-Security, которые используются для защиты сообщений, которые совместимы с WSE 3.0, путем добавления дочернего [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) для [ \<привязки >](../../../../docs/framework/misc/binding.md).  
  
         Чтобы задать режим проверки подлинности, установите `authenicationMode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0. Следующая таблица показывает сопоставление режимов проверки подлинности в WCF для готовые утверждения безопасности в WSE 3.0.  
  
        |Режим проверки подлинности WCF|Готовое к использованию утверждение безопасности WSE 3.0|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* Одно из основных различий между `mutualCertificate10Security` и `mutualCertificate11Security` готовые утверждения безопасности — это версия спецификации WS-Security, используемой в WSE для защиты сообщений SOAP. Для `mutualCertificate10Security` используется версия WS-Security 1.0, а для `mutualCertificate11Security` - версия WS-Security 1.1. Для WCF, версия спецификации WS-Security, указанная в `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Чтобы установить версию спецификации WS-Security, который используется для защиты сообщений SOAP, задайте `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Укажите версию спецификации WS-Addressing августа 2004 г. Использование, WCF, добавив [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) и задайте `messageVersion` для него значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2.  Укажите, что служба использует пользовательскую привязку.  
  
    1.  Задать `binding` атрибут [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент `customBinding`.  
  
    2.  Задать `bindingConfiguration` атрибут [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемента значение, указанное в `name` атрибут [ \<привязки >](../../../../docs/framework/misc/binding.md) настраиваемый привязка.  
  
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
 [Практическое руководство. Изменение привязки, предоставляемой системой](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
