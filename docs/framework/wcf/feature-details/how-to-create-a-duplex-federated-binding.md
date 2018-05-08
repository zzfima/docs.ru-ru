---
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: d736d0119f3e938d81a15d57bb6d97ca2a1990fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Практическое руководство. Создание дуплексной федеративной привязки
Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос-ответ». Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку. В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP. Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.  
  
 Также можно создать привязку в коде. Описание стек элементов привязки, чтобы создать см. [как: Создание привязки настраиваемый с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Создание дуплексной федеративной пользовательской привязки с использованием HTTP  
  
1.  В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемента.  
  
2.  Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создайте [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибуту присвоено значение `FederationDuplexHttpMessageSecurityBinding`.  
  
3.  Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создайте [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибуту присвоено значение `SecureConversation`.  
  
4.  Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создайте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.  
  
5.  Следующая [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) элемента.  
  
6.  Следующая [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) элемент, создать пустой [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) элемента.  
  
7.  Следующая [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) элемент, создать пустой [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) элемента.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP  
  
1.  В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемента.   
  
2.  Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создайте [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибуту присвоено значение `FederationDuplexTcpMessageSecurityBinding`.  
  
3.  Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создайте [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибуту присвоено значение `SecureConversation`.  
  
4.  Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создайте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.  
  
5.  Следующая [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) элемента.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP  
  
1.  В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемента.   
  
2.  Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создайте [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибуту присвоено значение `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.  
  
3.  Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создайте [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибуту присвоено значение `SecureConversation`.  
  
4.  Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создайте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.  
  
5.  После [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) элемента.  
  
6.  Следующая [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) элемент, создать пустой [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) элемента.  
  
## <a name="code-sample"></a>Образец кода  
  
#### <a name="sample-with-3-bindings"></a>Образец с 3 привязками  
  
1.  Вставьте следующий код в свой файл конфигурации.  
  
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
