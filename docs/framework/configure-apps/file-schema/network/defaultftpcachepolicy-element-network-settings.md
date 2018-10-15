---
title: '&lt;defaultFtpCachePolicy&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e03fb02bd351058c1fcdedb8367d03318418a12c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316445"
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="14e71-102">&lt;defaultFtpCachePolicy&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="14e71-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="14e71-103">Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14e71-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="14e71-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="14e71-104">\<configuration></span></span>  
<span data-ttu-id="14e71-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="14e71-105">\<system.net></span></span>  
<span data-ttu-id="14e71-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="14e71-106">\<requestCaching></span></span>  
<span data-ttu-id="14e71-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="14e71-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e71-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14e71-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e71-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14e71-109">Attributes and Elements</span></span>  
 <span data-ttu-id="14e71-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14e71-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e71-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14e71-111">Attributes</span></span>  
  
|<span data-ttu-id="14e71-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="14e71-112">Attribute</span></span>|<span data-ttu-id="14e71-113">Описание</span><span class="sxs-lookup"><span data-stu-id="14e71-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="14e71-114">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="14e71-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="14e71-115">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="14e71-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="14e71-116">policyLevel атрибут</span><span class="sxs-lookup"><span data-stu-id="14e71-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="14e71-117">Значение</span><span class="sxs-lookup"><span data-stu-id="14e71-117">Value</span></span>|<span data-ttu-id="14e71-118">Описание</span><span class="sxs-lookup"><span data-stu-id="14e71-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="14e71-119">Возвращает кэшированный ресурс, если ресурс является новым, длина содержимого точна и присутствуют атрибуты content-length, модификации и истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="14e71-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="14e71-120">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="14e71-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="14e71-121">Возвращает кэшированный ресурс, если длина содержимого присутствует и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="14e71-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="14e71-122">Возвращает кэшированный ресурс, если длина содержимого и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="14e71-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="14e71-123">Возвращает кэшированный ресурс, если метка времени используется кэшированный ресурс совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, сохраняется в кэше и возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="14e71-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="14e71-124">Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="14e71-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="14e71-125">Если кэшируемый ресурс существует, она удаляется.</span><span class="sxs-lookup"><span data-stu-id="14e71-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="14e71-126">Ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="14e71-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="14e71-127">Выполняет запрос с помощью кэшированной копии ресурса, если метка времени совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, представляется вызывающему и сохраняется в кэше.</span><span class="sxs-lookup"><span data-stu-id="14e71-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14e71-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14e71-128">Child Elements</span></span>  
 <span data-ttu-id="14e71-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="14e71-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14e71-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14e71-130">Parent Elements</span></span>  
  
|<span data-ttu-id="14e71-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="14e71-131">Element</span></span>|<span data-ttu-id="14e71-132">Описание</span><span class="sxs-lookup"><span data-stu-id="14e71-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e71-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="14e71-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="14e71-134">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="14e71-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e71-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="14e71-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e71-136">Пример</span><span class="sxs-lookup"><span data-stu-id="14e71-136">Example</span></span>  
 <span data-ttu-id="14e71-137">В следующем примере показано задание политики кэширования для FTP `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="14e71-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14e71-138">См. также</span><span class="sxs-lookup"><span data-stu-id="14e71-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="14e71-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="14e71-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
