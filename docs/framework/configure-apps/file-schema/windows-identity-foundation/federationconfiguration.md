---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152740"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Настраивает <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) при использовании федеративной аутентификации через протокол WS-Federation. Настраивает <xref:System.Security.Claims.ClaimsAuthorizationManager> при использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> или классе для обеспечения контроля доступа на основе утверждений.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<федерацияКонфигурация>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|name|Имя этого элемента конфигурации федерации. Этот атрибут в первую очередь обеспечивает точку размнозамости для будущих протоколов. Необязательный параметр.|  
|личностьConfigurationName|Имя раздела конфигурации идентификации, указанное в [ \<идентификационномконфигурации,>](identityconfiguration.md) элемент для использования. Если этот атрибут не указан, используется раздел конфигурации идентификации по умолчанию. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Настраивает обработчик файлов cookie, используемый SAM. Необязательный параметр.|  
|[\<>сервис-сертификат](servicecertificate.md)|Настраивает сертификат, который используется для шифрования и расшифровки токенов. Необязательный параметр.|  
|[\<wsFederation>](wsfederation.md)|Настраивает модуль аутентификации WS-Federation (WSFAM). Необязательный параметр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Раздел конфигурации для проверки подлинности с использованием протокола WS-Federation.|  
  
## <a name="remarks"></a>Remarks  
 Элемент \<> federationConfiguration предоставляет настройки в двух различных сценариях:  
  
- При использовании WS-Federation в пассивном веб-приложении элемент <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> содержит настройки, <xref:System.IdentityModel.Services.SessionAuthenticationModule> настраивающие (WSFAM) и (SAM). Он также ссылается на конфигурацию идентификационных данных, которая будет использоваться для настройки обработчиков и сертификатов маркеров безопасности, а также такие компоненты, как менеджер авторизации утверждений и менеджер проверки подлинности утверждений.  
  
- При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или класса для предоставления в коде элемента на основе утверждений ссылки на конфигурацию идентификации, которая настраивает менеджер авторизации утверждений и политику, которая используется для принятия решений о авторизации. Это верно даже в сценариях, которые не являются пассивными веб-сценариями; например, приложения Windows Communication Foundation (WCF) или приложение, не основанное на веб-базе. Если приложение не является пассивным веб-приложением, [ \<то претензииАвторизируяmanager>](claimsauthorizationmanager.md) элемент (и его элементы политики ребенка, если присутствует) конфигурации идентификации, на которую ссылается `<federationConfiguration>` элемент, являются единственными применяемыми параметрами. Другие атрибуты игнорируются.  
  
 Независимо от сценария, время выполнения загружает конфигурацию федерации по умолчанию. Поведение определяется следующим образом:  
  
1. Если нет `<federationConfiguration>` элемента, время выполнения создает конфигурацию федерации и заполняет ее значениями по умолчанию. Эта конфигурация федерации по умолчанию будет ссылаться на конфигурацию идентификации по умолчанию.  
  
2. При наличии одного `<federationConfiguration>` элемента это конфигурация федерации по умолчанию независимо от того, назван он или неназван. Если `identityConfiguration` его атрибут указан, то на именование конфигурации идентификации ссылаются; в противном случае ссылка на конфигурацию идентификации по умолчанию.  
  
3. При наличии `<federationConfiguration>` неназванного элемента это конфигурация федерации по умолчанию. Если `identityConfiguration` его атрибут указан, то на именование конфигурации идентификации ссылаются; в противном случае ссылка на конфигурацию идентификации по умолчанию.  
  
4. При наличии нескольких названных `<federationConfiguration>` `<federationConfiguration>` элементов и нет неназванного элемента, выбрасывается исключение.  
  
 Как правило, `<federationConfiguration>` определяется только один раздел. Этот раздел представляет собой конфигурацию федерации по умолчанию. Вы можете указать несколько, однозначно названных `<federationConfiguration>` элементов; однако в этом случае, если вы хотите загрузить конфигурацию федерации, кроме неназванной, необходимо предоставить обработчик для. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>событие и <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> установить свойство <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> внутри обработчика к `<federationConfiguration>` объекту, инициализированному с значениями из соответствующего элемента в файле конфигурации.  
  
 Элемент `<federationConfiguration>` представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> классом. Сам объект конфигурации представлен <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> классом. Один <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> экземпляр устанавливается <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> на свойстве и обеспечивает федеративную конфигурацию приложения.  
  
## <a name="example"></a>Пример  
 Следующий XML `<federationConfiguration>` отображает элемент, определяющий параметры для WSFAM, и указывает, что обработчик <xref:System.IdentityModel.Services.ChunkedCookieHandler> файлов cookie по умолчанию (экземпляр класса) используется SAM.  
  
> [!WARNING]
> В этом примере ни обработчик файлов cookie, ни WSFAM не обязаны использовать HTTPS. Это связано `requireHttps` с `<wsFederation>` тем, `requireSsl` что атрибут `<cookieHandlerElement>` `false`на элементе и атрибутна на являются . Эти параметры не рекомендуются для большинства производственных сред, поскольку они могут представлять угрозу безопасности.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<идентичностьНастройка>](identityconfiguration.md)
