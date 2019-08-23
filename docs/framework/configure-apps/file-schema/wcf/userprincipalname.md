---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940515"
---
# <a name="userprincipalname"></a>\<userPrincipalName >
Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.  
  
 Дополнительные сведения о настройке имени участника-пользователя см. в статье [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.  
  
\<> удостоверений  
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
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> удостоверений](identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## <a name="remarks"></a>Примечания  
 Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя участника-пользователя при выполнении проверки подлинности SSPI с конечной точкой.  
  
## <a name="example"></a>Пример  
 Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [Идентификация и проверка подлинности службы](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<> удостоверений](identity.md)
