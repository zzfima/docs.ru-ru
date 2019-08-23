---
title: Элемент <defaultCertificate>
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 93410e815a156f91db1962f05fb1aa6baca7f955
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919250"
---
# <a name="defaultcertificate-element"></a>\<Элемент > Дефаултцертификате
Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.  
  
 \<системой. > ServiceModel  
\<> поведения  
раздел endpointBehaviors  
\<> поведения  
\<> clientCredentials  
\<serviceCertificate >  
\<Дефаултцертификате >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|findValue|Строка. Значение, которое нужно найти.|  
|x509FindType|Перечисление. Одно из полей сертификата, где следует проводить поиск.|  
|storeLocation|Перечисление. Одно из двух системных расположений хранилища, где следует проводить поиск.|  
|storeName|Перечисление. Одно из системных хранилищ, где следует проводить поиск.|  
  
## <a name="findvalue-attribute"></a>Атрибут findValue  
  
|Значение|Описание|  
|-----------|-----------------|  
|String|Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется. Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.|  
  
## <a name="x509findtype-attribute"></a>Атрибут x509FindType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Атрибут storeLocation  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|CurrentUser или LocalMachine.|  
  
## <a name="storename-attribute"></a>Атрибут storeName  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCertificate >](servicecertificate-of-clientcredentials-element.md)|Задает сертификат для использования при проверке подлинности службы для клиента.|  
  
## <a name="remarks"></a>Примечания  
 Для привязок, использующих безопасность сообщений на основе сертификатов, сертификат, заданный этим элементом конфигурации, используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту. Он сохраняет один сертификат для использования при отсутствии сертификата, заданного службой сертификата.  
  
## <a name="example"></a>Пример  
 В следующем примере указывается сертификат, который будет использоваться для конечных точек, `http://www.contoso.com` URI которых начинается с, и сертификат, который будет использоваться для всех остальных конечных точек, не выполняющих согласование сертификатов.  
  
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

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Защита клиентов](../../../wcf/securing-clients.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
