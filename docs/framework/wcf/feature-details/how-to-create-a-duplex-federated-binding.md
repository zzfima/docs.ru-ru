---
title: "Как создавать дуплексную федеративную привязку | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Как создавать дуплексную федеративную привязку
Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос\-ответ».Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку.В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP.Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.  
  
 Также можно создать привязку в коде.Описание процедуры создания стека элементов привязки см. в разделе [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### Создание дуплексной федеративной пользовательской привязки с использованием HTTP  
  
1.  В узле [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)[\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2.  Внутри элемента [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)[\<привязка\>](../../../../docs/framework/misc/binding.md)`name` `и присвойте атрибуту FederationDuplexHttpMessageSecurityBinding` значение .  
  
3.  Внутри элемента [\<привязка\>](../../../../docs/framework/misc/binding.md)[\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode` `и присвойте атрибуту SecureConversation` значение .  
  
4.  Внутри элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode` `и присвойте атрибуту IssuedTokenForCertificate` `значение IssuedTokenForSslNegotiated` или .  
  
5.  После элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md).  
  
6.  После элемента [\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md).  
  
7.  После элемента [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
### Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP  
  
1.  В узле [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md).  
  
2.  Внутри элемента [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)`name` `и присвойте атрибуту FederationDuplexTcpMessageSecurityBinding` значение .  
  
3.  Внутри элемента [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode` `и присвойте атрибуту SecureConversation` значение .  
  
4.  Внутри элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode` `и присвойте атрибуту IssuedTokenForCertificate` `значение IssuedTokenForSslNegotiated` или .  
  
5.  После элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md).  
  
### Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP  
  
1.  В узле [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md).  
  
2.  Внутри элемента [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)`name` `и присвойте атрибуту FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` значение .  
  
3.  Внутри элемента [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode` `и присвойте атрибуту SecureConversation` значение .  
  
4.  Внутри элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode` `и присвойте атрибуту IssuedTokenForCertificate` `значение IssuedTokenForSslNegotiated` или .  
  
5.  После элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md).  
  
6.  После элемента [\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)[\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md).  
  
## Образец кода  
  
#### Образец с 3 привязками  
  
1.  Вставьте следующий код в свой файл конфигурации.  
  
## Пример  
  
```  
  
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