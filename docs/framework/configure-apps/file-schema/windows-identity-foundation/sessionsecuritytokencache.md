---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0b0d3c01a81f110f79f64d75aa2ab2ff2873fedd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755049"
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="fc0c4-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="fc0c4-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="fc0c4-103">Регистрирует кэша для маркеров сеанса службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc0c4-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="fc0c4-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="fc0c4-104">\<system.identityModel></span></span>  
<span data-ttu-id="fc0c4-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fc0c4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="fc0c4-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="fc0c4-106">\<caches></span></span>  
<span data-ttu-id="fc0c4-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="fc0c4-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc0c4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc0c4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc0c4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc0c4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fc0c4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc0c4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc0c4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc0c4-111">Attributes</span></span>  
  
|<span data-ttu-id="fc0c4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fc0c4-112">Attribute</span></span>|<span data-ttu-id="fc0c4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fc0c4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc0c4-114">type</span><span class="sxs-lookup"><span data-stu-id="fc0c4-114">type</span></span>|<span data-ttu-id="fc0c4-115">Тип, который является производным от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.</span><span class="sxs-lookup"><span data-stu-id="fc0c4-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc0c4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc0c4-116">Child Elements</span></span>  
 <span data-ttu-id="fc0c4-117">Нет</span><span class="sxs-lookup"><span data-stu-id="fc0c4-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc0c4-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc0c4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fc0c4-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc0c4-119">Element</span></span>|<span data-ttu-id="fc0c4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fc0c4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc0c4-121">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="fc0c4-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="fc0c4-122">Регистрирует кэши, используемая службой или коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc0c4-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc0c4-123">Пример</span><span class="sxs-lookup"><span data-stu-id="fc0c4-123">Example</span></span>  
 <span data-ttu-id="fc0c4-124">Следующий код XML показана конфигурация пользовательского кэша для хранения токенов безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="fc0c4-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="fc0c4-125">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="fc0c4-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="fc0c4-126">Дополнительные сведения об этом образце см. в разделе [индекс образцов кода WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="fc0c4-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc0c4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fc0c4-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
