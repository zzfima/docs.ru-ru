---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942622"
---
# <a name="nameclaimtype"></a>\<Намеклаимтипе >
Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство. Тип утверждения используется для поиска <xref:System.Security.Claims.Claim> в <xref:System.Security.Claims.ClaimsIdentity> коллекции объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом этого обработчика маркеров. Затем значение соответствующего утверждения задается в качестве имени объекта, <xref:System.Security.Principal.IIdentity> созданного из этого обработчика маркеров.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<samlSecurityTokenRequirement>  
\<Намеклаимтипе >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|value|Строка, указывающая URI, который представляет тип утверждения для утверждения, используемого для <xref:System.Security.Principal.IIdentity.Name%2A> свойства. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.|  
  
## <a name="remarks"></a>Примечания  
 Элемент задает свойство при<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> `<nameClaimType>`  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
