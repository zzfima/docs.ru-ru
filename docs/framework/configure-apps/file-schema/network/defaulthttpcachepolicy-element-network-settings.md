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
ms.openlocfilehash: f3b029e8b931e976bee85c98dd926e020c5b8743
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698268"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="47648-102">Элемент > @no__t 0defaultHttpCachePolicy (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="47648-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="47648-103">Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47648-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="47648-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="47648-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="47648-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="47648-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="47648-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<requestCaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="47648-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="47648-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<defaultHttpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="47648-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47648-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47648-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47648-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47648-109">Attributes and Elements</span></span>  
 <span data-ttu-id="47648-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47648-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47648-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47648-111">Attributes</span></span>  
  
|<span data-ttu-id="47648-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="47648-112">Attribute</span></span>|<span data-ttu-id="47648-113">Описание</span><span class="sxs-lookup"><span data-stu-id="47648-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="47648-114">Указывает максимальный интервал времени, по истечении которого кэшированный объект помечается как истекший.</span><span class="sxs-lookup"><span data-stu-id="47648-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="47648-115">Указывает максимальное время после истечения срока действия вычисленного объекта до пометки времени, когда кэшированный объект помечается как истекший.</span><span class="sxs-lookup"><span data-stu-id="47648-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="47648-116">Указывает минимальное время, в течение которого кэшированный объект будет считаться актуальным.</span><span class="sxs-lookup"><span data-stu-id="47648-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="47648-117">Указывает, является ли политика кэширования автоматическим, или же кэш будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="47648-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="47648-118">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="47648-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47648-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47648-119">Child Elements</span></span>  
 <span data-ttu-id="47648-120">None</span><span class="sxs-lookup"><span data-stu-id="47648-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47648-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47648-121">Parent Elements</span></span>  
  
|<span data-ttu-id="47648-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="47648-122">Element</span></span>|<span data-ttu-id="47648-123">Описание</span><span class="sxs-lookup"><span data-stu-id="47648-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47648-124">Элемент requestcaching</span><span class="sxs-lookup"><span data-stu-id="47648-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="47648-125">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="47648-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47648-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="47648-126">Remarks</span></span>  
 <span data-ttu-id="47648-127">Значением атрибута `policyLevel` может быть `BypassCache` или `Default`.</span><span class="sxs-lookup"><span data-stu-id="47648-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="47648-128">Значения для элементов `maximumAge`, `maximumStale` и `minimumFresh` являются либо явным интервалом времени, форматом *d*. *чч*:*мм*:*СС* (дни, часы, минуты и секунды) или константы `minValue` или `maxValue`, в зависимости от ситуации.</span><span class="sxs-lookup"><span data-stu-id="47648-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="47648-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="47648-129">Configuration Files</span></span>  
 <span data-ttu-id="47648-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="47648-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="47648-131">Пример</span><span class="sxs-lookup"><span data-stu-id="47648-131">Example</span></span>  
 <span data-ttu-id="47648-132">В следующем примере показано, как задать минимальное новое время в 6 часов, максимальное время существования, равное двум дням, и максимальное устаревшее время, равное четырем часам.</span><span class="sxs-lookup"><span data-stu-id="47648-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="47648-133">См. также</span><span class="sxs-lookup"><span data-stu-id="47648-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="47648-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="47648-134">Network Settings Schema</span></span>](index.md)
