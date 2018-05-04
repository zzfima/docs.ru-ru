---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d725cc0d16457f2bdfb404baf4758e3431ce6b7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a>&lt;userNameSecurityTokenHandlerRequirement&gt;
Обеспечивает настройку для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<userNameSecurityTokenHandlerRequirement >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
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
|Используйте|Указывает <xref:System.Web.Security.MembershipProvider> , следует использовать обработчик маркеров безопасности.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.|  
  
## <a name="remarks"></a>Примечания  
 `<userNameSecurityTokenHandlerRequirement>` Наборы элементов <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> свойство при <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> инициализации объекта из конфигурации.  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
