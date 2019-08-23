---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941931"
---
# <a name="certificatereference"></a>\<certificateReference >
Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.  
  
 \<> System. identityModel. Services  
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
|storeName|Имя хранилища сертификатов X. 509. Значение по умолчанию — "My". Необязательный параметр.|  
|storeLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Значение, указывающее расположение хранилища сертификатов X. 509. Значение по умолчанию — LocalMachine. Необязательный параметр.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение типа, указывающее тип выполняемого поиска. Значение по умолчанию — "Финдбисубжектдистингуишеднаме". Необязательный параметр.|  
|findValue|Значение для поиска в хранилище сертификатов X.509. Необязательный параметр.|  
|isChainIncluded|Указывает, следует ли выполнять проверку с помощью цепочки сертификатов. Значение по умолчанию — true; Проверка выполняется с помощью цепочки сертификатов. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCertificate >](servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки маркеров.|  
  
## <a name="remarks"></a>Примечания  
 `<certificateReference>` Элемент задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов. Если он указан как дочерний элемент `<serviceCertificate>` , он указывает параметры расположения и проверки сертификата X. 509, который используется для шифрования и расшифровки токенов. `<certificateReference>` Элемент представлен<xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.
