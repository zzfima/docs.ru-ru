---
title: "Как настраивать учетные данные службы федерации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "федерация"
  - "WCF, федерация"
ms.assetid: 149ab165-0ef3-490a-83a9-4322a07bd98a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Как настраивать учетные данные службы федерации
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] процесс создания федеративной службы состоит из следующих основных процедур.  
  
1.  Настройка <xref:System.ServiceModel.WSFederationHttpBinding> или аналогичной пользовательской привязки.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о создании соответствующей привязки см. в разделе [Практическое руководство. Создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).  
  
2.  Настройка объекта <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>, который определяет порядок проверки подлинности выданных маркеров, которые предоставляются службе.  
  
 В этом разделе описывается второй этап.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о работе федеративной службы см. в разделе [Федерация](../../../../docs/framework/wcf/feature-details/federation.md).  
  
### Задание свойств объекта IssuedTokenServiceCredential в коде  
  
1.  Свойство <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A> класса <xref:System.ServiceModel.Description.ServiceCredentials> служит для возврата ссылки на экземпляр <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>.Доступ к этому свойству осуществляется через свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> класса <xref:System.ServiceModel.ServiceHostBase>.  
  
2.  Задайте для свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> значение `true`, если требуется проверять подлинность самостоятельно выданных маркеров, например карт [!INCLUDE[infocard](../../../../includes/infocard-md.md)].Значение по умолчанию — `false`.  
  
3.  Заполните коллекцию, возвращаемую свойством <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>, экземплярами класса <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.Каждый экземпляр представляет издателя, для которого служба будет проверять подлинность маркеров.  
  
    > [!NOTE]
    >  В отличие от клиентской коллекции, возвращаемой свойством <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>, коллекция известных сертификатов не является коллекцией с ключом.Служба принимает маркеры, выдаваемые заданным сертификатом, независимо от адреса клиента, который отправил сообщение с выданным маркером \(на него накладываются дополнительные ограничения, описанные ниже в этом разделе\).  
  
4.  Присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> одно из значений перечисления <xref:System.ServiceModel.Security.X509CertificateValidationMode>.Это можно сделать только в коде.Значение по умолчанию — <xref:System.IdentityModel.Selectors.X509CertificateValidator.ChainTrust%2A>.  
  
5.  Если свойство <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> имеет значение <xref:System.ServiceModel.Security.X509CertificateValidationMode>, присвойте экземпляр пользовательского класса <xref:System.IdentityModel.Selectors.X509CertificateValidator> свойству <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.  
  
6.  Если свойство <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> имеет значение `ChainTrust` или `PeerOrChainTrust`, присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.RevocationMode%2A> соответствующее значение из перечисления <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.Обратите внимание, что в режимах проверки `PeerTrust` и `Custom`, режим отзыва не используется.  
  
7.  Если необходимо, присвойте экземпляр пользовательского класса <xref:System.IdentityModel.Tokens.SamlSerializer> свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.SamlSerializer%2A>.Пользовательский сериализатор языка Security Assertions Markup Language \(SAML\) требуется, например, для анализа пользовательских утверждений SAML.  
  
### Задание свойств объекта IssuedTokenServiceCredential в файле конфигурации  
  
1.  Создайте элемент `<issuedTokenAuthentication>`, являющийся дочерним для элемента \<`serviceCredentials`\>.  
  
2.  Задайте для атрибута `allowUntrustedRsaIssuers` элемента `<issuedTokenAuthentication>` значение `true`, если проверяется подлинность выданного самостоятельно маркера, например карты [!INCLUDE[infocard](../../../../includes/infocard-md.md)].  
  
3.  Создайте элемент `<knownCertificates>`, являющийся дочерним для элемента `<issuedTokenAuthentication>`.  
  
4.  Создайте ноль или несколько элементов `<add>`, являющихся дочерними для элемента `<knownCertificates>`, и с помощью атрибутов `storeLocation`, `storeName`, `x509FindType` и `findValue` укажите, каким образом обнаружить сертификат.  
  
5.  Если необходимо, задайте для атрибута `samlSerializer` элемента \<`issuedTokenAuthentication`\> имя типа пользовательского класса <xref:System.IdentityModel.Tokens.SamlSerializer>.  
  
## Пример  
 В следующем примере свойства объекта <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> задаются в коде.  
  
 [!code-csharp[C_FederatedService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedservice/cs/source.cs#2)]
 [!code-vb[C_FederatedService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedservice/vb/source.vb#2)]  
  
 Чтобы федеративная служба проверяла подлинность клиента, для выданного маркера должны выполняться следующие условия:  
  
-   если в цифровой сигнатуре выданного маркера используется идентификатор ключа безопасности RSA, свойство <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> должно иметь значение `true`;  
  
-   если в подписи выданного маркера используется серийный номер издателя X.509, идентификатор ключа субъекта X.509 или идентификатор безопасности отпечатка X.509, выданный маркер должен быть подписан сертификатом из коллекции, возвращаемой свойством <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> класса <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>;  
  
-   если выданный маркер подписан с помощью сертификата X.509, этот сертификат должен осуществлять проверку на основании семантики, определенной значением свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>, независимо от того, был ли сертификат отправлен проверяющей стороне в качестве объекта <xref:System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause> или же получен из свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] проверке сертификатов X.509 см. в разделе [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 Например, установка свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> равным <xref:System.ServiceModel.Security.X509CertificateValidationMode> приведет к тому, что будет проверяться подлинность всех выданных маркеров, сертификаты которых принадлежат к хранилищу сертификатов `TrustedPeople`.В этом случае задайте для свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.TrustedStoreLocation%2A> значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> или <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.Можно выбрать и другие режимы, в том числе режим <xref:System.ServiceModel.Security.X509CertificateValidationMode>.Если выбран режим `Custom`, необходимо присвоить экземпляр класса <xref:System.IdentityModel.Selectors.X509CertificateValidator> свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CustomCertificateValidator%2A>.Пользовательский проверяющий элемент управления может проверять сертификаты, используя любые условия.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## См. также  
 [Федерация](../../../../docs/framework/wcf/feature-details/federation.md)   
 [Федерация и доверие](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)   
 [Образец федерации](../../../../docs/framework/wcf/samples/federation-sample.md)   
 [Как упорядочить отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)   
 [Практическое руководство. Создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)   
 [Как создавать федеративный клиент](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)