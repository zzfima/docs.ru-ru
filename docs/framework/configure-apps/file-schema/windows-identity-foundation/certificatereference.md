---
title: '&lt;certificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756843"
---
# <a name="ltcertificatereferencegt"></a>&lt;certificateReference&gt;
Указывает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
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
|storeName|Имя хранилища сертификатов X.509. Значение по умолчанию — «My». Необязательный.|  
|storeLocation|Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509. Значение по умолчанию — «LocalMachine». Необязательный.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, указывающее тип выполняемого поиска, должно быть выполнено. Значение по умолчанию — «FindBySubjectDistinguishedName». Необязательный.|  
|findValue|Значение для поиска в хранилище сертификатов X.509. Необязательный.|  
|isChainIncluded|Указывает, следует ли выполнять проверки с с использованием цепочки сертификатов. Значение по умолчанию — «true»; Проверка выполняется с помощью цепочки сертификатов. Необязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки токенов.|  
  
## <a name="remarks"></a>Примечания  
 `<certificateReference>` Элемент задает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509. Когда он указан как дочерний элемент элемента `<serviceCertficate>` элемент задает параметры расположения и проверки сертификата X.509, используемый для шифрования и расшифровки токенов. `<certificateReference>` Представлен <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.
