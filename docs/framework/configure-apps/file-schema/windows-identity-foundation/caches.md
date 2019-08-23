---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941969"
---
# <a name="caches"></a><span data-ttu-id="e705f-101">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="e705f-101">\<caches></span></span>
<span data-ttu-id="e705f-102">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="e705f-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="e705f-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="e705f-103">\<system.identityModel></span></span>  
<span data-ttu-id="e705f-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e705f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e705f-105">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="e705f-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e705f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e705f-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e705f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e705f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e705f-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e705f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e705f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e705f-109">Attributes</span></span>  
 <span data-ttu-id="e705f-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e705f-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e705f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e705f-111">Child Elements</span></span>  
  
|<span data-ttu-id="e705f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e705f-112">Element</span></span>|<span data-ttu-id="e705f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e705f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e705f-114">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="e705f-114">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="e705f-115">Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e705f-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="e705f-116">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="e705f-116">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="e705f-117">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e705f-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e705f-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e705f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e705f-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="e705f-119">Element</span></span>|<span data-ttu-id="e705f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e705f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e705f-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e705f-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="e705f-122">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="e705f-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="e705f-123">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="e705f-123">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e705f-124">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e705f-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e705f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="e705f-125">Remarks</span></span>  
 <span data-ttu-id="e705f-126">Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<caches>`</span><span class="sxs-lookup"><span data-stu-id="e705f-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="e705f-127">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="e705f-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="e705f-128">`<caches>` Элемент представлен<xref:System.IdentityModel.Configuration.IdentityModelCachesElement> классом.</span><span class="sxs-lookup"><span data-stu-id="e705f-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="e705f-129">Настроенные кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> классом.</span><span class="sxs-lookup"><span data-stu-id="e705f-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e705f-130">Пример</span><span class="sxs-lookup"><span data-stu-id="e705f-130">Example</span></span>  
 <span data-ttu-id="e705f-131">В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="e705f-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="e705f-132">Конфигурация берется из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="e705f-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
