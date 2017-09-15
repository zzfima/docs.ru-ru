---
title: "Сопоставление пространств имен между WIF 3.5 и WIF 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9c3d726ee5b6da733ddaa79ec23943bb6faa43e5
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="namespace-mapping-between-wif-35-and-wif-45"></a>Сопоставление пространств имен между WIF 3.5 и WIF 4.5
Начиная с .NET 4.5 Windows Identity Foundation (WIF) полностью интегрирована в .NET Framework. Эта интеграция привела к изменениям имен и некоторой консолидации пространств имен WIF и области API. В этом разделе приведены некоторые рекомендации и общее сопоставление пространств имен WIF 3.5 и WIF 4.5. Этот раздел не является исчерпывающим. В нем представлены общие сведения о том, как найти знакомые классы WIF 3.5 в WIF 4.5. Дополнительные сведения о различиях между WIF 3.5 и WIF 4.5 см. в разделе [Новые возможности Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md). Руководство по миграции приложений, созданных с использованием WIF 3.5, в WIF 4.5 см. в разделе [Руководство по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
## <a name="wif-35-to-wif-45-namespace-map"></a>Сопоставление пространств имен WIF 3.5 и WIF 4.5  
 Классы WIF, которые находились в пространствах имен `Microsoft.IdentityModel` в WIF 3.5, в WIF 4.5 распределены по следующим пространствам имен: `System.Security.Claims`, `System.ServiceModel.Security` и `System.IdentityModel`. Кроме того, некоторые пространства имен WIF 3.5 были объединены или полностью удалены в WIF 4.5.  
  
> [!IMPORTANT]
>  Следующие пространства имен `System.IdentityModel` содержат классы, которые реализуют модель удостоверений WCF на основе утверждений: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> и <xref:System.IdentityModel.Selectors?displayProperty=fullName>. Модель удостоверений WCF на базе утверждений заменяется WIF. При создании решений на основе WIF не следует использовать классы из этих трех пространств имен.  
  
 В следующей таблице представлены сведения о том, как найти классы WIF 3.5 в WIF 4.5.  
  
|**Пространство имен WIF 3.5**|**Пространство имен WIF 4.5**|**Комментарии**|  
|-|-|-|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|– Большинство классов, которые представляют константы, не реализованы.<br />– Классы, которые используются для создания служб маркеров безопасности, перемещены из `Microsoft.IdentityModel.SecurityTokenService` в <xref:System.IdentityModel?displayProperty=fullName>.<br />– Классы в `Microsoft.IdentityModel.Threading` перемещены в <xref:System.IdentityModel?displayProperty=fullName>.<br />– Классы `ExceptionMapper` и `MruSecurityTokenCache` не реализованы.|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|– Интерфейсы `IClaimsPrincipal` и `IClaimsIdentity` не реализованы в WIF 4.5. Теперь <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> и <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> — это базовые классы, от которых наследуется большинство классов субъектов и удостоверений .NET. Это означает, что в WIF 4.5 не требуется использовать специализированные классы субъектов и удостоверений утверждений, такие как `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` и `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity`. Вместо них используйте <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> и <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName>. То же справедливо для других специализированных классов субъектов и удостоверений утверждений, которые использовались в WIF 3.5.<br />– Класс `Microsoft.IdentityModel.Claims.ClaimsCollection` не реализован в WIF 4.5. Вместо этого коллекции утверждений представлены в виде перечислимых коллекций типа <xref:System.Security.Claims.Claim?displayProperty=fullName>.<br />Теперь -   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> и <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> предоставляют методы, которые полностью поддерживают LINQ.|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|Некоторые элементы и классы в WIF 4.5 были удалены, у других были изменены имена; например, `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` теперь носит имя <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|Не реализовано в WIF 4.5|В WIF 3.5 присутствовали классы для поддержки CardSpace, эти классы не реализованы в WIF 4.5.|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|Разделено между пространствами имен <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> и <xref:System.ServiceModel.Security?displayProperty=fullName>.|Классы, представляющие артефакты WS-Trust (например, класс <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>), находятся в пространстве имен <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>. Классы, которые представляют контракты службы WCF, узлы службы и каналы, позволяющие службе WCF обмениваться данными по протоколу WS-Trust, находятся в пространстве имен <xref:System.ServiceModel.Security?displayProperty=fullName>. К таким классам относится, например, класс <xref:System.ServiceModel.Security.WSTrustServiceHost>.|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|Не реализовано в WIF 4.5|-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|Не реализовано в WIF 4.5|Включало классы, которые представляли константы шифрования XML в WIF 3.5. Эти константы не реализованы в WIF 4.5.|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|Класс `EnvelopingSignature` и классы, которые представляют константы, не реализованы.|  
|`Microsoft.IdentityModel.SecurityTokenService`|Разделено между пространствами имен <xref:System.IdentityModel?displayProperty=fullName>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> и <xref:System.IdentityModel.Tokens?displayProperty=fullName>.|-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|Большинство классов, которые предоставляют конфигурацию для пассивных сценариев (WS-Federation), были перемещены в <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>, однако некоторые из этих классов находятся в <xref:System.IdentityModel.Services?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Web.Controls`|Не реализовано в WIF 4.5|Классы в `Microsoft.IdentityModel.Web.Controls` реализуют федеративное пассивное управление входом в систему, которое отсутствует в WIF 4.5.|  
|`Microsoft.IdentityModel.WindowsTokenService`|Не реализовано в WIF 4.5|-|  
  
## <a name="see-also"></a>См. также  
 [Новые возможности Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)   
 [Руководства по миграции приложения, созданного с использованием WIF 3.5, в WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)

