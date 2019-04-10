---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: e0ac3b663b2a65e00524fe0fba7997125721487c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297491"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Настраивает <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM), при использовании Федеративная проверка подлинности по протоколу WS-Federation. Настраивает <xref:System.Security.Claims.ClaimsAuthorizationManager> при использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класс, чтобы обеспечить управление доступом на основе утверждений.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
  
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
|имя|Имя данного элемента конфигурации федерации. Этот атрибут главным образом предоставляет точку расширения для будущих протоколов. Необязательный параметр.|  
|identityConfigurationName|Имя раздела конфигурации удостоверений, как указано в [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент для использования. Если этот атрибут не указан, используется раздел конфигурации удостоверений по умолчанию. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает обработчик файлов cookie, используемый SAM. Необязательный параметр.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки маркеров. Необязательный параметр.|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Настраивает модуль проверки подлинности WS-Federation (WSFAM). Необязательный параметр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.|  
  
## <a name="remarks"></a>Примечания  
 \<FederationConfiguration > элемент предоставляет параметры в двух разных сценариев:  
  
-   При использовании WS-Federation passive веб-приложения, элемент содержит параметры, определяющие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Он также ссылается на конфигурацию удостоверения, чтобы использовать для настройки обработчики маркеров безопасности и сертификаты и компоненты, такие как диспетчер авторизации утверждений и диспетчер аутентификации утверждений.  
  
-   При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса, чтобы обеспечить управление доступом на основе утверждений в коде, элемент, ссылающийся на конфигурацию удостоверения, который настраивает диспетчера авторизации утверждений и политику, которая используется для выполнения авторизации решения. Это верно даже в сценариях, которые не являются пассивных сценариях Web; Например, приложение, которое не является веб-или приложений Windows Communication Foundation (WCF). Если приложение не пассивное веб-приложение, [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) элемента (и политики его дочерние элементы, если он имеется) конфигурации удостоверения, ссылается `<federationConfiguration>` элемент применяются только параметры. Другие атрибуты игнорируются.  
  
 Независимо от сценария среда выполнения загружает конфигурации федерации по умолчанию. Поведение определяется следующим образом:  
  
1. Если нет `<federationConfiguration>` элемент присутствует, среда выполнения создает конфигурацию федерации и заполняет его значения по умолчанию. Эта конфигурация федерации будет ссылаться на конфигурацию удостоверения по умолчанию.  
  
2. Если одно `<federationConfiguration>` элемент присутствует, он является конфигурацией федерации по умолчанию независимо от того, независимо от того, является ли она с именем или без имени. Если его `identityConfiguration` атрибут указан, на который приведена ссылка на конфигурацию удостоверения именованный; в противном случае используется конфигурация по умолчанию.  
  
3. Если неименованный `<federationConfiguration>` элемент присутствует, это конфигурация по умолчанию федерации. Если его `identityConfiguration` атрибут указан, на который приведена ссылка на конфигурацию удостоверения именованный; в противном случае используется конфигурация по умолчанию.  
  
4. Если несколько с именем `<federationConfiguration>` элементы являются присутствует и нет неименованных `<federationConfiguration>` присутствует элемент, возникает исключение.  
  
 Как правило, только один `<federationConfiguration>` определен раздел. Этот раздел представляет конфигурацию федерации по умолчанию. Можно указать несколько, с уникальным именем `<federationConfiguration>` элементов; Однако в этом случае, если вы хотите загрузить конфигурацию федерации, отличном от того, без имени, необходимо указать обработчик для. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> событие и набор <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> свойство внутри обработчика <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объект инициализирован со значениями из соответствующих `<federationConfiguration>` элемент в файле конфигурации.  
  
 `<federationConfiguration>` Элемент, представленный объектом <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> класса. Сам объект конфигурации представленного <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> класса. Один <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> экземпляр устанавливается на <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойство и предоставляет федеративной конфигурации для приложения.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает `<federationConfiguration>` элемент, который задает параметры для WSFAM и указывает, что обработчик файлов cookie по умолчанию (экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса) будет использоваться SAM.  
  
> [!WARNING]
>  В этом примере ни обработчик файлов cookie, ни WSFAM необходимы для использования протокола HTTPS. Это обусловлено `requireHttps` атрибут `<wsFederation>` элемент и `requireSsl` атрибут `<cookieHandlerElement>` являются `false`. Эти параметры не рекомендуется для большинства рабочих сред, как они могут представлять угрозу безопасности.  
  
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

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
