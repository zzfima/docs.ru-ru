---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251810"
---
# <a name="systemidentitymodelservices"></a>\<> System. identityModel. Services
Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp; **\<> System. identityModel. Services**  
  
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
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) <xref:System.IdentityModel.Services.SessionAuthenticationModule> и HTTP-модули (SAM).|  
  
### <a name="parent-elements"></a>Родительские элементы  
 Отсутствуют  
  
## <a name="remarks"></a>Примечания  
 `<system.identityModel.services>` Добавьте раздел в файл конфигурации приложения, чтобы указать параметры для SAM и всфам.  
  
> [!IMPORTANT]
> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде Диспетчер авторизации утверждений (<xref:System.Security.Claims.ClaimsAuthorizationManager>) и политика, используемые `<identityConfiguration>` для принятия решений об авторизации, настраиваются с помощью элемент, который неявно или явно указан из `<federationConfiguration>` элемента в этом разделе. Дополнительные сведения см. в разделе **"Примечания** " в [ \<элементе > federationConfiguration](federationconfiguration.md) .  
  
 `<system.identityModel.services>` Раздел представлен<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> классом. Коллекция дочерних `<federationConfiguration>` элементов, настроенных в разделе, представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> классом.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как добавить `<system.identityModel.services>` раздел в файл конфигурации. Сначала необходимо добавить объявления разделов как для `<system.identityModel.services>` раздела `<system.identityModel>` , так и для разделов. (При добавлении `<system.identityModel.services>` раздела необходимо также добавить объявление `<system.identityModel>` для раздела, чтобы гарантировать, что при необходимости раздел по умолчанию `<identityConfiguration>` может быть создан средой выполнения.) После добавления объявлений разделов можно настроить параметры федеративной проверки подлинности в `<system.identityModel.services>` элементе.  
  
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
