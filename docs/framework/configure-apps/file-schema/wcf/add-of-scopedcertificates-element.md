---
title: <add> элемента <scopedCertificates>
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 34dc51c27a5e16b1a8411112fb9afdfe617ed582
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262326"
---
# <a name="add-of-scopedcertificates-element"></a>\<Добавить > из \<scopedCertificates > элемент
Добавляет сертификат X.509 в коллекцию сертификатов в области действия.  
  
 \<system.ServiceModel>  
\<варианты поведения >  
раздел endpointBehaviors  
\<поведение >  
\<clientCredentials>  
\<serviceCertificate >  
\<scopedCertificates >  
\<Добавить > элемент для \<scopedCertificates >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|targetUri|Строка. Задает универсальный код ресурса (URI) службы, связанной с сертификатом.|  
|findValue|Строка. Значение, которое нужно найти.|  
|x509FindType|Перечисление. Одно из полей сертификата, где следует проводить поиск.|  
|storeLocation|Перечисление. Одно из двух местоположений хранилища, где следует проводить поиск.|  
|storeName|Перечисление. Одно из системных хранилищ, где следует проводить поиск.|  
  
## <a name="findvalue-attribute"></a>Атрибут findValue  
  
|Значение|Описание|  
|-----------|-----------------|  
|Строковое|Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется. Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.|  
  
## <a name="x509findtype-attribute"></a>Атрибут x509FindType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|К этим значениям относятся следующие. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Атрибут storeLocation  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|CurrentUser или LocalMachine.|  
  
## <a name="storename-attribute"></a>Атрибут storeName  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|К этим значениям относятся следующие. AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<scopedCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент позволяет клиенту настроить сертификат службы для использования на основе URL-адреса службы, с которой он связывается. Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами (с конечной службой, а также с промежуточными службами маркеров безопасности). Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.  
  
 Если для привязки необходим сертификат для службы, а конкретный сертификат для URL-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.  
  
 Дополнительные сведения см. в разделе «Сертификаты в области действия» [как: Создание федеративного клиента](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
## <a name="example"></a>Пример  
 В следующем примере к коллекции добавляется сертификат X.509.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [Практическое руководство. Создание федеративного клиента](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
