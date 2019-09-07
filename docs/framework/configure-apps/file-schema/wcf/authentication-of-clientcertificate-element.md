---
title: <authentication> элемента <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 99084f6b7afbdd8586ee706cd6ec44b349d81ff2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398270"
---
# <a name="authentication-of-clientcertificate-element"></a>\<> проверки подлинности элемента > \<clientcertificate
Указывает расширения функциональности аутентификации для сертификатов клиентов, используемых службой.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCertificate >** ](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> проверки подлинности**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|customCertificateValidatorType|Необязательная строка. Тип и сборка, используемые для проверки пользовательского типа. Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.|  
|certificateValidationMode|Необязательное перечисление. Задает один из режимов для проверки учетных данных. Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Если свойству присвоено значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, также необходимо указать свойство `customCertificateValidator`. Значение по умолчанию — <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.|  
|includeWindowsGroups|Необязательный логический атрибут. Указывает, включены ли группы Windows в контекст безопасности. Установка для этого атрибута значения `true` снижает производительность, поскольку приводит к расширению всей группы. Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.|  
|мапклиентцертификатетовиндовсаккаунт|Логическое. Указывает, может ли клиент сопоставляться с удостоверением Windows с помощью сертификата. Для этого необходимо включить службу Active Directory.|  
|revocationMode|Необязательное перечисление. Один из режимов, используемых для проверки списков отозванных сертификатов (RCL). Значение по умолчанию — `Online`. Это значение не учитывается при использовании безопасности транспорта HTTP.|  
|trustedStoreLocation|Необязательное перечисление. Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`. Данное значение используется при согласовании сертификата службы для клиента. Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина. Значение по умолчанию — `CurrentUser`.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>Атрибут customCertificateValidatorType  
  
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
|Перечисление|Одно из следующих значений: Не проверять, в сети, вне сети. Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Атрибут trustedStoreLocation  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Одно из следующих значений: `LocalMachine` или `CurrentUser`. Значение по умолчанию — `CurrentUser`. Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`. Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCertificate >](clientcertificate-of-servicecredentials.md)|Определяет сертификат X.509, используемый для проверки подлинности клиента по отношению к службе.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. Это дает возможность настраивать способ проверки подлинности клиентов. Для атрибута `certificateValidationMode` можно задать значение `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` или `Custom`. По умолчанию уровень имеет значение `ChainTrust`, которое указывает, что каждый сертификат должен быть найден в иерархии сертификатов, которые заканчиваются *корневым центром* в верхней части цепочки. Это наиболее безопасный режим. Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия. Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации. При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.  
  
 Также можно установить значение `Custom`. При установке значения `Custom` необходимо также задать атрибут `customCertificateValidatorType` для сборки и тип, который используется при проверке сертификата. Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Дополнительные сведения см. в разделе [Практическое руководство. Создайте службу, которая использует пользовательский проверяющий элемент управления](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)для сертификатов.  
  
## <a name="example"></a>Пример  
 В следующем примере кода задается сертификат X.509 и пользовательский тип проверки в элементе `<authentication>`.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
