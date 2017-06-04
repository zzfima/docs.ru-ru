---
title: "&lt;federationConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;federationConfiguration&gt;
Настройка <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> федеративного \(SAM\), при использовании проверки подлинности по протоколу WS\-Federation.  Настройка <xref:System.Security.Claims.ClaimsAuthorizationManager> при использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе заявок.  
  
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
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Имя элемента конфигурации федерации.  Этот атрибут в первую очередь обеспечивает точку расширения для будущих протоколов.  Необязательный.|  
|identityConfigurationName|Имя раздела конфигурации идентификатора, указанного в [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента для использования.  Если этот атрибут не указан, используется раздел конфигурации по умолчанию удостоверения.  Необязательный.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает обработчик файлов cookie, используемый SAM.  Необязательный.|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Настройка сертификата, который используется для шифрования и расшифровки маркеры.  Необязательный.|  
|[\<wsFederation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Настраивает модуль проверки подлинности WS\-Federation \(WSFAM\).  Необязательный.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.identityModel.services\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Раздел конфигурации для проверки подлинности с помощью протокола WS\-Federation.|  
  
## Заметки  
 \<federationConfiguration\> элемент содержит параметры в двух разных сценариев:  
  
-   При использовании WS\-Federation passive веб\-приложения, элемент содержит параметры конфигурации <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).  Он также ссылается на удостоверение конфигурация, настройки обработчиков маркеров безопасности и сертификаты и компонентами, такими как диспетчер авторизации заявок и диспетчер проверки подлинности заявки.  
  
-   При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе заявок в коде, элемент ссылается на удостоверение конфигурации, который настраивает диспетчер авторизации заявок и политики, который используется для принятия решения об авторизации.  Это верно даже в ситуациях, которые не являются пассивный веб\-сценариев; Например, приложения Windows Communication Foundation \(WCF\) или не является веб\-приложение.  Если приложение не является пассивным веб\-приложения, [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) элемент \(и политики его дочерних элементов, если они есть\) Идентификация конфигурации, ссылается `<federationConfiguration>` элемента являются только параметры, применяемые.  Другие члены не обрабатываются.  
  
 Вне зависимости от ситуации среда выполнения загружает федерации конфигурации по умолчанию.  Поведение определяется следующим образом:  
  
1.  Если не `<federationConfiguration>` элемент существует, среда выполнения создает конфигурации федерации и заполняет значениями по умолчанию.  Эта конфигурация федерации будет ссылаться на идентификатор конфигурации по умолчанию.  
  
2.  Если один `<federationConfiguration>` элемент присутствует, это конфигурация по умолчанию федерации независимо от ли она с именем или неименованными.  Если его `identityConfiguration` указан атрибут, указанный именованный идентификатор конфигурации; в противном случае указанный идентификатор конфигурации по умолчанию.  
  
3.  Если неименованный `<federationConfiguration>` элемент присутствует, он представляет собой конфигурацию по умолчанию федерации.  Если его `identityConfiguration` указан атрибут, указанный именованный идентификатор конфигурации; в противном случае указанный идентификатор конфигурации по умолчанию.  
  
4.  Если несколько `<federationConfiguration>` элементы имеются в наличии и не неименованный `<federationConfiguration>` элемент отсутствует, генерируется исключение.  
  
 Как правило, только один `<federationConfiguration>` определенный раздел.  В этом разделе Конфигурация по умолчанию федерации.  Можно указать несколько, однозначно с именем `<federationConfiguration>` элементов; Однако в этом случае, если вы хотите загрузить конфигурацию федерации, отличный от неименованный необходимо предоставить обработчик для.  <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>события и установить <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> свойство внутри обработчика для <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> инициализируются значениями из соответствующего объекта `<federationConfiguration>` элемент в файле конфигурации.  
  
 `<federationConfiguration>` Представленного элементом <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> класса.  Представленный самого объекта конфигурации <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> класса.  Один <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> экземпляр устанавливается на <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> свойства и обеспечивает федеративные конфигурации для приложения.  
  
## Пример  
 Показано в следующем XML `<federationConfiguration>` элемент, который определяет параметры для WSFAM и указывает, что обработчик по умолчанию файл cookie \(экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класс\) использовать SAM.  
  
> [!WARNING]
>  В этом примере обработчик cookie ни WSFAM необходимо использовать протокол HTTPS.  Это происходит потому, что `requireHttps` атрибут на `<wsFederation>` элемент и `requireSsl` атрибут на `<cookieHandlerElement>` , `false`.  Эти параметры не рекомендуется для большинства рабочих средах, как они могут представлять угрозу безопасности.  
  
```  
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
  
## См. также  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>   
 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)