---
title: "&lt;system.identityModel.services&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;system.identityModel.services&gt;
Раздел конфигурации для проверки подлинности с помощью протокола WS\-Federation.  
  
 \<system.identityModel.services\>  
  
## Синтаксис  
  
```  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
 None  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> модули HTTP \(SAM\).|  
  
### Родительские элементы  
 None  
  
## Заметки  
 Добавить `<system.identityModel.services>` раздел в файле конфигурации приложения для предоставления параметров SAM и WSFAM.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе заявок в коде, диспетчер авторизации заявок \(<xref:System.Security.Claims.ClaimsAuthorizationManager>\) и политики, который используется для принятия решения об авторизации, настраиваются через `<identityConfiguration>` элемент, который явно или неявно ссылается `<federationConfiguration>` элемент в данном разделе.  Для получения дополнительных сведений см.  **примечания** в [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемент.  
  
 `<system.identityModel.services>` Разделе представлена <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> класса.  Коллекция дочерних `<federationConfiguration>` элементов, настроенных в разделе представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> класса.  
  
## Пример  
 Следующий код XML показывает, как добавить `<system.identityModel.services>` раздел в файле конфигурации.  Сначала необходимо добавить раздел объявлений для обоих `<system.identityModel.services>` раздел и `<system.identityModel>` разделы.  \(При добавлении `<system.identityModel.services>` разделе, следует также добавить объявление для `<system.identityModel>` раздел, чтобы убедиться, что по умолчанию `<identityConfiguration>` раздел может быть создана путем выполнения, при необходимости.\) После добавления объявления разделов можно настроить параметры интегрированную проверку подлинности в разделе `<system.identityModel.services>` элемент.  
  
```  
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