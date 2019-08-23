---
title: <clientCertificate> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 3450df921da8c72a555c2faf424c51e0063cb235
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926123"
---
# <a name="clientcertificate-of-clientcredentials-element"></a>\<clientCertificate > \<>ного элемента ClientCredentials
Определяет сертификат X.509, используемый для проверки подлинности клиента по отношению к службе.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<endpointBehaviors >  
\<> поведения  
\<> clientCredentials  
\<clientCertificate >  
  
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
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в атрибуте, должен отвечать требованиям к значению атрибута `X509FindType`. Значение по умолчанию — пустая строка.|  
|`storeLocation`|Указывает расположение сертификата X.509, который клиент использует для подтверждения подлинности при взаимодействии со службой. Допустимы следующие значения:<br /><br /> -LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Задает имя хранилища сертификатов X.509 для поиска. Допустимы следующие значения:<br /><br /> AddressBook Хранилище сертификатов для других пользователей.<br />-Аусрут: Хранилище сертификатов для сторонних центров сертификации (ЦС).<br />CertificateAuthority Хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />Запрещено Хранилище сертификатов для отозванных сертификатов.<br />Мне Хранилище сертификатов для личных сертификатов.<br />Корневой Хранилище сертификатов для доверенных корневых центров сертификации (CAs).<br />TrustedPeople Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-Трустедпублишер: Хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - My. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Определяет тип поиска сертификата X.509. Тип, указанный в атрибуте `findValue`, должен отвечать требованиям этого атрибута. Допустимы следующие значения:<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> clientCredentials](clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации указывает сертификат, используемый для проверки подлинности клиента с помощью этого элемента. Дополнительные сведения см. в разделе [Практическое руководство. Укажите значения](../../../wcf/how-to-specify-client-credential-values.md)учетных данных клиента.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Укажите значения учетных данных клиента](../../../wcf/how-to-specify-client-credential-values.md)
- [Защита клиентов](../../../wcf/securing-clients.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
