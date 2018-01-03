---
title: "политики кэша на основе времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time-based cache policies
- cache synchronization date policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- time, cached resources
- maximum age policy
- synchronization, cache
- staleness of cached resources
- default time-based cache policy
- maximum staleness policy
- content cache policies
- expired content
- minimum freshness policy
- age of cached resources
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f712f223ef5787e50ef6a0c26949ff99c13dee33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="time-based-cache-policies"></a><span data-ttu-id="6c4bc-102">политики кэша на основе времени</span><span class="sxs-lookup"><span data-stu-id="6c4bc-102">Time-Based Cache Policies</span></span>
<span data-ttu-id="6c4bc-103">Политика кэша на основе времени определяет актуальность записей в кэше на основе времени извлечения ресурса, заголовков, возвращаемых вместе с ним, и текущего времени.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-103">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, the headers returned with the resource, and the current time.</span></span> <span data-ttu-id="6c4bc-104">При задании политики кэша на основе времени можно использовать политику на основе времени <xref:System.Net.Cache.HttpRequestCacheLevel.Default> или создать настраиваемую политику на основе времени.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-104">When setting a time-based cache policy, you can either use the <xref:System.Net.Cache.HttpRequestCacheLevel.Default> time-based policy or create a customized time-based policy.</span></span> <span data-ttu-id="6c4bc-105">При использовании политики на основе времени по умолчанию для ресурсов, полученных по протоколу HTTP, способ выполнения кэширования определяется заголовками, включенными в кэшированный ответ, и поведением, описанным в разделах 13 и 14 документа RFC 2616, который доступен на сайте [http://www.ietf.org](http://www.ietf.org/). Пример кода, в котором демонстрируется задание политики на основе времени по умолчанию для ресурсов HTTP, см. в разделе [Практическое руководство. Установка политики кэша для приложения на основе времени по умолчанию](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="6c4bc-105">When using the default time-based policy for resources obtained using Hypertext Transfer Protocol (HTTP), the exact cache behavior is determined by the headers included in the cached response and by the behaviors specified in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). For a code example that demonstrates setting the default time-based policy for HTTP resources, see [How to: Set the Default Time-Based Cache Policy for an Application](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).</span></span> <span data-ttu-id="6c4bc-106">Примеры кода, демонстрирующие создание и использование политик кэша, см. в разделе [Настройка кэширования в сетевых приложениях](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).</span><span class="sxs-lookup"><span data-stu-id="6c4bc-106">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a><span data-ttu-id="6c4bc-107">Критерии для определения актуальности записей в кэше</span><span class="sxs-lookup"><span data-stu-id="6c4bc-107">Criteria to Determine Freshness of Cached Entries</span></span>  
 <span data-ttu-id="6c4bc-108">Для настройки политики кэша на основе времени можно настроить один или несколько из следующих критериев актуальности записей в кэше:</span><span class="sxs-lookup"><span data-stu-id="6c4bc-108">To customize a time-based cache policy, you can specify that one or more of the following criteria be used to determine the freshness of cached entries:</span></span>  
  
-   <span data-ttu-id="6c4bc-109">максимальный срок действия;</span><span class="sxs-lookup"><span data-stu-id="6c4bc-109">Maximum age</span></span>  
  
-   <span data-ttu-id="6c4bc-110">максимальный возраст;</span><span class="sxs-lookup"><span data-stu-id="6c4bc-110">Maximum staleness</span></span>  
  
-   <span data-ttu-id="6c4bc-111">минимальная актуальность;</span><span class="sxs-lookup"><span data-stu-id="6c4bc-111">Minimum freshness</span></span>  
  
-   <span data-ttu-id="6c4bc-112">дата синхронизации кэша.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-112">Cache synchronization date</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c4bc-113">Использование кэша политики на основе времени по умолчанию не следует путать с заданием политики кэша по умолчанию для приложения.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-113">Using the default time-based cache policy should not be confused with setting a default cache policy for your application.</span></span> <span data-ttu-id="6c4bc-114">Политика на основе времени по умолчанию — это конкретная политика, которую можно использовать на уровне приложения или запросов.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-114">The default time-based policy is a specific policy that can be used at the request or application level.</span></span> <span data-ttu-id="6c4bc-115">Политика кэша по умолчанию для приложения — это политика (на основе расположения или времени), которая вступает в силу, если политика для запроса не задана.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-115">The default cache policy for your application is a policy (location-based or time-based) that takes effect when no policy is set on a request.</span></span> <span data-ttu-id="6c4bc-116">Подробные сведения о задании политики кэша по умолчанию для приложения см. в разделе <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-116">For details on setting a default cache policy for your application, see <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.</span></span>  
  
### <a name="maximum-age"></a><span data-ttu-id="6c4bc-117">Максимальный срок действия</span><span class="sxs-lookup"><span data-stu-id="6c4bc-117">Maximum Age</span></span>  
 <span data-ttu-id="6c4bc-118">Критерий максимального срока действия определяет то, как долго может использоваться кэшированная копия ресурса.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-118">The maximum age policy criterion specifies the amount of time a cached copy of a resource can be used.</span></span> <span data-ttu-id="6c4bc-119">Если указанный срок действия кэшированной копии ресурса истек, ресурс необходимо проверить повторно, сравнив его с содержимым на сервере.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-119">If the cached copy of the resource is older than the amount of time specified, the resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="6c4bc-120">Если использование ресурса по истечении срока действия разрешено, этот критерий не учитывается, если только также не задано значение максимального возраста.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-120">If the maximum age would allow the resource to be used after it expires, this criteria is not honored unless a maximum staleness value is also specified.</span></span>  
  
### <a name="maximum-staleness"></a><span data-ttu-id="6c4bc-121">Максимальный возраст</span><span class="sxs-lookup"><span data-stu-id="6c4bc-121">Maximum Staleness</span></span>  
 <span data-ttu-id="6c4bc-122">Критерий максимального возраста определяет то, как долго может использоваться кэшированная копия ресурса после истечения срока ее действия.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-122">The maximum staleness policy criterion specifies the length of time after content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="6c4bc-123">Это единственный критерий политики кэша, который разрешает использовать ресурсы с истекшим сроком действия.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-123">This is the only cache policy criterion that permits resources to be used after they have expired.</span></span>  
  
### <a name="minimum-freshness"></a><span data-ttu-id="6c4bc-124">Минимальная актуальность</span><span class="sxs-lookup"><span data-stu-id="6c4bc-124">Minimum Freshness</span></span>  
 <span data-ttu-id="6c4bc-125">Критерий минимальной актуальности определяет период времени до истечения срока действия, до которого может использоваться кэшированная копия ресурса.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-125">The minimum freshness policy criterion specifies the length of time before content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="6c4bc-126">Вследствие этой политики срок действия записи в кэше истекает до назначенного времени. Таким образом, параметры минимальной актуальности и максимального возраста являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-126">This policy has the effect of causing a cache entry to expire before its expiration date; therefore, the minimum freshness and maximum staleness settings are mutually exclusive.</span></span>  
  
## <a name="cache-synchronization-date"></a><span data-ttu-id="6c4bc-127">Дата синхронизации кэша</span><span class="sxs-lookup"><span data-stu-id="6c4bc-127">Cache Synchronization Date</span></span>  
 <span data-ttu-id="6c4bc-128">Критерий даты синхронизации кэша определяет то, когда необходимо повторно проверить кэшированную копию ресурса, сравнив ее с содержимым на сервере.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-128">The cache synchronization date policy criterion determines when a cached copy of a resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="6c4bc-129">Если содержимое изменилось с момента кэширования объекта, он извлекается с сервера, сохраняется в кэше и возвращается приложению.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-129">If the content has changed since the item was cached, it is retrieved from the server, stored in the cache, and returned to the application.</span></span> <span data-ttu-id="6c4bc-130">Если содержимое не изменилось, его метка времени обновляется и приложение получает содержимое из кэша.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-130">If the content has not changed, its timestamp is updated and the application gets the cached content.</span></span>  
  
 <span data-ttu-id="6c4bc-131">С помощью даты синхронизации кэша можно указать абсолютную дату, когда кэшированное содержимое должно быть проверено повторно.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-131">The cache synchronization date allows you to specify an absolute date when cached contents must be revalidated.</span></span> <span data-ttu-id="6c4bc-132">Если актуальная запись в кэше была в последний раз повторно проверена до даты синхронизации кэша, повторная проверка все же выполняется.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-132">If a fresh cache entry was last revalidated prior to the cache synchronization date, revalidation with the server still occurs.</span></span> <span data-ttu-id="6c4bc-133">Если запись в кэше была повторно проверена после даты синхронизации кэша и нет дополнительных требований к актуальности или повторной проверке на сервере, используется запись из кэша.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-133">If the cache entry was revalidated after the cache synchronization date and there are no additional freshness or server revalidation requirements that invalidate the cached entry, the entry from the cache is used.</span></span> <span data-ttu-id="6c4bc-134">Если дата синхронизации кэша — это будущая дата, запись повторно проверяется каждый раз, когда она запрашивается, пока эта дата не пройдет.</span><span class="sxs-lookup"><span data-stu-id="6c4bc-134">If the cache synchronization date is set to a future date, the entry is revalidated every time it is requested, until the cache synchronization date passes.</span></span>  
  
 <span data-ttu-id="6c4bc-135">В следующих разделах приводятся сведения о том, как действуют различные сочетания критериев для политики кэша на основе времени:</span><span class="sxs-lookup"><span data-stu-id="6c4bc-135">The following topics provide information about the effects of combining time-based cache policy criteria:</span></span>  
  
-   [<span data-ttu-id="6c4bc-136">Взаимодействие с политикой кэша: максимальный возраст и устаревание</span><span class="sxs-lookup"><span data-stu-id="6c4bc-136">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
-   [<span data-ttu-id="6c4bc-137">Взаимодействие с политикой кэша: максимальный возраст и минимальная актуальность</span><span class="sxs-lookup"><span data-stu-id="6c4bc-137">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c4bc-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6c4bc-138">See Also</span></span>  
 [<span data-ttu-id="6c4bc-139">Управление кэшем для сетевых приложений</span><span class="sxs-lookup"><span data-stu-id="6c4bc-139">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="6c4bc-140">Политика кэша</span><span class="sxs-lookup"><span data-stu-id="6c4bc-140">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="6c4bc-141">Политики кэша на основе расположения</span><span class="sxs-lookup"><span data-stu-id="6c4bc-141">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="6c4bc-142">Настройка кэширования в сетевых приложениях</span><span class="sxs-lookup"><span data-stu-id="6c4bc-142">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="6c4bc-143">Элемент \<requestCaching> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="6c4bc-143">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
