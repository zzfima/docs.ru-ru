---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423031"
---
# <a name="certificatereference"></a>\<certificateReference >
Задает параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<serviceCertificate >  
\<certificateReference >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|storeName|Имя хранилища сертификатов X.509. Значение по умолчанию — «My». Необязательный параметр.|  
|storeLocation|Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509. Значение по умолчанию — «LocalMachine». Необязательный параметр.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, указывающее тип выполняемого поиска, который должен выполняться. Значение по умолчанию — «FindBySubjectDistinguishedName». Необязательный параметр.|  
|findValue|Значение для поиска в хранилище сертификатов X.509. Необязательный параметр.|  
|isChainIncluded|Указывает, нужно ли выполнять проверку с помощью цепочки сертификатов. Значение по умолчанию равно «true»; Проверка выполняется с помощью цепочки сертификатов. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки маркеров.|  
  
## <a name="remarks"></a>Примечания  
 `<certificateReference>` Элемент определяет параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов. Когда он указан как дочерний элемент `<serviceCertificate>` , он указывает расположение и проверки параметров сертификата X.509, который используется для шифрования и расшифровки маркеров. `<certificateReference>` Элемент, представленный объектом <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.
