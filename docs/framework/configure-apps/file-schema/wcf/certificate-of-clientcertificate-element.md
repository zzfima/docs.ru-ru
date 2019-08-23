---
title: <certificate> элемента <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 1af56280397e7d8924656f2f7cda5af4e30e91e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926188"
---
# <a name="certificate-of-clientcertificate-element"></a>\<> сертификата для \<элемента > clientcertificate
Указывает сертификат X.509, используемый для подписания и шифрования сообщений.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<serviceCredentials >  
\<clientCertificate >  
\<> сертификата  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType. Значение по умолчанию — пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера. Допустимы следующие значения:<br /><br /> -LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509. Допустимы следующие значения:<br /><br /> AddressBook Хранилище сертификатов для других пользователей.<br />-Аусрут: Хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-Цертификатионаусорити: Хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />Запрещено Хранилище сертификатов для отозванных сертификатов.<br />Мне Хранилище сертификатов для личных сертификатов.<br />Корневой Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).<br />TrustedPeople Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-Трустедпублишер: Хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - My.|  
|`X509FindType`|Определяет тип поиска сертификата X.509. Допустимы следующие значения:<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCertificate >](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a>Примечания  
 Элемент `<certificate>` используется в случаях, когда служба должна заранее получить клиентский сертификат для безопасного обмена данными с клиентом. Это характерно для дуплексного обмена данными. В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика. Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту. Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента. Дополнительные сведения о дуплексных службах см [. в разделе как Создание дуплексного контракта](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется поиск соответствующего сертификата X.509 и пользовательского типа проверки в элементе `<authentication>`.  
  
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

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
