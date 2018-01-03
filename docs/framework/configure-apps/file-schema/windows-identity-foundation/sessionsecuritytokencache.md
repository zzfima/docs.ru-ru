---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 9f4b87d6c620a07ee831888086bdab75a689875e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="92110-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="92110-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="92110-103">Регистрирует кэша для маркеров сеанса службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="92110-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="92110-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="92110-104">\<system.identityModel></span></span>  
<span data-ttu-id="92110-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="92110-105">\<identityConfiguration></span></span>  
<span data-ttu-id="92110-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="92110-106">\<caches></span></span>  
<span data-ttu-id="92110-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="92110-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92110-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92110-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92110-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92110-109">Attributes and Elements</span></span>  
 <span data-ttu-id="92110-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="92110-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92110-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92110-111">Attributes</span></span>  
  
|<span data-ttu-id="92110-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="92110-112">Attribute</span></span>|<span data-ttu-id="92110-113">Описание</span><span class="sxs-lookup"><span data-stu-id="92110-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92110-114">type</span><span class="sxs-lookup"><span data-stu-id="92110-114">type</span></span>|<span data-ttu-id="92110-115">Тип, который является производным от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.</span><span class="sxs-lookup"><span data-stu-id="92110-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92110-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92110-116">Child Elements</span></span>  
 <span data-ttu-id="92110-117">Нет</span><span class="sxs-lookup"><span data-stu-id="92110-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92110-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92110-118">Parent Elements</span></span>  
  
|<span data-ttu-id="92110-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="92110-119">Element</span></span>|<span data-ttu-id="92110-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="92110-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92110-121">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="92110-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="92110-122">Регистрирует кэши, используемая службой или коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="92110-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="92110-123">Пример</span><span class="sxs-lookup"><span data-stu-id="92110-123">Example</span></span>  
 <span data-ttu-id="92110-124">Следующий код XML показана конфигурация пользовательского кэша для хранения токенов безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="92110-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="92110-125">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="92110-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="92110-126">Дополнительные сведения об этом образце см. в разделе [индекс образцов кода WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="92110-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92110-127">См. также</span><span class="sxs-lookup"><span data-stu-id="92110-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
