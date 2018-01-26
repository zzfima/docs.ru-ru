---
title: '&lt;claimsAuthorizationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: eb0475796a488489f4a32c820d1a92994237d7fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
|type|Пользовательский тип, который является производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса. Дополнительные сведения о способах указания `type` см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 При наличии не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класса `<claimsAuthorizationManager>` элемент не принимает дочерних элементов; Однако классы, производные от <xref:System.Security.Claims.ClaimsAuthorizationManager> можно определить дочерние элементы конфигурации.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы удостоверений.|  
  
## <a name="remarks"></a>Примечания  
 Поведение по умолчанию, предоставленные с помощью <xref:System.Security.Claims.ClaimsAuthorizationManager> класса всегда разрешает входящие утверждения. Если не `type` указан атрибут или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, `<claimsAuthorizationManager>` элемент не принимает дочерних элементов. Можно указать `type` атрибут, чтобы зарегистрировать тип производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, чтобы реализовать пользовательское поведение. Производные классы могут поддерживать конфигурацию с помощью дочерних элементов `<claimsAuthorizationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов. Схемы, определенных для дочерних элементов зависит от конструктора класса.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде, на который ссылается конфигурация удостоверений `<federationConfiguration>` элемент настраивает диспетчера авторизации утверждений и политики, которая используется, чтобы сделать решения об авторизации. Это верно даже в случаях, не пассивный сценариях веб-, например приложений Windows Communication Foundation (WCF) или приложение, которое не является веб сервера. Если приложение не пассивное веб-приложение `<claimsAuthorizationManager>` элемент (и политики его дочерние элементы, если он имеется) указанное удостоверение конфигурации являются только параметры, применяемые. Все остальные параметры игнорируются. Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.  
  
 Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойства.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает конфигурацию для авторизации утверждений диспетчер, который реализует политики состоит из пары действие ресурса, каждый из которых определяет логическое сочетания утверждения, запрашивающая сторона должна иметь для выполнения действия с ресурсом. Код, который реализует диспетчера авторизации утверждений, может использовать эту политику можно найти в `ClaimsBasedAuthorization` образца.  
  
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
