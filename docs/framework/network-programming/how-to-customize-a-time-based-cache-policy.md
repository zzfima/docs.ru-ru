---
title: Практическое руководство. Настройка политики кэша на основе времени
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: 1a2ba404e333eeec2a23758c834876d0df5aba81
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040632"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="ff05d-102">Практическое руководство. Настройка политики кэша на основе времени</span><span class="sxs-lookup"><span data-stu-id="ff05d-102">How to: customize a time-based cache policy</span></span>

<span data-ttu-id="ff05d-103">При создании политики кэша на основе времени можно настроить поведение кэширования, устанавливая значения максимального возраста, минимальной актуальности или даты синхронизации кэша.</span><span class="sxs-lookup"><span data-stu-id="ff05d-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="ff05d-104">Объект <xref:System.Net.Cache.HttpRequestCachePolicy> предоставляет несколько конструкторов, позволяющих определять допустимые сочетания этих значений.</span><span class="sxs-lookup"><span data-stu-id="ff05d-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="ff05d-105">Создание политики кэша на основе времени с использованием даты синхронизации кэша</span><span class="sxs-lookup"><span data-stu-id="ff05d-105">To create a time-based cache policy that uses a cache synchronization date</span></span>

<span data-ttu-id="ff05d-106">Создание политики кэша на основе времени с использованием даты синхронизации кэша осуществляется за счет передачи объекта <xref:System.DateTime> в конструктор <xref:System.Net.Cache.HttpRequestCachePolicy>:</span><span class="sxs-lookup"><span data-stu-id="ff05d-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)
{
    var policy = new HttpRequestCachePolicy(when);
    Console.WriteLine("When: {0}", when);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy([when])
    Console.WriteLine("When: {0}", [when])
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="ff05d-107">Выходные данные будут иметь примерно следующий вид:</span><span class="sxs-lookup"><span data-stu-id="ff05d-107">The output is similar to the following:</span></span>

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="ff05d-108">Создание политики кэша на основе времени с использованием минимальной актуальности</span><span class="sxs-lookup"><span data-stu-id="ff05d-108">To create a time-based cache policy that is based on minimum freshness</span></span>

<span data-ttu-id="ff05d-109">Чтобы создать политику кэша на основе времени с использованием минимальной актуальности, укажите <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> в качестве значения параметра `cacheAgeControl` и передайте объект <xref:System.TimeSpan> в конструктор <xref:System.Net.Cache.HttpRequestCachePolicy>:</span><span class="sxs-lookup"><span data-stu-id="ff05d-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="ff05d-110">Для следующего вызова:</span><span class="sxs-lookup"><span data-stu-id="ff05d-110">For the following invocation:</span></span>

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

<span data-ttu-id="ff05d-111">Результаты:</span><span class="sxs-lookup"><span data-stu-id="ff05d-111">The output is:</span></span>

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="ff05d-112">Создание политики кэша на основе времени с использованием минимальной актуальности и максимального возраста</span><span class="sxs-lookup"><span data-stu-id="ff05d-112">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>

<span data-ttu-id="ff05d-113">Чтобы создать политику кэша на основе времени с использованием минимальной актуальности и максимального возраста, укажите <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> в качестве значения параметра `cacheAgeControl` и передайте два объекта <xref:System.TimeSpan> в конструктор <xref:System.Net.Cache.HttpRequestCachePolicy>. Один из этих объектов задает максимальный возраст ресурсов, а второй — минимально допустимую актуальность объекта, возвращаемого из кэша:</span><span class="sxs-lookup"><span data-stu-id="ff05d-113">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache:</span></span>

```csharp
public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="ff05d-114">Для следующего вызова:</span><span class="sxs-lookup"><span data-stu-id="ff05d-114">For the following invocation:</span></span>
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

<span data-ttu-id="ff05d-115">Результаты:</span><span class="sxs-lookup"><span data-stu-id="ff05d-115">The output is:</span></span>
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff05d-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff05d-116">See also</span></span>

- [<span data-ttu-id="ff05d-117">Управление кэшем для сетевых приложений</span><span class="sxs-lookup"><span data-stu-id="ff05d-117">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="ff05d-118">Политика кэша</span><span class="sxs-lookup"><span data-stu-id="ff05d-118">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="ff05d-119">Политики кэша на основе расположения</span><span class="sxs-lookup"><span data-stu-id="ff05d-119">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="ff05d-120">Политики кэша на основе времени</span><span class="sxs-lookup"><span data-stu-id="ff05d-120">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="ff05d-121">Элемент \<requestCaching> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ff05d-121">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
