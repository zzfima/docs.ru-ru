---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> модули HTTP (SAM).|  
  
### <a name="parent-elements"></a>Родительские элементы  
 Нет  
  
## <a name="remarks"></a>Примечания  
 Добавить `<system.identityModel.services>` раздел в файле конфигурации приложения для предоставления параметров для диспетчера учетных записей безопасности и WSFAM.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде диспетчера авторизации утверждений (<xref:System.Security.Claims.ClaimsAuthorizationManager>) и политики, которая используется для принятия решения об авторизации, настраиваются через `<identityConfiguration>` элемент, который явно или неявно ссылается `<federationConfiguration>` элемент в этом разделе. Дополнительные сведения см. в разделе **примечания** под [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.  
  
 `<system.identityModel.services>` Разделе представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> класса. Коллекция дочерних `<federationConfiguration>` элементы, настроенные в разделе представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> класса.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает, как добавить `<system.identityModel.services>` раздел в файле конфигурации. Сначала необходимо добавить раздел объявлений для обоих `<system.identityModel.services>` раздел и `<system.identityModel>` разделы. (При добавлении `<system.identityModel.services>` раздела, следует также добавить объявление для `<system.identityModel>` раздел, чтобы убедиться, что значение по умолчанию `<identityConfiguration>` раздел, создаваемых средой выполнения при необходимости.) После добавления объявления разделов, можно настроить параметры федеративной проверки подлинности в разделе `<system.identityModel.services>` элемента.  
  
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
