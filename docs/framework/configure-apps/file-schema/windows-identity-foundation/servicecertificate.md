---
title: "&lt;serviceCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;serviceCertificate&gt;
Настройка сертификата X.509, который используется для шифрования и расшифровки маркеры.  
  
## Синтаксис  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
 None  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<certificateReference\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|Задает параметры, используемые для поиска и проверки сертификата в хранилище сертификатов X.509.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Пример  
 Следующий код XML показывает использование \<serviceCertificate\> элемент.  XML берется из `CustomToken` образца.  
  
```  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```