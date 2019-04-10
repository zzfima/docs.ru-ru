---
title: Практическое руководство. Настройка учетных данных службы федерации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 149ab165-0ef3-490a-83a9-4322a07bd98a
ms.openlocfilehash: 33df685b4d14130ae00d59012706b7637924c9be
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295436"
---
# <a name="how-to-configure-credentials-on-a-federation-service"></a>Практическое руководство. Настройка учетных данных службы федерации
В Windows Communication Foundation (WCF), создания федеративной службы состоит из следующих основных процедур:  
  
1. Настройка <xref:System.ServiceModel.WSFederationHttpBinding> или аналогичной пользовательской привязки. Дополнительные сведения о создании соответствующей привязки см. в разделе [как: Создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).  
  
2. Настройка объекта <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>, который определяет порядок проверки подлинности выданных маркеров, которые предоставляются службе.  
  
 В этом разделе описывается второй этап. Дополнительные сведения о работе федеративной службы см. в разделе [федерации](../../../../docs/framework/wcf/feature-details/federation.md).  
  
### <a name="to-set-the-properties-of-issuedtokenservicecredential-in-code"></a>Задание свойств объекта IssuedTokenServiceCredential в коде  
  
1. Свойство <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A> класса <xref:System.ServiceModel.Description.ServiceCredentials> служит для возврата ссылки на экземпляр <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>. Доступ к этому свойству осуществляется через свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> класса <xref:System.ServiceModel.ServiceHostBase>.  
  
2. Задайте для свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> значение `true`, если требуется проверять подлинность самостоятельно выданных маркеров, например карт [!INCLUDE[infocard](../../../../includes/infocard-md.md)]. Значение по умолчанию — `false`.  
  
3. Заполните коллекцию, возвращаемую свойством <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>, экземплярами класса <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>. Каждый экземпляр представляет издателя, для которого служба будет проверять подлинность маркеров.  
  
    > [!NOTE]
    >  В отличие от клиентской коллекции, возвращаемой свойством <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>, коллекция известных сертификатов не является коллекцией с ключом. Служба принимает маркеры, выдаваемые заданным сертификатом, независимо от адреса клиента, который отправил сообщение с выданным маркером (на него накладываются дополнительные ограничения, описанные ниже в этом разделе).  
  
4. Присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> одно из значений перечисления <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Это можно сделать только в коде. Значение по умолчанию — <xref:System.IdentityModel.Selectors.X509CertificateValidator.ChainTrust%2A>.  
  
5. Если свойство <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> имеет значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>, присвойте экземпляр пользовательского класса <xref:System.IdentityModel.Selectors.X509CertificateValidator> свойству <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.  
  
6. Если свойство <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> имеет значение `ChainTrust` или `PeerOrChainTrust`, присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.RevocationMode%2A> соответствующее значение из перечисления <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Обратите внимание, что в режимах проверки `PeerTrust` и `Custom`, режим отзыва не используется.  
  
7. Если необходимо, присвойте экземпляр пользовательского класса <xref:System.IdentityModel.Tokens.SamlSerializer> свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.SamlSerializer%2A>. Пользовательский сериализатор языка Security Assertions Markup Language (SAML) требуется, например, для анализа пользовательских утверждений SAML.  
  
### <a name="to-set-the-properties-of-issuedtokenservicecredential-in-configuration"></a>Задание свойств объекта IssuedTokenServiceCredential в файле конфигурации  
  
1. Создание `<issuedTokenAuthentication>` как дочерний элемент элемента <`serviceCredentials`> элемента.  
  
2. Задайте для атрибута `allowUntrustedRsaIssuers` элемента `<issuedTokenAuthentication>` значение `true`, если проверяется подлинность выданного самостоятельно маркера, например карты [!INCLUDE[infocard](../../../../includes/infocard-md.md)].  
  
3. Создайте элемент `<knownCertificates>`, являющийся дочерним для элемента `<issuedTokenAuthentication>`.  
  
4. Создайте ноль или несколько элементов `<add>`, являющих дочерними для элемента `<knownCertificates>`, и с помощью атрибутов `storeLocation`, `storeName`, `x509FindType` и `findValue` укажите, каким образом обнаружить сертификат.  
  
5. При необходимости задайте `samlSerializer` атрибут <`issuedTokenAuthentication`> элемент как имя типа пользовательского <xref:System.IdentityModel.Tokens.SamlSerializer> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере свойства объекта <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> задаются в коде.  
  
 [!code-csharp[C_FederatedService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedservice/cs/source.cs#2)]
 [!code-vb[C_FederatedService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedservice/vb/source.vb#2)]  
  
 Чтобы федеративная служба проверяла подлинность клиента, для выданного маркера должны выполняться следующие условия:  
  
-   если в цифровой сигнатуре выданного маркера используется идентификатор ключа безопасности RSA, свойство <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> должно иметь значение `true`;  
  
-   если в подписи выданного маркера используется серийный номер издателя X.509, идентификатор ключа субъекта X.509 или идентификатор безопасности отпечатка X.509, выданный маркер должен быть подписан сертификатом из коллекции, возвращаемой свойством <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> класса <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>;  
  
-   если выданный маркер подписан с помощью сертификата X.509, этот сертификат должен осуществлять проверку на основании семантики, определенной значением свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>, независимо от того, был ли сертификат отправлен проверяющей стороне в качестве объекта <xref:System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause> или же получен из свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>. Дополнительные сведения о проверки сертификата X.509, см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 Например, установка свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> равным <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerTrust> приведет к тому, что будет проверяться подлинность всех выданных маркеров, сертификаты которых принадлежат к хранилищу сертификатов `TrustedPeople`. В этом случае задайте для свойства <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.TrustedStoreLocation%2A> значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser> или <xref:System.Security.Cryptography.X509Certificates.StoreLocation.LocalMachine>. Можно выбрать и другие режимы, в том числе режим <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>. Если выбран режим `Custom`, необходимо присвоить экземпляр класса <xref:System.IdentityModel.Selectors.X509CertificateValidator> свойству <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CustomCertificateValidator%2A>. Пользовательский проверяющий элемент управления может проверять сертификаты, используя любые условия. Дополнительные сведения см. в разделе [Как Создание службы, использующей пользовательское средство проверки сертификатов](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## <a name="see-also"></a>См. также

- [Федерация](../../../../docs/framework/wcf/feature-details/federation.md)
- [Федерация и доверие](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)
- [Пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md)
- [Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Практическое руководство. Создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Практическое руководство. Создание федеративного клиента](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)
