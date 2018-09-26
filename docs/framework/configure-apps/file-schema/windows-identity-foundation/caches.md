---
title: '&lt;Кэши&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: a91a389e53354e4f5b26e1510fc2f025300d65cc
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084245"
---
# <a name="ltcachesgt"></a><span data-ttu-id="769e1-102">&lt;Кэши&gt;</span><span class="sxs-lookup"><span data-stu-id="769e1-102">&lt;caches&gt;</span></span>
<span data-ttu-id="769e1-103">Регистрирует кэши маркеров сеанса и обнаружения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="769e1-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="769e1-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="769e1-104">\<system.identityModel></span></span>  
<span data-ttu-id="769e1-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="769e1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="769e1-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="769e1-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769e1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="769e1-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="769e1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="769e1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="769e1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="769e1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="769e1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="769e1-110">Attributes</span></span>  
 <span data-ttu-id="769e1-111">Нет</span><span class="sxs-lookup"><span data-stu-id="769e1-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="769e1-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="769e1-112">Child Elements</span></span>  
  
|<span data-ttu-id="769e1-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="769e1-113">Element</span></span>|<span data-ttu-id="769e1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="769e1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="769e1-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="769e1-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="769e1-116">Регистрирует кэш токенов сеансов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="769e1-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="769e1-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="769e1-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="769e1-118">Регистрирует кэш повторного использования токенов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="769e1-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="769e1-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="769e1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="769e1-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="769e1-120">Element</span></span>|<span data-ttu-id="769e1-121">Описание</span><span class="sxs-lookup"><span data-stu-id="769e1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="769e1-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="769e1-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="769e1-123">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="769e1-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="769e1-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="769e1-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="769e1-125">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="769e1-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="769e1-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="769e1-126">Remarks</span></span>  
 <span data-ttu-id="769e1-127">Объект `<caches>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="769e1-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="769e1-128">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="769e1-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="769e1-129">`<caches>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> класса.</span><span class="sxs-lookup"><span data-stu-id="769e1-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="769e1-130">Настраиваемые кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> класса.</span><span class="sxs-lookup"><span data-stu-id="769e1-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="769e1-131">Пример</span><span class="sxs-lookup"><span data-stu-id="769e1-131">Example</span></span>  
 <span data-ttu-id="769e1-132">Следующий код XML показана конфигурация пользовательского кэша для хранения сеанса маркеров безопасности (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="769e1-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="769e1-133">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="769e1-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
