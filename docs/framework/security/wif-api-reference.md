---
title: Справочник по API WIF
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f5a38420cf5ddb0a76946d5e44e98e1f39118236
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wif-api-reference"></a>Справочник по API WIF
В Windows Identity Foundation (WIF) классы размещаются в следующих сборках: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) и `System.ServiceModel` (System.ServiceModel.dll). В этом разделе приводятся ссылки на пространства имен WIF и вкратце описываются классы, которые содержит каждое из них.  
  
> [!IMPORTANT]
>  Следующие пространства имен `System.IdentityModel` содержат классы, которые реализуют модель удостоверений WCF на основе утверждений: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> и <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. Начиная с .NET Framework 4.5 модель удостоверений WCF на базе утверждений заменяется WIF. При создании решений на основе WIF не следует использовать классы из этих трех пространств имен.  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 Содержит классы, представляющие преобразования файлов cookie, службы маркеров безопасности, а также средства чтения словарей XML.  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 Содержит классы, которые обеспечивают настройку приложений и служб, создаваемых с помощью Windows Identity Foundation (WIF). Классы в этом пространстве имен представляют параметры в элементе [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 Содержит классы, представляющие элементы в документе метаданных федерации.  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 Содержит классы, представляющие артефакты WS-Trust.  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 Содержит классы, используемые в пассивных сценариях (WS-Federation). Также содержит некоторые классы, представляющие параметры в элементе [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Параметры в этом элементе настраивают WS-Federation для приложений. Пространство имен `System.IdentityModel.Services.Configuration` содержит большинство классов, используемых для настройки WS-Federation.  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 Содержит классы, обеспечивающие настройку приложений WIF, которые используют протокол WS-Federation. Классы в этом пространстве имен представляют параметры в элементе [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Пространство имен `System.IdentityModel.Services` также содержит большинство классов, используемых для настройки WS-Federation.  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 Содержит специальные обработчики маркеров безопасности для веб-ферм.  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 Содержит классы, представляющие маркеры безопасности, обработчики маркеров безопасности, а также другие артефакты маркеров безопасности.  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 Содержит классы, представляющие утверждения, удостоверения на основе утверждений, субъекты на основе утверждений, а также другие артефакты модели удостоверений на основе утверждений.  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 Содержит классы, представляющие контракты, каналы, узлы службы и другие артефакты WCF, которые используются в активных сценариях (WS-Trust). Это пространство имен также содержит классы, которые относятся к Windows Communication Foundation (WCF) и не используются платформой WIF.  
  
## <a name="see-also"></a>См. также  
 [Справочник по конфигурации WIF](../../../docs/framework/security/wif-configuration-reference.md)  
 [Сопоставление пространств имен между WIF 3.5 и WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
