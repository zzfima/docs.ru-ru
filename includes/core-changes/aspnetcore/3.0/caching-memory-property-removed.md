---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901869"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="97f89-101">Кэширование: свойство CompactOnMemoryPressure удалено</span><span class="sxs-lookup"><span data-stu-id="97f89-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="97f89-102">В выпуске ASP.NET Core 3.0 недоступны [устаревшие API MemoryCacheOptions](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span><span class="sxs-lookup"><span data-stu-id="97f89-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="97f89-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="97f89-103">Change description</span></span>

<span data-ttu-id="97f89-104">Это изменение реализовано в рамках исправления [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span><span class="sxs-lookup"><span data-stu-id="97f89-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="97f89-105">Обсуждение этого вопроса см. на странице [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span><span class="sxs-lookup"><span data-stu-id="97f89-105">For discussion, see [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="97f89-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="97f89-106">Version introduced</span></span>

<span data-ttu-id="97f89-107">3.0</span><span class="sxs-lookup"><span data-stu-id="97f89-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="97f89-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="97f89-108">Old behavior</span></span>

<span data-ttu-id="97f89-109">Свойство `MemoryCacheOptions.CompactOnMemoryPressure` было доступно.</span><span class="sxs-lookup"><span data-stu-id="97f89-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="97f89-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="97f89-110">New behavior</span></span>

<span data-ttu-id="97f89-111">Свойство `MemoryCacheOptions.CompactOnMemoryPressure` было удалено.</span><span class="sxs-lookup"><span data-stu-id="97f89-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="97f89-112">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="97f89-112">Reason for change</span></span>

<span data-ttu-id="97f89-113">Автоматическое сжатие кэша приводило к возникновению проблем.</span><span class="sxs-lookup"><span data-stu-id="97f89-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="97f89-114">Чтобы не допустить непредвиденное поведение, сжимайте кэш только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="97f89-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="97f89-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="97f89-115">Recommended action</span></span>

<span data-ttu-id="97f89-116">Чтобы сжать кэш, выполните приведение с понижением к `MemoryCache` и вызовите `Compact` при необходимости.</span><span class="sxs-lookup"><span data-stu-id="97f89-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="97f89-117">Категория</span><span class="sxs-lookup"><span data-stu-id="97f89-117">Category</span></span>

<span data-ttu-id="97f89-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97f89-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="97f89-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="97f89-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
