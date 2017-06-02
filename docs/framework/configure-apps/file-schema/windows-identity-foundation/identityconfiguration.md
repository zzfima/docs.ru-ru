---
title: "&lt;identityConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# &lt;identityConfiguration&gt;
Задает параметры уровня службы удостоверений.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Имя раздела конфигурации identity.  Это имя можно использовать для ссылки на раздел определенной конфигурации.  Если не `name` атрибут указан, раздел определяет конфигурацию по умолчанию.  Конфигурация по умолчанию всегда используется в сценарии пассивной интеграции.  Дополнительные сведения см. в описании элемента [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).|  
|saveBootstrapContext|Указывает, включены ли загрузочный маркеров в маркер сеанса.  Также возможно установить значение на коллекции обработчик маркеров, задав `saveBootstrapContext` атрибут на [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент.  Значение в коллекцию обработчиков маркеров переопределяет значение, заданное на службу.|  
|maximumClockSkew|A <xref:System.TimeSpan> , определяющий максимальное разрешенные часы Наклон.  Управляет Наклон максимальное разрешенные часы при выполнении операций с учетом времени, такие как проверка время истечения срока действия сеанса входа.  Значение по умолчанию — 5 минут "00: 05".  Дополнительные сведения об указании <xref:System.TimeSpan> значения, см. [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  Наклон максимального времени могут быть указаны на коллекцию обработчика маркера, установив `maximumClockSkew` атрибут на [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент.  Значение в коллекцию обработчиков маркеров переопределяет значение, заданное на службу.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэши для обнаружения маркеров преобразования и маркеров сеансов.  Задается на уровне службы или на коллекцию обработчика маркера безопасности.  Необязательный.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Управляет параметрами, обработчиков маркеров для проверки сертификатов.  Задается на уровне службы или на коллекцию обработчика маркера безопасности.  Необязательный.|  
|[\<claimsAuthenticationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Регистрирует диспетчер проверки подлинности заявок для входящих утверждений.  Необязательный.|  
|[\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Регистрирует диспетчер авторизации заявок для входящих утверждений.  Необязательный.|  
|[\<claimTypeRequired\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Определяет набор необходимых утверждений для входящих токенов безопасности.  Необязательный.|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Указывает коллекции обработчиков маркеров безопасности.  Можно указать ноль или более коллекций обработчики маркеров безопасности.  Необязательный.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Включает маркера повторений и определяет срок действия маркеров.  Задается на уровне службы или на коллекцию обработчика маркера безопасности.  Необязательный.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.identityModel\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Содержит настройки для включения параметров Foundation удостоверение Windows \(WIF\) в приложениях.|  
  
## Заметки  
 Несколько идентификаторов, могут быть определены конфигурации, каждый с уникальным именем.  Поведение выглядит следующим образом:  
  
1.  Если не `<identityConfiguration>` указанного элемента.  Идентификатор конфигурации по умолчанию создается во время выполнения и заполняются значениями по умолчанию.  
  
2.  Если один `<identityConfiguration>` указанного элемента.  Это идентификатор конфигурации по умолчанию.  Не важно с именем или неименованными.  
  
3.  Если несколько `<identityConfiguration>` указанных элементов.  Безымянные элемент указывает идентификатор конфигурации по умолчанию.  Рекомендуется указывать несколько `<identityConfiguration>` элементов, один из них должен быть без имени.  
  
> [!WARNING]
>  Если задано несколько `<identityConfiguration>` элементов, один из них должен быть без имени.  Без имени элемента будет идентификатор конфигурации по умолчанию.  
  
 Некоторые из параметров, указанных в `<identityConfiguration>` элемент может быть переопределен путем настройки на коллекцию обработчика маркера безопасности или настройки обработчиков маркеров безопасности.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе заявок в коде конфигурации identity, на который ссылается `<federationConfiguration>` элемент настраивает диспетчер авторизации заявок и политики, который используется для принятия решения об авторизации.  Это верно даже в ситуациях, которые не являются пассивный веб\-сценариев, например приложения Windows Communication Foundation \(WCF\) или приложение, которое не является веб.  Если приложение не является пассивным веб\-приложения [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) элемент \(и политики его дочерних элементов, если они есть\) являются только параметры, применяемые конфигурации указанного удостоверения.  Другие параметры не обрабатываются.  Дополнительные сведения см. в описании элемента [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).  
  
 `<identityConfiguration>` Представленного элементом <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> класса.  Представленный раздел конфигурации identity <xref:System.IdentityModel.Configuration.IdentityConfiguration> класса.  
  
> [!IMPORTANT]
>  Указав следующие элементы в качестве дочерних элементов `<identityConfiguration>` элемент устарел, несмотря на то, что поведение по\-прежнему поддерживается для обратной совместимости.  Вместо этого указанного этих элементов в [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент.  
>   
>  -   [\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## Пример  
 В следующем примере создается конфигурация удостоверения, с именем «alternateConfiguration».  Идентификация конфигурации определяет параметры по умолчанию.  
  
```  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## См. также  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>   
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>