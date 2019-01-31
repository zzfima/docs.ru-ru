---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: aab76949d9c31ac003b8afd519c2ad66529cbf26
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254870"
---
# <a name="nameclaimtype"></a>\<nameClaimType >
Задает тип утверждения, указывающее <xref:System.Security.Principal.IIdentity.Name%2A> свойство. Тип утверждения используется для поиска <xref:System.Security.Claims.Claim> в коллекцию <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращенных <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> метод данного обработчика токенов. Задайте значение соответствующее утверждение имени <xref:System.Security.Principal.IIdentity> созданные из этого обработчика токенов.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers >  
\<add>  
\<samlSecurityTokenRequirement>  
\<nameClaimType >  
  
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
|value|Строка, указывающая URI, представляющий тип требования утверждения для <xref:System.Security.Principal.IIdentity.Name%2A> свойство. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от любого из этих классов.|  
  
## <a name="remarks"></a>Примечания  
 `<nameClaimType>` Наборов элементов <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объект инициализирован из конфигурации.  
  
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
