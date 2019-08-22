---
title: Элемент <defaultHttpCachePolicy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 1dd31884a072d16ed004c0b49be61e8cee399787
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664156"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="78aa4-102">\<Элемент > Дефаулсттпкачеполици (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="78aa4-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="78aa4-103">Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="78aa4-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="78aa4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="78aa4-104">\<configuration></span></span>  
<span data-ttu-id="78aa4-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="78aa4-105">\<system.net></span></span>  
<span data-ttu-id="78aa4-106">\<Элемент requestcaching ></span><span class="sxs-lookup"><span data-stu-id="78aa4-106">\<requestCaching></span></span>  
<span data-ttu-id="78aa4-107">\<defaultHttpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="78aa4-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78aa4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78aa4-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78aa4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78aa4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="78aa4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78aa4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78aa4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78aa4-111">Attributes</span></span>  
  
|<span data-ttu-id="78aa4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="78aa4-112">Attribute</span></span>|<span data-ttu-id="78aa4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="78aa4-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="78aa4-114">Указывает максимальный интервал времени, по истечении которого кэшированный объект помечается как истекший.</span><span class="sxs-lookup"><span data-stu-id="78aa4-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="78aa4-115">Указывает максимальное время после истечения срока действия вычисленного объекта до пометки времени, когда кэшированный объект помечается как истекший.</span><span class="sxs-lookup"><span data-stu-id="78aa4-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="78aa4-116">Указывает минимальное время, в течение которого кэшированный объект будет считаться актуальным.</span><span class="sxs-lookup"><span data-stu-id="78aa4-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="78aa4-117">Указывает, является ли политика кэширования автоматическим, или же кэш будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="78aa4-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="78aa4-118">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="78aa4-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78aa4-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78aa4-119">Child Elements</span></span>  
 <span data-ttu-id="78aa4-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="78aa4-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78aa4-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78aa4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="78aa4-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="78aa4-122">Element</span></span>|<span data-ttu-id="78aa4-123">Описание</span><span class="sxs-lookup"><span data-stu-id="78aa4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78aa4-124">Элемент requestcaching</span><span class="sxs-lookup"><span data-stu-id="78aa4-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="78aa4-125">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="78aa4-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78aa4-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="78aa4-126">Remarks</span></span>  
 <span data-ttu-id="78aa4-127">Значение `policyLevel` атрибута может быть `BypassCache` или `Default`.</span><span class="sxs-lookup"><span data-stu-id="78aa4-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="78aa4-128">Значения для `maximumAge`элементов, `maximumStale`и `minimumFresh` являются либо явным временным интервалом с форматом *d*. *чч*:*мм*:*СС* (дни, часы, минуты и секунды), константы `minValue` или `maxValue`(при необходимости).</span><span class="sxs-lookup"><span data-stu-id="78aa4-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="78aa4-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="78aa4-129">Configuration Files</span></span>  
 <span data-ttu-id="78aa4-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="78aa4-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78aa4-131">Пример</span><span class="sxs-lookup"><span data-stu-id="78aa4-131">Example</span></span>  
 <span data-ttu-id="78aa4-132">В следующем примере показано, как задать минимальное новое время в 6 часов, максимальное время существования, равное двум дням, и максимальное устаревшее время, равное четырем часам.</span><span class="sxs-lookup"><span data-stu-id="78aa4-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="78aa4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="78aa4-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="78aa4-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="78aa4-134">Network Settings Schema</span></span>](index.md)
