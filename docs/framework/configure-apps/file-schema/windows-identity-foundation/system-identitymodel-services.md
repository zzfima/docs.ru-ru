---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152508"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Раздел конфигурации для проверки подлинности с использованием протокола WS-Federation.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
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
 None  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<федерацияКонфигурация>](federationconfiguration.md)|Содержит настройки, настраивающие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> модули (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP.|  
  
### <a name="parent-elements"></a>Родительские элементы  
 None  
  
## <a name="remarks"></a>Remarks  
 Добавьте `<system.identityModel.services>` раздел в файл конфигурации приложения, чтобы предоставить настройки для SAM и WSFAM.  
  
> [!IMPORTANT]
> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> или класса для обеспечения элемента доступа на основе<xref:System.Security.Claims.ClaimsAuthorizationManager>утверждений в коде менеджер авторизации претензий () и политика, используемая для принятия решений о авторизации, настраиваются через `<identityConfiguration>` элемент, на который косвенно или явно ссылается `<federationConfiguration>` элемент в этом разделе. Для получения дополнительной **информации** см [ \<>.](federationconfiguration.md)  
  
 Раздел `<system.identityModel.services>` представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> классом. Коллекция элементов `<federationConfiguration>` ребенка, настроенная в разделе, представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> классом.  
  
## <a name="example"></a>Пример  
 В следующем XML показано, `<system.identityModel.services>` как добавить раздел в файл конфигурации. Сначала необходимо добавить объявления раздела как для раздела, `<system.identityModel.services>` так и для разделов. `<system.identityModel>` (При добавлении раздела `<system.identityModel.services>` следует также добавить декларацию для `<system.identityModel>` раздела, чтобы при необходимости можно было создать раздел по умолчанию `<identityConfiguration>` к времени выполнения.) После добавления объявлений раздела можно настроить настройки федеративной аутентификации под элементом. `<system.identityModel.services>`  
  
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
