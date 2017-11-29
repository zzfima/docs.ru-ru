---
title: "Взаимодействие с политикой кэша: максимальный возраст и устаревание"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: baec376501feb70e4a9ceb3f33ac66fa76b91ac1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a><span data-ttu-id="419e8-102">Взаимодействие с политикой кэша: максимальный возраст и устаревание</span><span class="sxs-lookup"><span data-stu-id="419e8-102">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>
<span data-ttu-id="419e8-103">Чтобы обеспечить возврат клиентскому приложению самого актуального содержимого, в результате взаимодействия политики кэша клиента и требований к повторной проверке сервера всегда применяется наиболее консервативная политика кэша.</span><span class="sxs-lookup"><span data-stu-id="419e8-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="419e8-104">Все примеры в этом разделе иллюстрируют политику кэша для ресурса, который кэшируется 1 января и срок действия которого истекает 4 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="419e8-105">В следующих примерах значение максимального возраста (`maxStale`) используется в сочетании со значением максимального срока действия (`maxAge`):</span><span class="sxs-lookup"><span data-stu-id="419e8-105">In the following examples, the maximum staleness value (`maxStale`) is used in conjunction with a maximum age (`maxAge`):</span></span>  
  
-   <span data-ttu-id="419e8-106">Если в политике кэша значение `maxAge` задано равным 5 дням, а значение `maxStale` не задано, то в соответствии со значением `maxAge` содержимое можно использовать до 6 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-106">If the cache policy sets `maxAge` = 5 days and does not specify a `maxStale` value, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="419e8-107">Однако согласно требованиям сервера к повторной проверке срок действия содержимого истекает 4 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-107">However, according to the server's revalidation requirements, the content expires on January 4.</span></span> <span data-ttu-id="419e8-108">Так как дата истечения срока действия содержимого более консервативна (наступает раньше), она имеет приоритет над политикой `maxAge`.</span><span class="sxs-lookup"><span data-stu-id="419e8-108">Because the content expiration date is more conservative (sooner), it takes precedence over the `maxAge` policy.</span></span> <span data-ttu-id="419e8-109">Поэтому срок действия содержимого истекает 4 января и его необходимо проверить повторно, несмотря на то, что максимальный срок действия не достигнут.</span><span class="sxs-lookup"><span data-stu-id="419e8-109">Therefore, the content expires on January 4 and must be revalidated even though its maximum age has not been reached.</span></span>  
  
-   <span data-ttu-id="419e8-110">Если политика кэша задает значение `maxAge` равным 5 дням, а значение `maxStale` равным 3 дням, то в соответствии со значением `maxAge` содержимое можно использовать до 6 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-110">If the cache policy sets `maxAge` = 5 days and `maxStale` = 3 days, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="419e8-111">Согласно значению `maxStale` содержимое можно использовать до 7 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-111">According to the `maxStale` value, the content is usable until January 7.</span></span> <span data-ttu-id="419e8-112">Поэтому оно будет проверено повторно 6 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-112">Therefore, the content gets revalidated on January 6.</span></span>  
  
-   <span data-ttu-id="419e8-113">Если политика кэша задает значение `maxAge` равным 5 дням, а значение `maxStale` равным 1 дню, то в соответствии со значением `maxAge` содержимое можно использовать до 6 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-113">If the cache policy sets `maxAge` = 5 days and `maxStale` = 1 day, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="419e8-114">Согласно значению `maxStale` содержимое можно использовать до 5 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-114">According to the `maxStale` value, the content is usable until January 5.</span></span> <span data-ttu-id="419e8-115">Поэтому оно будет проверено повторно 5 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-115">Therefore, the content gets revalidated on January 5.</span></span>  
  
 <span data-ttu-id="419e8-116">Если максимальный срок действия заканчивается раньше фактической даты истечения срока действия, приоритет имеет более консервативный критерий кэширования и значение максимального возраста не действует.</span><span class="sxs-lookup"><span data-stu-id="419e8-116">When the maximum age is less than the content expiration date, the more conservative caching behavior always prevails and the maximum staleness value has no effect.</span></span> <span data-ttu-id="419e8-117">В следующих примерах показан результат задания максимального возраста (`maxStale`) в случае, если максимальный срок действия (`maxAge`) истекает до того, как содержимое станет недействительным:</span><span class="sxs-lookup"><span data-stu-id="419e8-117">The following examples illustrate the effect of setting a maximum staleness (`maxStale`) value when the maximum age (`maxAge`) is reached before the content expires:</span></span>  
  
-   <span data-ttu-id="419e8-118">Если политика кэша задает значение `maxAge` равным 1 дню, а значение `maxStale` не задано, содержимое проверяется повторно 2 января, даже если срок его действия не истек.</span><span class="sxs-lookup"><span data-stu-id="419e8-118">If the cache policy sets `maxAge` = 1 day and does not specify a value for `maxStale` value, the content is revalidated on January 2 even though it has not expired.</span></span>  
  
-   <span data-ttu-id="419e8-119">Если политика кэша задает значение `maxAge` равным 1 дню, а значение `maxStale` равным 3 дням, содержимое проверяется повторно 2 января в соответствии с более консервативным параметром политики.</span><span class="sxs-lookup"><span data-stu-id="419e8-119">If the cache policy sets `maxAge` = 1 day and `maxStale` = 3 days, the content is revalidated on January 2 to enforce the more conservative policy setting.</span></span>  
  
-   <span data-ttu-id="419e8-120">Если политика кэша задает значения `maxAge` и `maxStale` равными 1 дню, содержимое повторно проверяется 2 января.</span><span class="sxs-lookup"><span data-stu-id="419e8-120">If the cache policy sets `maxAge` = 1 day and `maxStale` = 1 day, the content is revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419e8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="419e8-121">See Also</span></span>  
 [<span data-ttu-id="419e8-122">Управление кэшем для сетевых приложений</span><span class="sxs-lookup"><span data-stu-id="419e8-122">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="419e8-123">Политика кэша</span><span class="sxs-lookup"><span data-stu-id="419e8-123">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="419e8-124">Политики кэша на основе расположения</span><span class="sxs-lookup"><span data-stu-id="419e8-124">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="419e8-125">Политики кэша на основе времени</span><span class="sxs-lookup"><span data-stu-id="419e8-125">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="419e8-126">Настройка кэширования в сетевых приложениях</span><span class="sxs-lookup"><span data-stu-id="419e8-126">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="419e8-127">Взаимодействие с политикой кэша: максимальный возраст и минимальная актуальность</span><span class="sxs-lookup"><span data-stu-id="419e8-127">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)
