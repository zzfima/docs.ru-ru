---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: c7261d20ae2379ad33679cadecdef484f2afdecf
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075223"
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;system.identityModel.services&gt;
Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.  
  
 \<system.identityModel.services >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, определяющие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> модули HTTP (SAM).|  
  
### <a name="parent-elements"></a>Родительские элементы  
 Нет  
  
## <a name="remarks"></a>Примечания  
 Добавить `<system.identityModel.services>` раздел в файл конфигурации приложения для предоставления параметров для SAM и WSFAM.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса, чтобы обеспечить управление доступом на основе утверждений в коде, диспетчер авторизации требований (<xref:System.Security.Claims.ClaimsAuthorizationManager>) и политики, который используется для принятия решений об авторизации, настраиваются через `<identityConfiguration>` элемент, который явно или неявно ссылается `<federationConfiguration>` элемент в этом разделе. Дополнительные сведения см. в разделе **"Примечания"** под [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемент.  
  
 `<system.identityModel.services>` Представлен раздел <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> класса. Коллекция дочерних объектов `<federationConfiguration>` элементы, настроенные в разделе представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> класса.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как добавить `<system.identityModel.services>` раздел в файл конфигурации. Сначала необходимо добавить раздел объявлений для обоих `<system.identityModel.services>` раздел и `<system.identityModel>` разделы. (При добавлении `<system.identityModel.services>` раздел, также следует добавить объявление для `<system.identityModel>` раздел, чтобы убедиться, что по умолчанию `<identityConfiguration>` разделе могут создаваться средой выполнения, при необходимости.) После объявления раздела будут добавлены, можно настроить параметры федеративной проверки подлинности в разделе `<system.identityModel.services>` элемент.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
