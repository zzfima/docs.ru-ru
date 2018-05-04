---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicecertificategt"></a>&lt;serviceCertificate&gt;
Настраивает сертификат X.509, используемый для шифрования и расшифровки токенов.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<serviceCertificate >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<certificateReference >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|Указывает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="example"></a>Пример  
 Следующий XML-КОДЕ показано использование \<serviceCertificate > элемента. XML-код будет браться из `CustomToken` образца.  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
