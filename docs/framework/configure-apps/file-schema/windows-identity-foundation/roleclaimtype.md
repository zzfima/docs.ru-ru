---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942543"
---
# <a name="roleclaimtype"></a>\<Ролеклаимтипе >
Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<samlSecurityTokenRequirement>  
\<Ролеклаимтипе >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
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
|value|Строка, указывающая URI, который представляет тип утверждения, используемого для типа утверждения роли.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.|  
  
## <a name="remarks"></a>Примечания  
 Элемент задает свойство при<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> `<roleClaimType>`  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
