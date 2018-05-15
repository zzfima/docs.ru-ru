---
title: '&lt;defaultFtpCachePolicy&gt; элемент (параметры сети)'
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
manager: markl
ms.openlocfilehash: e4ea16c925114d4ad4054af5f340c764ed6fe4fd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="f291f-102">&lt;defaultFtpCachePolicy&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f291f-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="f291f-103">Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f291f-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="f291f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f291f-104">\<configuration></span></span>  
<span data-ttu-id="f291f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="f291f-105">\<system.net></span></span>  
<span data-ttu-id="f291f-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="f291f-106">\<requestCaching></span></span>  
<span data-ttu-id="f291f-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="f291f-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f291f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f291f-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f291f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f291f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f291f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f291f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f291f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f291f-111">Attributes</span></span>  
  
|<span data-ttu-id="f291f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f291f-112">Attribute</span></span>|<span data-ttu-id="f291f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f291f-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="f291f-114">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="f291f-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="f291f-115">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="f291f-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="f291f-116">Сохранить атрибут</span><span class="sxs-lookup"><span data-stu-id="f291f-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="f291f-117">Значение</span><span class="sxs-lookup"><span data-stu-id="f291f-117">Value</span></span>|<span data-ttu-id="f291f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f291f-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="f291f-119">Возвращает кэшируемый ресурс, если ресурс является новым, длина содержимого точна и присутствуют истечения срока, изменения и атрибуты content-length.</span><span class="sxs-lookup"><span data-stu-id="f291f-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="f291f-120">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="f291f-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="f291f-121">Возвращает кэшируемый ресурс, если длина содержимого представлена и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="f291f-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="f291f-122">Возвращает кэшируемый ресурс, если длина содержимого предоставляется и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="f291f-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f291f-123">Возвращает кэшируемый ресурс, если метка времени кэшируемого ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="f291f-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="f291f-124">Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f291f-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="f291f-125">Если кэшируемый ресурс существует, она удаляется.</span><span class="sxs-lookup"><span data-stu-id="f291f-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="f291f-126">Ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f291f-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f291f-127">Выполняет запрос, используя кэшированную копию ресурса, если метка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представляются в вызывающем объекте и хранится в кэше.</span><span class="sxs-lookup"><span data-stu-id="f291f-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f291f-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f291f-128">Child Elements</span></span>  
 <span data-ttu-id="f291f-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f291f-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f291f-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f291f-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f291f-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="f291f-131">Element</span></span>|<span data-ttu-id="f291f-132">Описание</span><span class="sxs-lookup"><span data-stu-id="f291f-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f291f-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="f291f-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="f291f-134">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="f291f-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f291f-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="f291f-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="f291f-136">Пример</span><span class="sxs-lookup"><span data-stu-id="f291f-136">Example</span></span>  
 <span data-ttu-id="f291f-137">Приведенный ниже показано, как задать политику кэширования FTP `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="f291f-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f291f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f291f-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="f291f-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f291f-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
