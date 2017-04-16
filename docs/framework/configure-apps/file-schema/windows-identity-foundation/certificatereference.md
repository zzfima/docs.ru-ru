---
title: "&lt;certificateReference&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateReference&gt;
Задает параметры, используемые для поиска и проверки сертификата в хранилище сертификатов X.509.  
  
## Синтаксис  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName=”AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher”  
        storeLocation=”CurrentUser||LocalMachine”  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|storeName|Имя хранилища сертификатов X.509.  Значение по умолчанию — «My».  Необязательный.|  
|storeLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509.  Значение по умолчанию — «LocalMachine».  Необязательный.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, которое указывает тип поиска, который должен быть выполнен.  Значение по умолчанию — «FindBySubjectDistinguishedName».  Необязательный.|  
|findValue|Значение для поиска в хранилище сертификатов X.509.  Необязательный.|  
|isChainIncluded|Задает выполнение проверки при помощи цепочки сертификатов.  Значение по умолчанию — «истина»; Проверка выполняется с помощью цепочки сертификатов.  Необязательный.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Настройка сертификата, который используется для шифрования и расшифровки маркеры.|  
  
## Заметки  
 `<certificateReference>` Элемент задает параметры, используемые для поиска и проверки сертификата в хранилище сертификатов X.509.  Когда указан как дочерний элемент `<serviceCertficate>` элемент, определяет параметры расположения и проверки сертификата X.509, который используется для шифрования и расшифровки маркеры.  `<certificateReference>` Представленного элементом <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.