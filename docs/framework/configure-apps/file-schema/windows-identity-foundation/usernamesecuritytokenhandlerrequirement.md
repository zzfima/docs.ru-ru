---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944257"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a>\<Усернамесекурититокенхандлеррекуиремент >
Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<Усернамесекурититокенхандлеррекуиремент >  
  
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
|мембершиппровидернаме|<xref:System.Web.Security.MembershipProvider> Указывает, который должен использоваться обработчиком маркеров безопасности.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 Элемент задает свойство при<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> инициализации объекта из конфигурации. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> `<userNameSecurityTokenHandlerRequirement>`  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
