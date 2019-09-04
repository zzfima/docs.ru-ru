---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252136"
---
# <a name="certificatevalidation"></a>\<Цертификатевалидатион >
Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов. Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Цертификатевалидатион >**  
  
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|certificateValidationMode|Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509. Значение по умолчанию — "PeerOrChainTrust". Чтобы указать настраиваемый проверяющий элемент управления, установите для этого атрибута значение "Custom" и укажите проверяющий элемент управления с помощью [ \<элемента цертификатевалидатор >](certificatevalidator.md) . Необязательный параметр.|  
|revocationMode|Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509. Значение по умолчанию — "Online". Необязательный параметр.|  
|trustedStoreLocation|Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509. Значение по умолчанию — LocalMachine. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Цертификатевалидатор >](certificatevalidator.md)|Указывает пользовательский тип для проверки сертификата. Этот тип используется только в том случае `certificateValidationMode` , если атрибуту [ \<элемента цертификатевалидатион >](certificatevalidation.md) присвоено значение Custom.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<certificateValidation>` Параметры коллекции обработчиков маркеров переопределяют указанные в службе. Некоторые обработчики маркеров позволяют указать параметры проверки сертификата в конфигурации. Параметры отдельных обработчиков маркеров переопределяют те, которые указаны как на уровне службы, так и в коллекции обработчиков маркеров безопасности.  
  
## <a name="example"></a>Пример  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
