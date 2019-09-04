---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ddbe8a862940272e4192a3f4c0abdc1f9e8b5d48
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252083"
---
# <a name="claimsauthorizationmanager"></a>\<claimsAuthorizationManager >
Регистрирует диспетчер авторизации утверждений для входящих утверждений.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthorizationManager >**  
  
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
|type|Пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса. Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> Если атрибут отсутствует или атрибут <xref:System.Security.Claims.ClaimsAuthorizationManager> ссылаетсянакласс,элементнепринимаетдочерниеэлементы,однакоклассы,производныеот,могутопределятьдочерниеэлементыконфигурации.`<claimsAuthorizationManager>` `type`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
  
## <a name="remarks"></a>Примечания  
 Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthorizationManager> классом, всегда разрешает входящие утверждения. Если атрибут не указан или `type` <xref:System.Security.Claims.ClaimsAuthorizationManager> атрибут`<claimsAuthorizationManager>` указывает класс, элемент не принимает дочерние элементы. `type` Можно указать `type` атрибут для регистрации типа, производного <xref:System.Security.Claims.ClaimsAuthorizationManager> от класса, для реализации пользовательского поведения. Производные классы могут поддерживать конфигурацию через дочерние `<claimsAuthorizationManager>` элементы элемента путем <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> переопределения метода для работы с этими элементами. Схема, определенная для дочерних элементов, находится в конструкторе класса.  
  
> [!IMPORTANT]
> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде конфигурация удостоверений `<federationConfiguration>` , на которую ссылается элемент, настраивает диспетчер авторизации утверждений и политику, которая используется для создания решения по авторизации. Это справедливо даже в сценариях, которые не являются пассивными веб-сценариями, например Windows Communication Foundation приложений (WCF) или приложение, не основанное на веб-интерфейсе. Если приложение не является пассивным веб-приложением, то `<claimsAuthorizationManager>` к нему применяются только те элементы (и дочерние элемент политики, если таковые имеются) конфигурации удостоверения, на которую указывает ссылка. Все остальные параметры игнорируются. Дополнительные сведения см. в [ \<](federationconfiguration.md) описании элемента federationConfiguration >.  
  
 Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показана конфигурация для диспетчера авторизации утверждений, который реализует политику, состоящую из пар действий с ресурсами, каждый из которых указывает логические комбинации утверждений, которые должен обладать запрашивающей стороны для выполнения действия с ресурсом. Код, реализующий диспетчер авторизации утверждений, который может использовать эту политику, можно найти в `ClaimsBasedAuthorization` примере.  
  
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
