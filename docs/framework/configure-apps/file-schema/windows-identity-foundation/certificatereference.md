---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152818"
---
# <a name="certificatereference"></a>\<сертификатСправка>
Определяет настройки, которые используются для поиска и проверки сертификата X.509 в магазине сертификатов.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<федерацияКонфигурация>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>сервис-сертификат**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сертификатСправка>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|storeName|Имя хранилища сертификатов X.509. По умолчанию "Мой". Необязательный параметр.|  
|storeLocation|Значение, <xref:System.Security.Cryptography.X509Certificates.StoreLocation> опоглавивававаев оместонахождение магазина сертификатов X.509. Значение по умолчанию — «LocalMachine». Необязательный параметр.|  
|x509FindType|Значение, <xref:System.Security.Cryptography.X509Certificates.X509FindType> описавававававаемый тип поиска, который должен быть выполнен. По умолчанию является "FindBySubjectDistinguishedName". Необязательный параметр.|  
|findValue|Значение для поиска в хранилище сертификатов X.509. Необязательный параметр.|  
|isChainIncluded|Уточняется, следует ли проводить проверку с помощью цепочки сертификатов. По умолчанию является "истинным"; проверка осуществляется с помощью цепочки сертификатов. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<>сервис-сертификат](servicecertificate.md)|Настраивает сертификат, который используется для шифрования и расшифровки токенов.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `<certificateReference>` определяет параметры, которые используются для поиска и проверки сертификата X.509 в магазине сертификатов. Когда он указан в качестве `<serviceCertificate>` элемента элемента ребенка, он определяет настройки местоположения и проверки сертификата X.509, который используется для шифрования и расшифровки токенов. Элемент `<certificateReference>` представлен <xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.
