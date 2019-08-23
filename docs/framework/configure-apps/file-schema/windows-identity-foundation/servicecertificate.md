---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942414"
---
# <a name="servicecertificate"></a>\<serviceCertificate >
Настраивает сертификат X. 509, используемый для шифрования и расшифровки токенов.  
  
 \<> System. identityModel. Services  
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
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<certificateReference >](certificatereference.md)|Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> свойства (всфам) <xref:System.IdentityModel.Services.SessionAuthenticationModule> и (SAM).|  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано использование \<элемента > serviceCertificate. XML взят из `CustomToken` примера.  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
