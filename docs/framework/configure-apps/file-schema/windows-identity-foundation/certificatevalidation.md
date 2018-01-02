---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7a5d31bce5f71e644b40b3aa7e7c0c1c8790cab6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatevalidationgt"></a>&lt;certificateValidation&gt;
Управляет параметрами обработчиков токенов, используемых для проверки сертификатов. Эти параметры переопределяются, если обработчик конкретного настроен собственный проверяющий элемент управления.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<certificateValidation >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, указывающее режим проверки для сертификата X.509. Значение по умолчанию — «PeerOrChainTrust». Чтобы указать настраиваемый проверяющий элемент управления, присвоить этому атрибуту «Custom» и укажите с помощью проверяющего элемента управления [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) элемента. Необязательный.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, указывающее режим отзыва для сертификата X.509. Значение по умолчанию — «В сети». Необязательный.|  
|trustedStoreLocation|Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее хранилище сертификатов X.509. Значение по умолчанию — «LocalMachine». Необязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Задает пользовательский тип для проверки сертификата. Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы удостоверений.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Обеспечивает настройку для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 A `<certificateValidation>` элемент можно задать на уровне службы под `<identityConfiguration>` элемент, либо на уровне коллекции обработчик маркеров безопасности в разделе `<securityTokenHandlerConfiguration>` элемента. Параметры в коллекцию обработчика токенов переопределяют алгоритмам, заданным в службе. Некоторые обработчики маркеров позволяют задать параметры проверки сертификата в конфигурации. Параметры на отдельных обработчиков маркеров переопределить адреса, указанные как на уровне службы, так и в коллекцию обработчиков токенов безопасности.  
  
## <a name="example"></a>Пример  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
