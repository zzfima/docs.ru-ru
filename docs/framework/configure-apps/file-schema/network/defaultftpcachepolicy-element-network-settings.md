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
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088427"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="7c9a5-102">Элемент \<Дефаултфтпкачеполици > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="7c9a5-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="7c9a5-103">Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

<span data-ttu-id="7c9a5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7c9a5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7c9a5-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c9a5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="7c9a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<элемент requestcaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c9a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>\
<span data-ttu-id="7c9a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<дефаултфтпкачеполици >**</span><span class="sxs-lookup"><span data-stu-id="7c9a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7c9a5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c9a5-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c9a5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7c9a5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7c9a5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c9a5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7c9a5-111">Attributes</span></span>  
  
|<span data-ttu-id="7c9a5-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7c9a5-112">Attribute</span></span>|<span data-ttu-id="7c9a5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7c9a5-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="7c9a5-114">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="7c9a5-115">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="7c9a5-116">Атрибут Полицилевел</span><span class="sxs-lookup"><span data-stu-id="7c9a5-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="7c9a5-117">значения</span><span class="sxs-lookup"><span data-stu-id="7c9a5-117">Value</span></span>|<span data-ttu-id="7c9a5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7c9a5-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="7c9a5-119">Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="7c9a5-120">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="7c9a5-121">Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="7c9a5-122">Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="7c9a5-123">Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="7c9a5-124">Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="7c9a5-125">Если кэшированный ресурс существует, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="7c9a5-126">Ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="7c9a5-127">Удовлетворяет запросу, используя кэшированную копию ресурса, если отметка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленного вызывающему объекту, и сохраняется в кэше.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c9a5-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7c9a5-128">Child Elements</span></span>  
 <span data-ttu-id="7c9a5-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c9a5-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7c9a5-130">Parent Elements</span></span>  
  
|<span data-ttu-id="7c9a5-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="7c9a5-131">Element</span></span>|<span data-ttu-id="7c9a5-132">Описание</span><span class="sxs-lookup"><span data-stu-id="7c9a5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c9a5-133">Элемент requestcaching</span><span class="sxs-lookup"><span data-stu-id="7c9a5-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="7c9a5-134">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c9a5-135">Заметки</span><span class="sxs-lookup"><span data-stu-id="7c9a5-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c9a5-136">Пример</span><span class="sxs-lookup"><span data-stu-id="7c9a5-136">Example</span></span>  
 <span data-ttu-id="7c9a5-137">В следующем примере показано, как указать политику кэширования FTP для `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="7c9a5-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c9a5-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7c9a5-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="7c9a5-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="7c9a5-139">Network Settings Schema</span></span>](index.md)
