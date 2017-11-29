---
title: '&lt;federationConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9abe07c065dbea67c5ebc4a4490d9f88258130c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
Настраивает <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM), при использовании федеративной проверки подлинности по протоколу WS-Federation. Настраивает <xref:System.Security.Claims.ClaimsAuthorizationManager> при использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
  
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Имя данного элемента конфигурации федерации. В основном этот атрибут предоставляет точку расширения для будущих протоколов. Необязательно.|  
|identityConfigurationName|Имя раздела конфигурации удостоверения, как указано в [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента, который требуется использовать. Если этот атрибут не указан, используется раздел конфигурации по умолчанию удостоверение. Необязательно.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает обработчик куки-файл, используемый SAM. Необязательно.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки токенов. Необязательно.|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Настраивает модуль проверки подлинности WS-Federation (WSFAM). Необязательно.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.|  
  
## <a name="remarks"></a>Примечания  
 \<FederationConfiguration > элемент предоставляет параметры в двух разных сценариев:  
  
-   При использовании WS-Federation passive веб-приложения, элемент содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Он также ссылается на конфигурацию удостоверения используемый для настройки обработчики маркеров безопасности и сертификаты и компоненты, например диспетчера авторизации утверждений и диспетчером проверки подлинности утверждений.  
  
-   При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде, элемент ссылается на конфигурацию удостоверения, который настраивает диспетчера авторизации утверждений и политики, которая используется для выполнения авторизации решения. Это верно даже в случаях, которые не являются пассивный веб-сценариев; Например, приложения Windows Communication Foundation (WCF) или приложение, которое не является веб сервера. Если приложение не пассивное веб-приложение [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) элемент (и политики его дочерние элементы, если он имеется) идентификаторов конфигурации, ссылается `<federationConfiguration>` элемент применяются только параметры. Другие атрибуты игнорируются.  
  
 Независимо от того, сценарий среда выполнения загружает конфигурацию федерации по умолчанию. Поведение определяется следующим образом:  
  
1.  При наличии не `<federationConfiguration>` элемент отсутствует, среда выполнения создает конфигурацию федерации и заполняет значениями по умолчанию. Эта конфигурация по умолчанию федерации будет ссылаться на конфигурацию удостоверения по умолчанию.  
  
2.  Если один `<federationConfiguration>` элемент присутствует, он федерации конфигурации по умолчанию, будь то с именем или без имени. Если его `identityConfiguration` атрибут указан, указывается конфигурация именованный удостоверений; в противном случае ссылка на конфигурацию удостоверения по умолчанию.  
  
3.  Если неименованный `<federationConfiguration>` элемент присутствует, это конфигурация по умолчанию федерации. Если его `identityConfiguration` атрибут указан, указывается конфигурация именованный удостоверений; в противном случае ссылка на конфигурацию удостоверения по умолчанию.  
  
4.  Если несколько именованных `<federationConfiguration>` элементы, присутствует и нет неименованных `<federationConfiguration>` одного элемента, создается исключение.  
  
 Как правило, только один `<federationConfiguration>` определенный раздел. Этот раздел представляет конфигурацию федерации по умолчанию. Можно указать несколько уникальность имен `<federationConfiguration>` элементов; Однако в этом случае, если требуется загрузить конфигурацию федерации, отличном от того, без имени, необходимо указать обработчик. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>событие и набор <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> свойство в обработчике для <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объект инициализирован со значениями из соответствующих `<federationConfiguration>` элемент в файле конфигурации.  
  
 `<federationConfiguration>` Представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> класса. Сам объект конфигурации представленного <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> класса. Один <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> набор экземпляров на <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойства и обеспечивает федеративной конфигурацию для приложения.  
  
## <a name="example"></a>Пример  
 Следующий XML-КОДЕ показано `<federationConfiguration>` элемент, который задает настройки для WSFAM и указывает, что обработчик куки-файл по умолчанию (экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класс) будет использоваться SAM.  
  
> [!WARNING]
>  В этом примере обработчик cookie ни WSFAM необходимы для использования протокола HTTPS. Это вызвано `requireHttps` атрибут `<wsFederation>` элемент и `requireSsl` для атрибута `<cookieHandlerElement>` являются `false`. Эти параметры не рекомендуется для большинства рабочих сред, как они могут представлять угрозу безопасности.  
  
```xml  
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
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
