---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
Регистрирует диспетчер проверки подлинности утверждений входящие утверждения.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimsAuthenticationManager >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Задает пользовательский тип, который является производным от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса. Дополнительные сведения о способах указания `type` см. в разделе [пользовательский тип ссылки].|  
  
### <a name="child-elements"></a>Дочерние элементы  
 При наличии не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класса `<claimsAuthenticationManager>` элемент не принимает дочерних элементов; Однако классы, производные от <xref:System.Security.Claims.ClaimsAuthenticationManager> можно определить дочерние элементы конфигурации.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы удостоверений.|  
  
## <a name="remarks"></a>Примечания  
 Поведение по умолчанию, предоставленные с помощью <xref:System.Security.Claims.ClaimsAuthenticationManager> класс выводит входящих утверждений. Если не `type` указан атрибут или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, `<claimsAuthenticationManager>` элемент не принимает дочерних элементов. Можно указать `type` атрибут, чтобы зарегистрировать тип производным от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, чтобы реализовать пользовательское поведение. Производные классы могут поддерживать конфигурацию с помощью дочерних элементов `<claimsAuthenticationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов. Схемы, определенных для дочерних элементов зависит от конструктора класса.  
  
 `<claimsAuthenticationManager>` Наборы элементов <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
