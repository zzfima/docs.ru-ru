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
ms.openlocfilehash: 7ff44f0251936d51b4e396c37c53322efa110227
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659420"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="ebb58-102">\<Элемент > Дефаултфтпкачеполици (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ebb58-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="ebb58-103">Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ebb58-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="ebb58-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ebb58-104">\<configuration></span></span>  
<span data-ttu-id="ebb58-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="ebb58-105">\<system.net></span></span>  
<span data-ttu-id="ebb58-106">\<Элемент requestcaching ></span><span class="sxs-lookup"><span data-stu-id="ebb58-106">\<requestCaching></span></span>  
<span data-ttu-id="ebb58-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="ebb58-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb58-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebb58-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebb58-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ebb58-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ebb58-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ebb58-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebb58-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ebb58-111">Attributes</span></span>  
  
|<span data-ttu-id="ebb58-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ebb58-112">Attribute</span></span>|<span data-ttu-id="ebb58-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ebb58-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="ebb58-114">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="ebb58-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="ebb58-115">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="ebb58-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="ebb58-116">Атрибут Полицилевел</span><span class="sxs-lookup"><span data-stu-id="ebb58-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="ebb58-117">Значение</span><span class="sxs-lookup"><span data-stu-id="ebb58-117">Value</span></span>|<span data-ttu-id="ebb58-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ebb58-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="ebb58-119">Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.</span><span class="sxs-lookup"><span data-stu-id="ebb58-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="ebb58-120">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="ebb58-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="ebb58-121">Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="ebb58-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="ebb58-122">Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="ebb58-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="ebb58-123">Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="ebb58-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="ebb58-124">Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="ebb58-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="ebb58-125">Если кэшированный ресурс существует, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="ebb58-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="ebb58-126">Ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="ebb58-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="ebb58-127">Удовлетворяет запросу, используя кэшированную копию ресурса, если отметка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленного вызывающему объекту, и сохраняется в кэше.</span><span class="sxs-lookup"><span data-stu-id="ebb58-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebb58-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ebb58-128">Child Elements</span></span>  
 <span data-ttu-id="ebb58-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="ebb58-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebb58-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ebb58-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ebb58-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="ebb58-131">Element</span></span>|<span data-ttu-id="ebb58-132">Описание</span><span class="sxs-lookup"><span data-stu-id="ebb58-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebb58-133">Элемент requestcaching</span><span class="sxs-lookup"><span data-stu-id="ebb58-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="ebb58-134">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="ebb58-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebb58-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebb58-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb58-136">Пример</span><span class="sxs-lookup"><span data-stu-id="ebb58-136">Example</span></span>  
 <span data-ttu-id="ebb58-137">В следующем примере показано, как задать политику кэширования FTP для `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="ebb58-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ebb58-138">См. также</span><span class="sxs-lookup"><span data-stu-id="ebb58-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="ebb58-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ebb58-139">Network Settings Schema</span></span>](index.md)
