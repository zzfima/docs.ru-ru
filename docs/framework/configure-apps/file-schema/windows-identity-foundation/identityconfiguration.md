---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 91d64ce0d6a5cdbf32fec4a476fb111afe9a7952
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212499"
---
# <a name="identityconfiguration"></a>\<identityConfiguration>

Указывает параметры уровня службы идентификации.

 \<system.identityModel > \
\<identityConfiguration>

## <a name="syntax"></a>Синтаксис

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|имя|Имя раздела конфигурации удостоверения. Это имя можно использовать для ссылки на определенный раздел конфигурации. Если нет `name` атрибут указан, раздел определяет конфигурацию по умолчанию. Конфигурация по умолчанию всегда используется для пассивной федерации. Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемент.|
|saveBootstrapContext|Указывает, включаются ли токены начальной загрузки в токен сеанса. Также можно задать значение в коллекцию обработчиков токенов, задав `saveBootstrapContext` атрибут [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент. Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.|
|maximumClockSkew|Объект <xref:System.TimeSpan> , указывающее максимальное допустимое время отклонения. Определяет максимальное допустимое время отклонения при выполнении операций, зависящих от времени, таких как проверка срока действия сеанса входа в систему. Значение по умолчанию — 5 минут «00: 05:00». Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Также можно задать максимальную расфазировку синхронизирующих импульсов на коллекцию обработчиков токенов, задав `maximumClockSkew` атрибут [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент. Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<кэширует >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэши маркеров сеанса и обнаружения воспроизведения маркеров. Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности. Необязательный параметр.|
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Управляет параметрами, используемых обработчиками токена для проверки сертификатов. Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности. Необязательный параметр.|
|[\<claimsAuthenticationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Регистрирует диспетчер аутентификации утверждений для входящих утверждений. Необязательный параметр.|
|[\<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Регистрирует диспетчера авторизации утверждений для входящих утверждений. Необязательный параметр.|
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Указывает набор утверждений, необходимых для входящих маркеров безопасности. Необязательный параметр.|
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Задает коллекцию обработчиков токенов безопасности. Можно указать ноль или несколько коллекций обработчиков токенов безопасности. Необязательный параметр.|
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Включает обнаружение воспроизведения токенов и определяет срок действия маркеров. Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности. Необязательный параметр.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание:|
|-------------|-----------------|
|[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.|

## <a name="remarks"></a>Примечания

Несколько удостоверений, которые могут быть определены конфигурации, каждый с уникальным именем. Поведение выглядит следующим образом:

1. Если нет `<identityConfiguration>` указан элемент. Конфигурацией удостоверения по умолчанию создается во время выполнения и заполняется значениями по умолчанию.

2. Если одно `<identityConfiguration>` указан элемент. Это конфигурация по умолчанию. Это неважно, с именем или без имени.

3. При наличии нескольких `<identityConfiguration>` указаны элементы. Безымянный элемент указывает конфигурация по умолчанию. Рекомендуется, если задано несколько `<identityConfiguration>` элементов, один из них должен быть без имени.

> [!WARNING]
> Если задано несколько `<identityConfiguration>` элементов, один из них должен быть без имени. Неименованный элемент будет конфигурация по умолчанию.

 Некоторые из параметров, указанных в `<identityConfiguration>` элемент можно переопределить параметры на коллекцию обработчиков токенов безопасности или параметры на обработчики маркеров безопасности.

> [!IMPORTANT]
> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса, чтобы обеспечить управление доступом на основе утверждений в коде, конфигурация удостоверения, на который ссылается `<federationConfiguration>` элемент настраивает диспетчера авторизации утверждений и политику, которая используется для выполнения решения об авторизации. Это справедливо, даже в сценариях, которые не являются пассивных сценариях Web, например приложений Windows Communication Foundation (WCF) или приложение, которое не является веб. Если приложение не пассивное веб-приложение, [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) элемента (и политики его дочерние элементы, если он имеется) являются только параметры, применяемые на конфигурацию удостоверения, на которую указывает ссылка. Все остальные параметры игнорируются. Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемент.

`<identityConfiguration>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> класса. Раздел конфигурации удостоверения, представленного <xref:System.IdentityModel.Configuration.IdentityConfiguration> класса.

> [!IMPORTANT]
> Указание следующие элементы как дочерние элементы элемента `<identityConfiguration>` элемент является устаревшим, несмотря на то, что поведение по-прежнему поддерживается для обеспечения обратной совместимости. Эти элементы необходимо вместо этого указать в разделе [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент.
>
> - [\<audienceUris>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)
> - [\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)
> - [\<issuerTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)
> - [\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)

## <a name="example"></a>Пример

В следующем примере создается соответствующую конфигурацию удостоверения, с именем «alternateConfiguration». Конфигурация удостоверения задает параметры по умолчанию.

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
