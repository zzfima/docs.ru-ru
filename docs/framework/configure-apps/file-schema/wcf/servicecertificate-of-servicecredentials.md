---
title: <serviceCertificate> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 513dcad7f4325d653df87fe9cc27572c25e153c5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399672"
---
# <a name="servicecertificate-of-servicecredentials"></a>\<serviceCertificate > \<ServiceCredentials >
Задает сертификат X.509, который будет использоваться для проверки подлинности службы при подключении к клиентам с использованием режима безопасности сообщений.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType. Значение по умолчанию — пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера. Допустимы следующие значения:<br /><br /> -LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509. Допустимы следующие значения:<br /><br /> AddressBook Хранилище сертификатов для других пользователей.<br />-Аусрут: Хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-Цертификатаусорити: Хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />Запрещено Хранилище сертификатов для отозванных сертификатов.<br />Мне Хранилище сертификатов для личных сертификатов.<br />Корневой Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).<br />TrustedPeople Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-Трустедпублишер: Хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - My.|  
|`x509FindType`|Определяет тип поиска сертификата X.509. Допустимы следующие значения:<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials >](servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент используется для задания сертификата X.509, который будет использоваться для проверки подлинности службы при подключении к клиентам с использованием режима безопасности сообщений. Если используется сертификат, который будет периодически обновляться, то его отпечаток изменится. В этом случае следует использовать имя субъекта в виде `x509FindType`, поскольку сертификат может быть выдан повторно с тем же именем субъекта.  
  
 Дополнительные сведения об использовании элемента см. в разделе [как Укажите значения](../../../wcf/how-to-specify-client-credential-values.md)учетных данных клиента.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [Практическое руководство. Укажите значения учетных данных клиента](../../../wcf/how-to-specify-client-credential-values.md)
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
