---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793800"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="db247-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="db247-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="db247-102">Регистрирует кэш токенов сеансов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="db247-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="db247-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="db247-103">\<system.identityModel></span></span>  
<span data-ttu-id="db247-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="db247-104">\<identityConfiguration></span></span>  
<span data-ttu-id="db247-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="db247-105">\<caches></span></span>  
<span data-ttu-id="db247-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="db247-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db247-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db247-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db247-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db247-108">Attributes and Elements</span></span>  
 <span data-ttu-id="db247-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="db247-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db247-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db247-110">Attributes</span></span>  
  
|<span data-ttu-id="db247-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="db247-111">Attribute</span></span>|<span data-ttu-id="db247-112">Описание</span><span class="sxs-lookup"><span data-stu-id="db247-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db247-113">type</span><span class="sxs-lookup"><span data-stu-id="db247-113">type</span></span>|<span data-ttu-id="db247-114">Тип, который является производным от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.</span><span class="sxs-lookup"><span data-stu-id="db247-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db247-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db247-115">Child Elements</span></span>  
 <span data-ttu-id="db247-116">Нет</span><span class="sxs-lookup"><span data-stu-id="db247-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db247-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db247-117">Parent Elements</span></span>  
  
|<span data-ttu-id="db247-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="db247-118">Element</span></span>|<span data-ttu-id="db247-119">Описание</span><span class="sxs-lookup"><span data-stu-id="db247-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db247-120">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="db247-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="db247-121">Регистрирует кэши, используемые службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="db247-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="db247-122">Пример</span><span class="sxs-lookup"><span data-stu-id="db247-122">Example</span></span>  
 <span data-ttu-id="db247-123">Следующий код XML показана конфигурация пользовательского кэша для хранения сеанса маркеров безопасности (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="db247-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="db247-124">Конфигурации берется из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="db247-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="db247-125">Дополнительные сведения об этом образце см. в разделе [индекс образцов кода WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="db247-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db247-126">См. также</span><span class="sxs-lookup"><span data-stu-id="db247-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
