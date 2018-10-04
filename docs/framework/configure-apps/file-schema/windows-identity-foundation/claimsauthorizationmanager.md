---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: a745339cffdada56a9b7f27f3f879b9d437c2da2
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793231"
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
Регистрирует диспетчера авторизации утверждений для входящих утверждений.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimsAuthorizationManager >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса. Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Если не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthorizationManager>` элемент выполняет только дочерние элементы; тем не менее, классы, производные от <xref:System.Security.Claims.ClaimsAuthorizationManager> можно определить дочерние элементы конфигурации.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы идентификации.|  
  
## <a name="remarks"></a>Примечания  
 Поведение по умолчанию, предоставляемых <xref:System.Security.Claims.ClaimsAuthorizationManager> класса всегда разрешает входящие утверждения. Если не `type` атрибут указан или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthorizationManager> класс, `<claimsAuthorizationManager>` элемент выполняет только дочерние элементы. Можно указать `type` атрибут для регистрации типа производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, чтобы реализовать пользовательское поведение. Производные классы могут поддерживает настройку с помощью дочерних элементов `<claimsAuthorizationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов. В схеме, определенной для дочерних элементов зависит от конструктора класса.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса, чтобы обеспечить управление доступом на основе утверждений в коде, конфигурация удостоверения, на который ссылается `<federationConfiguration>` элемент настраивает диспетчера авторизации утверждений и политику, которая используется для выполнения решения об авторизации. Это справедливо, даже в сценариях, которые не являются пассивных сценариях Web, например приложений Windows Communication Foundation (WCF) или приложение, которое не является веб. Если приложение не пассивное веб-приложение, `<claimsAuthorizationManager>` элемента (и политики его дочерние элементы, если он имеется) являются только параметры, применяемые на конфигурацию удостоверения, на которую указывает ссылка. Все остальные параметры игнорируются. Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемент.  
  
 Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойства.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает конфигурацию для авторизации утверждений диспетчер, который реализует политику, состоящий из пар ресурс действие, каждый из которых указывает логическое комбинации утверждения, запрашивающая сторона должна иметь для выполнения действия в ресурсе. Код, который реализует диспетчера авторизации утверждений, может использовать эту политику можно найти в `ClaimsBasedAuthorization` образца.  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
