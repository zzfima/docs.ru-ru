---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285666"
---
# <a name="caches"></a><span data-ttu-id="0b1a7-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="0b1a7-101">\<caches></span></span>
<span data-ttu-id="0b1a7-102">Регистрирует кэши маркеров сеанса и обнаружения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="0b1a7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0b1a7-103">\<system.identityModel></span></span>  
<span data-ttu-id="0b1a7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0b1a7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="0b1a7-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="0b1a7-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1a7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b1a7-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b1a7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b1a7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0b1a7-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b1a7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b1a7-109">Attributes</span></span>  
 <span data-ttu-id="0b1a7-110">Нет</span><span class="sxs-lookup"><span data-stu-id="0b1a7-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b1a7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b1a7-111">Child Elements</span></span>  
  
|<span data-ttu-id="0b1a7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b1a7-112">Element</span></span>|<span data-ttu-id="0b1a7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0b1a7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b1a7-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="0b1a7-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="0b1a7-115">Регистрирует кэш токенов сеансов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="0b1a7-116">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="0b1a7-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="0b1a7-117">Регистрирует кэш повторного использования токенов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b1a7-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b1a7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0b1a7-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b1a7-119">Element</span></span>|<span data-ttu-id="0b1a7-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b1a7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b1a7-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0b1a7-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="0b1a7-122">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="0b1a7-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="0b1a7-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="0b1a7-124">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b1a7-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b1a7-125">Remarks</span></span>  
 <span data-ttu-id="0b1a7-126">Объект `<caches>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="0b1a7-127">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="0b1a7-128">`<caches>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> класса.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="0b1a7-129">Настраиваемые кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> класса.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b1a7-130">Пример</span><span class="sxs-lookup"><span data-stu-id="0b1a7-130">Example</span></span>  
 <span data-ttu-id="0b1a7-131">Следующий код XML показана конфигурация пользовательского кэша для хранения сеанса маркеров безопасности (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="0b1a7-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="0b1a7-132">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="0b1a7-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
