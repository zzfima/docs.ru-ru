---
title: '&lt;Кэши&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2a9766b826eb7a708b4b4e99b6bd984f9fc76812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcachesgt"></a><span data-ttu-id="3cac5-102">&lt;Кэши&gt;</span><span class="sxs-lookup"><span data-stu-id="3cac5-102">&lt;caches&gt;</span></span>
<span data-ttu-id="3cac5-103">Регистрирует кэши, используемый для маркеров сеансов и обнаружение воспроизведения токенов.</span><span class="sxs-lookup"><span data-stu-id="3cac5-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="3cac5-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3cac5-104">\<system.identityModel></span></span>  
<span data-ttu-id="3cac5-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3cac5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3cac5-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="3cac5-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cac5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cac5-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cac5-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3cac5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3cac5-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3cac5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cac5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3cac5-110">Attributes</span></span>  
 <span data-ttu-id="3cac5-111">Нет</span><span class="sxs-lookup"><span data-stu-id="3cac5-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cac5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3cac5-112">Child Elements</span></span>  
  
|<span data-ttu-id="3cac5-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cac5-113">Element</span></span>|<span data-ttu-id="3cac5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3cac5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cac5-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="3cac5-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="3cac5-116">Регистрирует кэша для маркеров сеанса службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3cac5-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="3cac5-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="3cac5-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="3cac5-118">Регистрирует кэш воспроизведения токена службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3cac5-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cac5-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3cac5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3cac5-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cac5-120">Element</span></span>|<span data-ttu-id="3cac5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3cac5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cac5-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3cac5-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="3cac5-123">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="3cac5-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="3cac5-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3cac5-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3cac5-125">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3cac5-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cac5-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cac5-126">Remarks</span></span>  
 <span data-ttu-id="3cac5-127">A `<caches>` элемент можно задать на уровне службы под `<identityConfiguration>` элемент, либо на уровне коллекции обработчик маркеров безопасности в разделе `<securityTokenHandlerConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="3cac5-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="3cac5-128">Параметры в коллекцию обработчика токенов переопределяют алгоритмам, заданным в службе.</span><span class="sxs-lookup"><span data-stu-id="3cac5-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="3cac5-129">`<caches>` Представлен <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> класса.</span><span class="sxs-lookup"><span data-stu-id="3cac5-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="3cac5-130">Настроенный кэши представляются <xref:System.IdentityModel.Configuration.IdentityModelCaches> класса.</span><span class="sxs-lookup"><span data-stu-id="3cac5-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cac5-131">Пример</span><span class="sxs-lookup"><span data-stu-id="3cac5-131">Example</span></span>  
 <span data-ttu-id="3cac5-132">Следующий код XML показана конфигурация пользовательского кэша для хранения токенов безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="3cac5-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="3cac5-133">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="3cac5-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
