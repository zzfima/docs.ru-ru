---
title: '&lt;requestCaching&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9c0c8d80182931f9ac14e687a337b7be55a5a9a5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743437"
---
# <a name="ltrequestcachinggt-element-network-settings"></a><span data-ttu-id="b2831-102">&lt;requestCaching&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b2831-102">&lt;requestCaching&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b2831-103">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="b2831-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="b2831-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2831-104">\<configuration></span></span>  
<span data-ttu-id="b2831-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="b2831-105">\<system.net></span></span>  
<span data-ttu-id="b2831-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="b2831-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2831-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2831-107">Syntax</span></span>  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2831-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2831-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b2831-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2831-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2831-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2831-110">Attributes</span></span>  
  
|<span data-ttu-id="b2831-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b2831-111">Attribute</span></span>|<span data-ttu-id="b2831-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b2831-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="b2831-113">Указывает, предоставляет ли кэш изоляцию сведений различных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2831-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="b2831-114">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="b2831-114">The default value is `true`.</span></span> <span data-ttu-id="b2831-115">Это значение должно быть `false` для приложений среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="b2831-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="b2831-116">Указывает, что кэширование отключено для всех веб-откликов и не может быть переопределено программным способом.</span><span class="sxs-lookup"><span data-stu-id="b2831-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="b2831-117">Одно из значений в перечислении <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="b2831-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="b2831-118">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="b2831-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="b2831-119">Указывает время по умолчанию, после которого содержимое помечается как устаревшая.</span><span class="sxs-lookup"><span data-stu-id="b2831-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="b2831-120">Сохранить атрибут</span><span class="sxs-lookup"><span data-stu-id="b2831-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="b2831-121">Значение</span><span class="sxs-lookup"><span data-stu-id="b2831-121">Value</span></span>|<span data-ttu-id="b2831-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b2831-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="b2831-123">Возвращает кэшируемый ресурс, если ресурс является новым, длина содержимого точна и присутствуют истечения срока, изменения и атрибуты content-length.</span><span class="sxs-lookup"><span data-stu-id="b2831-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="b2831-124">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="b2831-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="b2831-125">Возвращает кэшируемый ресурс, если длина содержимого представлена и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="b2831-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="b2831-126">Возвращает кэшируемый ресурс, если длина содержимого предоставляется и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="b2831-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b2831-127">Возвращает кэшируемый ресурс, если метка времени кэшируемого ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранящиеся в кэше и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="b2831-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="b2831-128">Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="b2831-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="b2831-129">Если кэшируемый ресурс существует, она удаляется.</span><span class="sxs-lookup"><span data-stu-id="b2831-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="b2831-130">Ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="b2831-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b2831-131">Выполняет запрос, используя кэшированную копию ресурса, если метка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленных вызывающему объекту и хранится в кэше,</span><span class="sxs-lookup"><span data-stu-id="b2831-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2831-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2831-132">Child Elements</span></span>  
  
|<span data-ttu-id="b2831-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2831-133">Element</span></span>|<span data-ttu-id="b2831-134">Описание</span><span class="sxs-lookup"><span data-stu-id="b2831-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2831-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="b2831-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="b2831-136">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b2831-136">Optional element.</span></span><br /><br /> <span data-ttu-id="b2831-137">Описывает указывает, активна ли функция HTTP-кэширования и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2831-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="b2831-138">\<defaultFtpCachePolicy > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="b2831-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="b2831-139">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b2831-139">Optional element.</span></span><br /><br /> <span data-ttu-id="b2831-140">Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2831-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2831-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2831-141">Parent Elements</span></span>  
  
|<span data-ttu-id="b2831-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2831-142">Element</span></span>|<span data-ttu-id="b2831-143">Описание</span><span class="sxs-lookup"><span data-stu-id="b2831-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2831-144">System.NET</span><span class="sxs-lookup"><span data-stu-id="b2831-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b2831-145">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b2831-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2831-146">Пример</span><span class="sxs-lookup"><span data-stu-id="b2831-146">Example</span></span>  
 <span data-ttu-id="b2831-147">В следующем примере показано, как отключить кэширование всех.</span><span class="sxs-lookup"><span data-stu-id="b2831-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2831-148">См. также</span><span class="sxs-lookup"><span data-stu-id="b2831-148">See Also</span></span>  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [<span data-ttu-id="b2831-149">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b2831-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
