---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: ff38a6975d1ec73c1a3014b94198ba630c3fec31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149984"
---
# <a name="ltuserprincipalnamegt"></a>&lt;userPrincipalName&gt;
Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.  
  
 Дополнительные сведения о параметрах UPN см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
\<удостоверение >  
\<userPrincipalName >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|value|Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя. Это стандартный способ входа в домен Windows. Формат: someone@example.com (как для адреса электронной почты).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## <a name="remarks"></a>Примечания  
 Защищенный клиент Windows Communication Foundation (WCF), который подключается к конечной точке с использованием этого удостоверения использует имя участника-пользователя при проверке подлинности SSPI с конечной точкой.  
  
## <a name="example"></a>Пример  
 Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
