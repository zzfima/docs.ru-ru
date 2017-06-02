---
title: "Режимы проверки подлинности SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 12300bf4-c730-4405-9f65-d286f68b5a43
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Режимы проверки подлинности SecurityBindingElement
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] имеется несколько режимов, с помощью которых клиенты и службы проверяют подлинность друг друга.Для этих режимов проверки подлинности можно создать привязки безопасности с помощью статических методов класса <xref:System.ServiceModel.Channels.SecurityBindingElement> или с помощью конфигурации.В этом разделе кратко описано 18 режимов проверки подлинности.  
  
 Пример использования данного элемента для одного из режимов проверки подлинности см. в разделе [Как создать SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## Базовое программирование конфигурации  
 Ниже описано, как задать режим проверки подлинности в файле конфигурации.  
  
#### Задание режима проверки подлинности в файле конфигурации  
  
1.  Добавьте элемент [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в элемент [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
2.  Добавьте элемент `<customBinding>` в качестве дочернего для элемента [\<привязка\>](../../../../docs/framework/misc/binding.md).  
  
3.  Добавьте элемент `<security>` в элемент `<binding>`.  
  
4.  Задайте для атрибута `authenticationMode` одно из описанных ниже значений.Например, следующий код задает режим `AnonymousForCertificate`.  
  
    ```  
    <bindings>  
      <customBinding>  
        <binding name="SecureCustomBinding">  
         <security authenticationMode ="AnonymousForCertificate" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
#### Задание режима программным образом  
  
1.  Определите возвращаемый тип, который может быть следующим: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2.  Вызовите соответствующий статический метод класса <xref:System.ServiceModel.Channels.SecurityBindingElement>.Например, в следующем фрагменте кода вызывается метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>.  
  
     [!code-csharp[c_CustomBindingsAuthMode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#3)]
     [!code-vb[c_CustomBindingsAuthMode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#3)]  
  
3.  С помощью элемента привязки создайте пользовательскую привязку.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## Описание режимов  
  
### AnonymousForCertificate  
 В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509.Элементом привязки безопасности является объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>.Можно также задать для атрибута `authenticationMode` элемента \<`security`\> значение `AnonymousForCertificate`.  
  
### AnonymousForSslNegotiated  
 В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509, который определяется во время выполнения.Элементом привязки безопасности является объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A>, если в качестве первого параметра передается значение `false`.Можно также задать для атрибута `authenticationMode` значение `AnonymousForSslNegotiated`.  
  
### CertificateOverTransport  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве разрешающего вспомогательного маркера, т. е. маркера, которым подписана подпись сообщения.Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.Элементом привязки безопасности является объект <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateCertificateOverTransportBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `CertificateOverTransport`.  
  
### IssuedToken  
 В этом режиме проверки подлинности клиент не проходит проверку подлинности на стороне службы; вместо этого клиент проходит проверку на стороне службы маркеров безопасности, получает маркер SAML, который затем представляет серверу, и, тем самым, подтверждает набор знаний общего ключа.Служба не проходит как таковую проверку подлинности на стороне клиента, но служба маркеров безопасности шифрует общий ключ в рамках выдаваемого маркера, чтобы только служба могла расшифровать этот ключ.Элементом привязки безопасности является объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `IssuedToken`.  
  
### IssuedTokenForCertificate  
 В этом режиме проверки подлинности клиент не проходит проверку подлинности на стороне службы; вместо этого клиент проходит проверку на стороне службы маркеров безопасности, получает маркер SAML, который затем представляет серверу, и, тем самым, подтверждает набор знаний общего ключа.Выданный маркер доступен на уровне SOAP в качестве разрешающего вспомогательного маркера либо в качестве маркера, не являющегося подтверждающим, т. е. маркера, которым подписана сигнатура сообщения.Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509.Элементом привязки безопасности является объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `IssuedTokenForCertificate`.  
  
### IssuedTokenForSslNegotiated  
 В этом режиме проверки подлинности клиент не проходит проверку подлинности на стороне службы; вместо этого клиент проходит проверку на стороне службы маркеров безопасности, получает маркер SAML, который затем представляет серверу, и, тем самым, подтверждает набор знаний общего ключа.Выданный маркер доступен на уровне SOAP в качестве разрешающего вспомогательного маркера либо в качестве маркера, не являющегося подтверждающим, т. е. маркера, которым подписана сигнатура сообщения.Служба проходит проверку подлинности с использованием сертификата X.509.Элементом привязки безопасности является объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `IssuedTokenForSslnegotiated`.  
  
### IssuedTokenOverTransport  
 В этом режиме проверки подлинности клиент не проходит проверку подлинности на стороне службы; вместо этого клиент проходит проверку на стороне службы маркеров безопасности, получает маркер SAML, который затем представляет серверу, и, тем самым, подтверждает набор знаний общего ключа.Выданный маркер доступен на уровне SOAP в качестве разрешающего вспомогательного маркера либо в качестве маркера, не являющегося подтверждающим, т. е. маркера, которым подписана сигнатура сообщения.Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.Элементом привязки безопасности является объект `TransportSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `IssuedTokenOverTransport`.  
  
### Kerberos  
 В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos.Этот же билет обеспечивает проверку подлинности сервера.Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `Kerberos`.  
  
> [!NOTE]
>  Для использования этого режима проверки подлинности учетная запись службы должна быть связана с именем участника\-службы \(SPN\).Для этого запустите службу от имени учетной записи NETWORK SERVICE или LOCAL SYSTEM.Для создания для учетной записи службы имени участника\-службы также можно воспользоваться средством SetSpn.exe.В обоих случаях клиент должен указать в элементе [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) правильное имя участника\-службы либо воспользоваться конструктором <xref:System.ServiceModel.EndpointAddress>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Идентификация и проверка подлинности службы](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
> [!NOTE]
>  При использовании режима проверки подлинности `Kerberos` уровни олицетворения <xref:System.Security.Principal.TokenImpersonationLevel> и <xref:System.Security.Principal.TokenImpersonationLevel> не поддерживаются.  
  
### KerberosOverTransport  
 В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos.Маркер Kerberos доступен на уровне SOAP в качестве разрешающего вспомогательного маркера, т. е. маркера, которым подписана подпись сообщения.Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.Элементом привязки безопасности является объект `TransportSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosOverTransportBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `KerberosOverTransport`.  
  
> [!NOTE]
>  Для использования этого режима проверки подлинности учетная запись службы должна быть связана с именем участника\-службы \(SPN\).Для этого запустите службу от имени учетной записи NETWORK SERVICE или LOCAL SYSTEM.Для создания для учетной записи службы имени участника\-службы также можно воспользоваться средством SetSpn.exe.В обоих случаях клиент должен указать в элементе [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) правильное имя участника\-службы либо воспользоваться конструктором <xref:System.ServiceModel.EndpointAddress>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Идентификация и проверка подлинности службы](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
### MutualCertificate  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве разрешающего вспомогательного маркера, т. е. маркера, которым подписана подпись сообщения.Служба также проходит проверку подлинности с использованием сертификата X.509.Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `MutualCertificate`.  
  
### MutualCertificateDuplex  
 В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве разрешающего вспомогательного маркера, т. е. маркера, которым подписана подпись сообщения.Служба также проходит проверку подлинности с использованием сертификата X.509.Привязкой является элемент `AsymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateDuplexBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `MutualCertificateDuplex`.  
  
### MutalSslNegotiation  
 В этом режиме проверка подлинности клиента и службы осуществляется с использованием сертификатов X.509.Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A>, если в качестве первого параметра передается значение `true`.Можно также задать для атрибута `authenticationMode` значение `MutualSslNegotiated`.  
  
### SecureConversation  
 Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>.Этот метод принимает в качестве параметра объект <xref:System.ServiceModel.Channels.SecurityBindingElement>, который используется во время инициализации для установки защищенного сеанса.Можно также задать для атрибута `authenticationMode` значение `SecureConversation`.  
  
 Если привязка начальной загрузки не задана, то для начальной загрузки используется режим проверки подлинности `SspiNegotiated`.  
  
### SspiNegotiation  
 В этом режиме для проверки подлинности клиента и сервера используется протокол согласования.Если это возможно, используется протокол Kerberos, в противном случае — протокол NT LanMan \(NTLM\).Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `SspiNegotiated`.  
  
### SspiNegotiatedOverTransport  
 В этом режиме для проверки подлинности клиента и сервера используется протокол согласования.Если это возможно, используется протокол Kerberos, в противном случае — протокол NTLM.Результирующий маркер доступен на уровне SOAP в качестве разрешающего вспомогательного маркера, т. е. маркера, которым подписана подпись сообщения.Служба проходит дополнительную проверку подлинности на транспортном уровне с использованием сертификата X.509.Элементом привязки безопасности является объект `TransportSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationOverTransportBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `SspiNegotiatedOverTransport`.  
  
### UserNameForCertificate  
 В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием маркера имени пользователя, который доступен на уровне SOAP в качестве подписанного вспомогательного маркера, т. е. маркера, который подписан подписью сообщения.Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509.Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `UserNameForCertificate`.  
  
 В режиме проверки подлинности `UserNameForCertificate` клиент и служба должны использовать протокол WS\-Security 1.1.  
  
### UserNameForSslNegotiated  
 В этом режиме проверка подлинности клиента осуществляется с использованием маркера имени пользователя, который доступен на уровне SOAP в качестве подписанного вспомогательного маркера, т. е. маркера, который подписан подписью сообщения.Служба проходит проверку подлинности с использованием сертификата X.509.Элементом привязки безопасности является объект `SymmetricSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForSslBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `UserNameForSslNegotiated`.  
  
### UserNameOverTransport  
 В этом режиме проверка подлинности клиента осуществляется с использованием маркера имени пользователя, который доступен на уровне SOAP в качестве подписанного вспомогательного маркера, т. е. маркера, который подписан подписью сообщения.Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.Элементом привязки безопасности является объект `TransportSecurityBindingElement`, возвращаемый методом <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameOverTransportBindingElement%2A>.Можно также задать для атрибута `authenticationMode` значение `UserNameOverTransport`.  
  
## См. также  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 [Как создать SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)