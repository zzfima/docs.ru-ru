---
title: Справочник по API WIF
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
ms.openlocfilehash: c94ccd3f25be576c57fda798c6b2b8cc25357022
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645894"
---
# <a name="wif-api-reference"></a><span data-ttu-id="84a35-102">Справочник по API WIF</span><span class="sxs-lookup"><span data-stu-id="84a35-102">WIF API Reference</span></span>
<span data-ttu-id="84a35-103">В Windows Identity Foundation (WIF) классы размещаются в следующих сборках: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) и `System.ServiceModel` (System.ServiceModel.dll).</span><span class="sxs-lookup"><span data-stu-id="84a35-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="84a35-104">В этом разделе приводятся ссылки на пространства имен WIF и вкратце описываются классы, которые содержит каждое из них.</span><span class="sxs-lookup"><span data-stu-id="84a35-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84a35-105">Следующие пространства имен `System.IdentityModel` содержат классы, которые реализуют модель удостоверений WCF на основе утверждений: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> и <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84a35-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84a35-106">Начиная с .NET Framework 4.5 модель удостоверений WCF на базе утверждений заменяется WIF.</span><span class="sxs-lookup"><span data-stu-id="84a35-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="84a35-107">При создании решений на основе WIF не следует использовать классы из этих трех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="84a35-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-108">Содержит классы, представляющие преобразования файлов cookie, службы маркеров безопасности, а также средства чтения словарей XML.</span><span class="sxs-lookup"><span data-stu-id="84a35-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-109">Содержит классы, которые обеспечивают настройку приложений и служб, создаваемых с помощью Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="84a35-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="84a35-110">Классы в этом пространстве имен представляют параметры в элементе [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).</span><span class="sxs-lookup"><span data-stu-id="84a35-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-111">Содержит классы, представляющие элементы в документе метаданных федерации.</span><span class="sxs-lookup"><span data-stu-id="84a35-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-112">Содержит классы, представляющие артефакты WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="84a35-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-113">Содержит классы, используемые в пассивных сценариях (WS-Federation).</span><span class="sxs-lookup"><span data-stu-id="84a35-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="84a35-114">Также содержит некоторые классы, представляющие параметры в элементе [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a35-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="84a35-115">Параметры в этом элементе настраивают WS-Federation для приложений.</span><span class="sxs-lookup"><span data-stu-id="84a35-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="84a35-116">Пространство имен `System.IdentityModel.Services.Configuration` содержит большинство классов, используемых для настройки WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="84a35-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-117">Содержит классы, обеспечивающие настройку приложений WIF, которые используют протокол WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="84a35-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="84a35-118">Классы в этом пространстве имен представляют параметры в элементе [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a35-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="84a35-119">Пространство имен `System.IdentityModel.Services` также содержит большинство классов, используемых для настройки WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="84a35-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-120">Содержит специальные обработчики маркеров безопасности для веб-ферм.</span><span class="sxs-lookup"><span data-stu-id="84a35-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-121">Содержит классы, представляющие маркеры безопасности, обработчики маркеров безопасности, а также другие артефакты маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="84a35-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-122">Содержит классы, представляющие утверждения, удостоверения на основе утверждений, субъекты на основе утверждений, а также другие артефакты модели удостоверений на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="84a35-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="84a35-123">Содержит классы, представляющие контракты, каналы, узлы службы и другие артефакты WCF, которые используются в активных сценариях (WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="84a35-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="84a35-124">Это пространство имен также содержит классы, которые относятся к Windows Communication Foundation (WCF) и не используются платформой WIF.</span><span class="sxs-lookup"><span data-stu-id="84a35-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a35-125">См. также</span><span class="sxs-lookup"><span data-stu-id="84a35-125">See also</span></span>

- [<span data-ttu-id="84a35-126">Справочник по конфигурации WIF</span><span class="sxs-lookup"><span data-stu-id="84a35-126">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)
- [<span data-ttu-id="84a35-127">Сопоставление пространств имен между WIF 3.5 и WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="84a35-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
