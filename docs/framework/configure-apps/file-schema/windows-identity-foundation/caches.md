---
title: "&lt;кэши&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f0c46532cb7716f4dc066f0e96c14534d7fa0b42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltcachesgt"></a><span data-ttu-id="d1707-102">&lt;кэши&gt;</span><span class="sxs-lookup"><span data-stu-id="d1707-102">&lt;caches&gt;</span></span>
<span data-ttu-id="d1707-103">Регистрирует кэши, используемый для маркеров сеансов и обнаружение воспроизведения токенов.</span><span class="sxs-lookup"><span data-stu-id="d1707-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="d1707-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d1707-104">\<system.identityModel></span></span>  
<span data-ttu-id="d1707-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d1707-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d1707-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="d1707-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1707-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1707-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1707-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1707-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d1707-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1707-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1707-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1707-110">Attributes</span></span>  
 <span data-ttu-id="d1707-111">Нет</span><span class="sxs-lookup"><span data-stu-id="d1707-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1707-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1707-112">Child Elements</span></span>  
  
|<span data-ttu-id="d1707-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1707-113">Element</span></span>|<span data-ttu-id="d1707-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d1707-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1707-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="d1707-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="d1707-116">Регистрирует кэша для маркеров сеанса службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1707-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="d1707-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="d1707-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="d1707-118">Регистрирует кэш воспроизведения токена службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1707-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1707-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1707-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d1707-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1707-120">Element</span></span>|<span data-ttu-id="d1707-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d1707-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1707-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d1707-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="d1707-123">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="d1707-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="d1707-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d1707-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d1707-125">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="d1707-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1707-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1707-126">Remarks</span></span>  
 <span data-ttu-id="d1707-127">A `<caches>` элемент можно задать на уровне службы под `<identityConfiguration>` элемент, либо на уровне коллекции обработчик маркеров безопасности в разделе `<securityTokenHandlerConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="d1707-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="d1707-128">Параметры в коллекцию обработчика токенов переопределяют алгоритмам, заданным в службе.</span><span class="sxs-lookup"><span data-stu-id="d1707-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="d1707-129">`<caches>` Представлен <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> класса.</span><span class="sxs-lookup"><span data-stu-id="d1707-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="d1707-130">Настроенный кэши представляются <xref:System.IdentityModel.Configuration.IdentityModelCaches> класса.</span><span class="sxs-lookup"><span data-stu-id="d1707-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1707-131">Пример</span><span class="sxs-lookup"><span data-stu-id="d1707-131">Example</span></span>  
 <span data-ttu-id="d1707-132">Следующий код XML показана конфигурация пользовательского кэша для хранения токенов безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="d1707-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d1707-133">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="d1707-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
