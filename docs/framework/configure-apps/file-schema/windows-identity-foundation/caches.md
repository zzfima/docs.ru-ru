---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252164"
---
# <a name="caches"></a><span data-ttu-id="733ae-101">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="733ae-101">\<caches></span></span>
<span data-ttu-id="733ae-102">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="733ae-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="733ae-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="733ae-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="733ae-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="733ae-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="733ae-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="733ae-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="733ae-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> кэшей**</span><span class="sxs-lookup"><span data-stu-id="733ae-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="733ae-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="733ae-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="733ae-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="733ae-108">Attributes and Elements</span></span>  
 <span data-ttu-id="733ae-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="733ae-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="733ae-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="733ae-110">Attributes</span></span>  
 <span data-ttu-id="733ae-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="733ae-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="733ae-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="733ae-112">Child Elements</span></span>  
  
|<span data-ttu-id="733ae-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="733ae-113">Element</span></span>|<span data-ttu-id="733ae-114">Описание</span><span class="sxs-lookup"><span data-stu-id="733ae-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="733ae-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="733ae-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="733ae-116">Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="733ae-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="733ae-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="733ae-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="733ae-118">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="733ae-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="733ae-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="733ae-119">Parent Elements</span></span>  
  
|<span data-ttu-id="733ae-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="733ae-120">Element</span></span>|<span data-ttu-id="733ae-121">Описание</span><span class="sxs-lookup"><span data-stu-id="733ae-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="733ae-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="733ae-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="733ae-123">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="733ae-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="733ae-124">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="733ae-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="733ae-125">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="733ae-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="733ae-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="733ae-126">Remarks</span></span>  
 <span data-ttu-id="733ae-127">Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<caches>`</span><span class="sxs-lookup"><span data-stu-id="733ae-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="733ae-128">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="733ae-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="733ae-129">`<caches>` Элемент представлен<xref:System.IdentityModel.Configuration.IdentityModelCachesElement> классом.</span><span class="sxs-lookup"><span data-stu-id="733ae-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="733ae-130">Настроенные кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> классом.</span><span class="sxs-lookup"><span data-stu-id="733ae-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="733ae-131">Пример</span><span class="sxs-lookup"><span data-stu-id="733ae-131">Example</span></span>  
 <span data-ttu-id="733ae-132">В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="733ae-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="733ae-133">Конфигурация берется из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="733ae-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
