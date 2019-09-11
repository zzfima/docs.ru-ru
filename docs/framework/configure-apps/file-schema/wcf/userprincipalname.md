---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854822"
---
# <a name="userprincipalname"></a>\<userPrincipalName >
Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.  
  
Дополнительные сведения о настройке имени участника-пользователя см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> удостоверений**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName >**  
  
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
