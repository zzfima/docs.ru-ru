---
title: Элемент <defaultFtpCachePolicy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 36d174beea58ff96674bd873bfbcb8be89591669
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132539"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="e1c11-102">\<defaultFtpCachePolicy > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="e1c11-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="e1c11-103">Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1c11-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="e1c11-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e1c11-104">\<configuration></span></span>  
<span data-ttu-id="e1c11-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e1c11-105">\<system.net></span></span>  
<span data-ttu-id="e1c11-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="e1c11-106">\<requestCaching></span></span>  
<span data-ttu-id="e1c11-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="e1c11-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c11-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1c11-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1c11-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1c11-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e1c11-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1c11-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1c11-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1c11-111">Attributes</span></span>  
  
|<span data-ttu-id="e1c11-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1c11-112">Attribute</span></span>|<span data-ttu-id="e1c11-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e1c11-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="e1c11-114">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="e1c11-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="e1c11-115">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="e1c11-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="e1c11-116">policyLevel атрибут</span><span class="sxs-lookup"><span data-stu-id="e1c11-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="e1c11-117">Значение</span><span class="sxs-lookup"><span data-stu-id="e1c11-117">Value</span></span>|<span data-ttu-id="e1c11-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e1c11-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="e1c11-119">Возвращает кэшированный ресурс, если ресурс является новым, длина содержимого точна и присутствуют атрибуты content-length, модификации и истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="e1c11-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="e1c11-120">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="e1c11-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="e1c11-121">Возвращает кэшированный ресурс, если длина содержимого присутствует и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="e1c11-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="e1c11-122">Возвращает кэшированный ресурс, если длина содержимого и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="e1c11-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="e1c11-123">Возвращает кэшированный ресурс, если метка времени используется кэшированный ресурс совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, сохраняется в кэше и возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="e1c11-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="e1c11-124">Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="e1c11-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="e1c11-125">Если кэшируемый ресурс существует, она удаляется.</span><span class="sxs-lookup"><span data-stu-id="e1c11-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="e1c11-126">Ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="e1c11-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="e1c11-127">Выполняет запрос с помощью кэшированной копии ресурса, если метка времени совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, представляется вызывающему и сохраняется в кэше.</span><span class="sxs-lookup"><span data-stu-id="e1c11-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1c11-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1c11-128">Child Elements</span></span>  
 <span data-ttu-id="e1c11-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1c11-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1c11-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1c11-130">Parent Elements</span></span>  
  
|<span data-ttu-id="e1c11-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1c11-131">Element</span></span>|<span data-ttu-id="e1c11-132">Описание</span><span class="sxs-lookup"><span data-stu-id="e1c11-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1c11-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="e1c11-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="e1c11-134">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="e1c11-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1c11-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1c11-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1c11-136">Пример</span><span class="sxs-lookup"><span data-stu-id="e1c11-136">Example</span></span>  
 <span data-ttu-id="e1c11-137">В следующем примере показано задание политики кэширования для FTP `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="e1c11-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1c11-138">См. также</span><span class="sxs-lookup"><span data-stu-id="e1c11-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="e1c11-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e1c11-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
