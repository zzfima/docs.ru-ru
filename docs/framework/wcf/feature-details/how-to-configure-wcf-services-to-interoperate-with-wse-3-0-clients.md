---
title: "Как настраивать службы WCF для взаимодействия с клиентами WSE 3.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как настраивать службы WCF для взаимодействия с клиентами WSE 3.0
Службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] на уровне каналов связи совместимы с клиентами расширений веб\-служб версии 3.0 для Microsoft .NET \(WSE\), если службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] настроены на использование спецификации WS\-Addressing \(версия от августа 2004 г.\).  
  
### Включение службы WCF для взаимодействия с клиентами WSE 3.0  
  
1.  Определите пользовательскую привязку для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
     Чтобы указать, что для кодирования сообщений используется версия спецификации WS\-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.  
  
    1.  Добавьте дочерний элемент [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в элемент [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации службы.  
  
    2.  Задайте имя привязки, добавив элемент [\<привязка\>](../../../../docs/framework/misc/binding.md) в элемент [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) и указав атрибут `name`.  
  
    3.  Задайте режим проверки подлинности и версию спецификации WS\-Security, которые используются для защиты сообщений, совместимых с WSE 3.0. Для этого добавьте дочерний элемент [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) в элемент [\<привязка\>](../../../../docs/framework/misc/binding.md).  
  
         Чтобы установить режим проверки подлинности, задайте атрибут `authenicationMode` элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0.В следующей таблице показано соответствие между режимами проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и готовыми к использованию утверждениями безопасности в WSE 3.0.  
  
        |Режим проверки подлинности WCF|Готовое к использованию утверждение безопасности WSE 3.0|  
        |------------------------------------|--------------------------------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate10Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate11Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameForCertificateSecurity`|  
  
         \* Одно из основных различий между готовыми к использованию утверждениями безопасности `mutualCertificate10Security` и `mutualCertificate11Security` связано с версией спецификации WS\-Security, используемой в WSE для защиты сообщений SOAP.Для `mutualCertificate10Security` используется версия WS\-Security 1.0, а для `mutualCertificate11Security` — версия WS\-Security 1.1.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] версия спецификации WS\-Security задается в атрибуте `messageSecurityVersion` элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Чтобы определить версию спецификации WS\-Security, используемую для защиты сообщений SOAP, задайте атрибут `messageSecurityVersion` элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Укажите, что в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется версия спецификации WS\-Addressing от августа 2004 г., добавив элемент [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) и задав для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2.  Укажите, что служба использует пользовательскую привязку.  
  
    1.  Задайте для атрибута `binding` элемента [\<конечная точка\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) значение `customBinding`.  
  
    2.  Задайте для атрибута `bindingConfiguration` элемента [\<конечная точка\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) значение, указанное в атрибуте `name` элемента [\<привязка\>](../../../../docs/framework/misc/binding.md) пользовательской привязки.  
  
## Пример  
 Следующий пример кода задает, что служба `Service.HelloWorldService` использует для взаимодействия с клиентами WSE 3.0 пользовательскую привязку.Пользовательская привязка задает, что для кодирования пересылаемых сообщений используется версия спецификация WS\-Addressing от августа 2004 г. и набор спецификаций WS\-Security 1.1.Защита сообщений обеспечивается с помощью режима проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode>.  
  
```  
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
  
## См. также  
 [Практическое руководство. Изменение привязки, предоставляемой системой](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)