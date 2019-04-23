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
ms.openlocfilehash: 20d9b92ca2bbffd6b98b8641e5cef5e567cb84cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177387"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="769b1-102">\<defaultHttpCachePolicy > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="769b1-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="769b1-103">Описывает указывает, активна ли HTTP-кэширования и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="769b1-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="769b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="769b1-104">\<configuration></span></span>  
<span data-ttu-id="769b1-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="769b1-105">\<system.net></span></span>  
<span data-ttu-id="769b1-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="769b1-106">\<requestCaching></span></span>  
<span data-ttu-id="769b1-107">\<defaultHttpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="769b1-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769b1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="769b1-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="769b1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="769b1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="769b1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="769b1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="769b1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="769b1-111">Attributes</span></span>  
  
|<span data-ttu-id="769b1-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="769b1-112">Attribute</span></span>|<span data-ttu-id="769b1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="769b1-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="769b1-114">Указывает максимальный интервал времени, кэшированный объект будет помечена как просроченная.</span><span class="sxs-lookup"><span data-stu-id="769b1-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="769b1-115">Указывает максимальное время после запрограммированного обновления срока действия кэшированного объекта будет помечена как просроченная.</span><span class="sxs-lookup"><span data-stu-id="769b1-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="769b1-116">Указывает минимальное время актуальности кэшированного объекта.</span><span class="sxs-lookup"><span data-stu-id="769b1-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="769b1-117">Указывает, является ли политика кэширования автоматической или кэш пропускается.</span><span class="sxs-lookup"><span data-stu-id="769b1-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="769b1-118">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="769b1-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="769b1-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="769b1-119">Child Elements</span></span>  
 <span data-ttu-id="769b1-120">Нет</span><span class="sxs-lookup"><span data-stu-id="769b1-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="769b1-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="769b1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="769b1-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="769b1-122">Element</span></span>|<span data-ttu-id="769b1-123">Описание</span><span class="sxs-lookup"><span data-stu-id="769b1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="769b1-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="769b1-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="769b1-125">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="769b1-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="769b1-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="769b1-126">Remarks</span></span>  
 <span data-ttu-id="769b1-127">Значение для `policyLevel` атрибут является либо `BypassCache` или `Default`.</span><span class="sxs-lookup"><span data-stu-id="769b1-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="769b1-128">Значения для `maximumAge`, `maximumStale`, и `minimumFresh` элементы, либо как явные временные интервалы в формате *d*. *hh*:*мм*:*ss* (дни, часы, минуты и секунды), либо как константы `minValue` или `maxValue`, соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="769b1-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="769b1-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="769b1-129">Configuration Files</span></span>  
 <span data-ttu-id="769b1-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="769b1-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="769b1-131">Пример</span><span class="sxs-lookup"><span data-stu-id="769b1-131">Example</span></span>  
 <span data-ttu-id="769b1-132">Приведенный ниже показано, как указать минимальное время актуальности шести часов, максимальный срок жизни за два дня и максимальное время устаревания четыре часа.</span><span class="sxs-lookup"><span data-stu-id="769b1-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="769b1-133">См. также</span><span class="sxs-lookup"><span data-stu-id="769b1-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="769b1-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="769b1-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
