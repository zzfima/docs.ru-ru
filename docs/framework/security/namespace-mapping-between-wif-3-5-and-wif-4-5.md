---
title: "Сопоставление пространств имен между WIF 3.5 и WIF 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Сопоставление пространств имен между WIF 3.5 и WIF 4.5
Начиная с .NET 4.5, являются основой идентификатора Windows \(WIF\) полностью встроено в платформе .NET Framework.  Эта интеграция engendered изменения имен и некоторая консолидация пространств имен WIF и области API.  В этом разделе приведены некоторые рекомендации и общее сопоставление между пространствами имен WIF 3.5 и пространствами имен WIF 4,5.  Не предназначено исчерпывающим, а предоставляет некоторые общие сведения о том, где найти знакомые классы WIF 3.5 в WIF 4,5.  Дополнительные сведения о различиях между WIF 3.5 и WIF 4.5 см. в разделе [Новые возможности Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md).  Для руководства о переносе приложения, построенные с помощью WIF 3.5 до 4,5 WIF см. в разделе [Рекомендации по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
## Сопоставление пространства имен WIF 3.5 до 4,5 WIF  
 Классы WIF, которые были собраны с пространствами имен `Microsoft.IdentityModel` в WIF 3.5, теперь распределятьы из следующих пространств имен: `System.Security.Claims`, `System.ServiceModel.Security` и пространства имен `System.IdentityModel` в WIF 4,5.  Помимо этого пространства имен определенного WIF 3.5 были консолидированы или были удалены полностью на WIF 4,5.  
  
> [!IMPORTANT]
>  Следующие пространства имен `System.IdentityModel` содержат классы, которые реализуют модель идентификатор на основе утверждений WCF. <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> и <xref:System.IdentityModel.Selectors?displayProperty=fullName>.  Модель идентификатор на основе утверждений WCF заменен WIF.  Не следует использовать классы в этих пространствах имен 3 при построении решения на основе WIF.  
  
 Следующая таблица содержит сведения о том, где классы WIF 3.5 можно найти в WIF 4,5.  
  
||||  
|-|-|-|  
|**Пространство имен WIF 3.5**|**Пространство имен WIF 4,5**|**Комментарии**|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|-   Большинство классов, представляющих константы не реализована.<br />-   Классы, используемые для построения службы маркеров безопасности были перемещены из `Microsoft.IdentityModel.SecurityTokenService` к <xref:System.IdentityModel?displayProperty=fullName>.<br />-   Классы в `Microsoft.IdentityModel.Threading` были перемещены к <xref:System.IdentityModel?displayProperty=fullName>.<br />-   Классы `ExceptionMapper` и `MruSecurityTokenCache` не реализованы.|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|-   Интерфейсы `IClaimsPrincipal` и `IClaimsIdentity` не реализованы в WIF 4,5.  Вместо <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> и <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> теперь базовые классы из которых большинство классов субъекта и идентификатора .NET являются производными.  Это означает, что нет необходимости для специализированных утверждений субъекта и классов, как `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` идентификатора и `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` в WIF 4,5, используйте <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> и <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName>.  Это также относится к другу для других специализированных утверждений субъекта и классов идентификатора, существовавшие в WIF 3.5.<br />-   Класс `Microsoft.IdentityModel.Claims.ClaimsCollection` не реализован в WIF 4,5.  Вместо этого коллекции утверждений предоставлены как перечисляемую коллекцию типа <xref:System.Security.Claims.Claim?displayProperty=fullName>.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> и <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> предоставляют методы, которые теперь полностью поддерживают LINQ.|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|Некоторые элементы и классы и некоторые были пройдены изменения имен удалены в WIF 4,5; например `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` теперь <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|Не реализованный в WIF 4,5|В WIF 3.5 содержит классы для поддержки CardSpace, реализованный в WIF не 4,5.|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|Разбиение " между <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> и пространствами имен <xref:System.ServiceModel.Security?displayProperty=fullName>.|Классы, представляющее артефакты WS\- Доверия в пространстве имен <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>; например, класс <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>.  Классы, представляющие контракты служб, узлы служб и каналов WCF, позволяющие службы WCF для взаимодействия по протоколу WS\- Доверия в пространстве имен <xref:System.ServiceModel.Security?displayProperty=fullName>; например, класс <xref:System.ServiceModel.Security.WSTrustServiceHost>.|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|Не реализованный в WIF 4,5|\-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|Не реализованный в WIF 4,5|Содержит классы, представляющие константы шифрования XML в WIF 3.5.  Эти константы не реализованы в WIF 4,5.|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|Класс и классы `EnvelopingSignature`, представляющих константы не реализованы.|  
|`Microsoft.IdentityModel.SecurityTokenService`|Разделение между <xref:System.IdentityModel?displayProperty=fullName>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> и пространствами имен <xref:System.IdentityModel.Tokens?displayProperty=fullName>.|\-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|Классы, предоставляющие конфигурацию пассивных сценариев \(WS\-Federation\) во многом были перемещены к <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>; однако некоторые из этих классов в <xref:System.IdentityModel.Services?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Web.Controls`|Не реализованный в WIF 4,5|Классы в `Microsoft.IdentityModel.Web.Controls` реализации федеративной пассивное элемент управления входа, которое не существует в WIF 4,5.|  
|`Microsoft.IdentityModel.WindowsTokenService`|Не реализованный в WIF 4,5|\-|  
  
## См. также  
 [Новые возможности Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)   
 [Рекомендации по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)