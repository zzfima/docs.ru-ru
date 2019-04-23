---
title: <clientCertificate> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 5abf0a99beff1b9fb3655cb82d74484f3b88237f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216461"
---
# <a name="clientcertificate-of-clientcredentials-element"></a>\<clientCertificate > элемента \<clientCredentials > элемент
Определяет сертификат X.509, используемый для проверки подлинности клиента по отношению к службе.  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<endpointBehaviors>  
\<поведение >  
\<clientCredentials>  
\<clientCertificate>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в атрибуте, должен отвечать требованиям к значению атрибута `X509FindType`. Значение по умолчанию - пустая строка.|  
|`storeLocation`|Указывает расположение сертификата X.509, который клиент использует для подтверждения подлинности при взаимодействии со службой. Допустимы следующие значения:<br /><br /> -LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Задает имя хранилища сертификатов X.509 для поиска. Допустимы следующие значения:<br /><br /> -AddressBook: Хранилище сертификатов для других пользователей.<br />-AuthRoot: Хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-CertificateAuthority: Хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />-Запрещается использовать следующее: Хранилище сертификатов для отозванных сертификатов.<br />— My: Хранилище сертификатов для личных сертификатов.<br />-Root: Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).<br />-TrustedPeople: Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-TrustedPublisher: Хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - My. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Определяет тип поиска сертификата X.509. Тип, указанный в атрибуте `findValue`, должен отвечать требованиям этого атрибута. Допустимы следующие значения:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации указывает сертификат, используемый для проверки подлинности клиента с помощью этого элемента. Дополнительные сведения см. в разделе [Как Укажите значения учетных данных клиента](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Укажите значения учетных данных клиента](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)
- [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)
- [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
