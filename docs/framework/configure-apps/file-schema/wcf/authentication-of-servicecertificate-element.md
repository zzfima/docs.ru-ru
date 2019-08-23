---
title: <authentication> элемента <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: d770ba1f9a0a18c927b3a4bf6d4141286e3a380c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919980"
---
# <a name="authentication-of-servicecertificate-element"></a>\<> проверки подлинности элемента > \<serviceCertificate
Задает параметры, которые использует прокси клиента для проверки подлинности сертификатов службы, полученных при помощи согласования SSL/TLS.  
  
 \<системой. > ServiceModel  
\<> поведения  
раздел endpointBehaviors  
\<> поведения  
\<> clientCredentials  
\<serviceCertificate >  
\<> проверки подлинности  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|customCertificateValidatorType|Строка. Тип и сборка, используемые для проверки пользовательского типа.|  
|certificateValidationMode|Задает один из трех режимов для проверки учетных данных. Если задано значение `Custom`, также необходимо предоставить customCertificateValidator. Значение по умолчанию — `ChainTrust`.|  
|revocationMode|Один из режимов, используемых для проверки списков отозванных сертификатов (CRL). Значение по умолчанию — `Online`.|  
|trustedStoreLocation|Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`. Данное значение используется при согласовании сертификата службы для клиента. Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина. Значение по умолчанию — `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>Атрибут customCertificateValidator  
  
|Значение|Описание|  
|-----------|-----------------|  
|String|Задает имя типа и сборку, а также другие данные, используемые для поиска типа.|  
  
## <a name="certificatevalidationmode-attribute"></a>Атрибут certificateValidationMode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Одно из следующих значений: None, доверие одноранговой группы, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Атрибут revocationMode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Одно из следующих значений: Не проверять, в сети, вне сети.<br /><br /> Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Атрибут trustedStoreLocation  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Одно из следующих значений: LocalMachine или CurrentUser. Значение по умолчанию - CurrentUser. Если клиентское приложение выполняется в контексте системной учетной записи, сертификат обычно находится в LocalMachine. Если клиентское приложение выполняется в контексте учетной записи пользователя, то сертификат обычно находится в CurrentUser.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCertificate >](servicecertificate-of-clientcredentials-element.md)|Задает сертификат для использования при проверке подлинности службы для клиента.|  
  
## <a name="remarks"></a>Примечания  
 Атрибут `certificateValidationMode` данного элемента конфигурации указывает уровень доверия, который используется при проверке подлинности сертификатов. По умолчанию для уровня устанавливается значение `ChainTrust`, которое указывает, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации. Это наиболее безопасный режим. Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия. Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации. При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`. Также можно задать значение `Custom` или `None`. Чтобы использовать значение `Custom`, необходимо также установить атрибут `customCertificateValidator` для сборки и типа, которые используются при проверке сертификата. Для создания собственного пользовательского проверяющего элемента управления необходимо унаследовать его от абстрактного класса X509CertificateValidator. Дополнительные сведения см. в разделе [Практическое руководство. Создайте службу, которая использует пользовательский проверяющий элемент управления](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)для сертификатов.  
  
 Атрибут `revocationMode` указывает способ проверки отозванных сертификатов. По умолчанию используется значение `online`, которое указывает, что проверка, является ли сертификат отозванным, будет выполняться автоматически. Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется две задачи. Сначала он указывает сертификат службы, который будет использоваться клиентом при взаимодействии с конечными точками, доменное имя которых находится `www.contoso.com` по протоколу HTTP. Во-вторых, в этом примере указывается режим отзыва и место хранения, которые используются при проверке подлинности.  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Защита клиентов](../../../wcf/securing-clients.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
