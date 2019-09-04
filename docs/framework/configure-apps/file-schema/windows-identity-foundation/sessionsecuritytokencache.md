---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251834"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="56ac6-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="56ac6-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="56ac6-102">Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="56ac6-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="56ac6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56ac6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56ac6-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="56ac6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="56ac6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="56ac6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="56ac6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> кэшей**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="56ac6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="56ac6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessionSecurityTokenCache >**</span><span class="sxs-lookup"><span data-stu-id="56ac6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56ac6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56ac6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56ac6-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56ac6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56ac6-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56ac6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56ac6-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56ac6-111">Attributes</span></span>  
  
|<span data-ttu-id="56ac6-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="56ac6-112">Attribute</span></span>|<span data-ttu-id="56ac6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="56ac6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56ac6-114">type</span><span class="sxs-lookup"><span data-stu-id="56ac6-114">type</span></span>|<span data-ttu-id="56ac6-115">Тип, производный от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.</span><span class="sxs-lookup"><span data-stu-id="56ac6-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56ac6-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56ac6-116">Child Elements</span></span>  
 <span data-ttu-id="56ac6-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="56ac6-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56ac6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56ac6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="56ac6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="56ac6-119">Element</span></span>|<span data-ttu-id="56ac6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="56ac6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56ac6-121">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="56ac6-121">\<caches></span></span>](caches.md)|<span data-ttu-id="56ac6-122">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="56ac6-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="56ac6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="56ac6-123">Example</span></span>  
 <span data-ttu-id="56ac6-124">В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="56ac6-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="56ac6-125">Конфигурация берется из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="56ac6-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="56ac6-126">Дополнительные сведения об этом образце см. в разделе [Индекс образца кода WIF](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="56ac6-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56ac6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="56ac6-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
