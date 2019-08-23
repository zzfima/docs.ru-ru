---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943712"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="7ec19-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="7ec19-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="7ec19-102">Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="7ec19-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="7ec19-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="7ec19-103">\<system.identityModel></span></span>  
<span data-ttu-id="7ec19-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7ec19-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7ec19-105">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="7ec19-105">\<caches></span></span>  
<span data-ttu-id="7ec19-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="7ec19-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec19-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ec19-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ec19-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7ec19-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7ec19-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7ec19-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ec19-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7ec19-110">Attributes</span></span>  
  
|<span data-ttu-id="7ec19-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7ec19-111">Attribute</span></span>|<span data-ttu-id="7ec19-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7ec19-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ec19-113">type</span><span class="sxs-lookup"><span data-stu-id="7ec19-113">type</span></span>|<span data-ttu-id="7ec19-114">Тип, производный от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.</span><span class="sxs-lookup"><span data-stu-id="7ec19-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ec19-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7ec19-115">Child Elements</span></span>  
 <span data-ttu-id="7ec19-116">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="7ec19-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ec19-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7ec19-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7ec19-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="7ec19-118">Element</span></span>|<span data-ttu-id="7ec19-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7ec19-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ec19-120">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="7ec19-120">\<caches></span></span>](caches.md)|<span data-ttu-id="7ec19-121">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="7ec19-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7ec19-122">Пример</span><span class="sxs-lookup"><span data-stu-id="7ec19-122">Example</span></span>  
 <span data-ttu-id="7ec19-123">В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="7ec19-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="7ec19-124">Конфигурация берется из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="7ec19-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="7ec19-125">Дополнительные сведения об этом образце см. в разделе [Индекс образца кода WIF](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="7ec19-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ec19-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7ec19-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
