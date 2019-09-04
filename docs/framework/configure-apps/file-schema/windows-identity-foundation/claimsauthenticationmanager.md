---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252095"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager >
Регистрирует диспетчер проверки подлинности утверждений для входящих утверждений.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthenticationManager >**  
  
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
|type|Указывает пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса. Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].|  
  
### <a name="child-elements"></a>Дочерние элементы  
 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> Если атрибут отсутствует или атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> ссылаетсянакласс,элементнепринимаетдочерниеэлементы,однакоклассы,производныеот,могутопределятьдочерниеэлементыконфигурации.`<claimsAuthenticationManager>` `type`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
  
## <a name="remarks"></a>Примечания  
 Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthenticationManager> классом, отображает входящие утверждения. Если атрибут не указан или `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> атрибут`<claimsAuthenticationManager>` указывает класс, элемент не принимает дочерние элементы. `type` Можно указать `type` атрибут для регистрации типа, производного <xref:System.Security.Claims.ClaimsAuthenticationManager> от класса, для реализации пользовательского поведения. Производные классы могут поддерживать конфигурацию через дочерние `<claimsAuthenticationManager>` элементы элемента путем <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> переопределения метода для работы с этими элементами. Схема, определенная для дочерних элементов, находится в конструкторе класса.  
  
 `<claimsAuthenticationManager>` Элемент<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> задает свойство.  
  
## <a name="example"></a>Пример  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
