---
ms.openlocfilehash: 53d2c989120c92f4e2d18f50ce4b364bd4c9b604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901989"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="a2da6-101">HTTP. Отключение синхронного ввода-вывода на всех серверах</span><span class="sxs-lookup"><span data-stu-id="a2da6-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="a2da6-102">Начиная с ASP.NET Core 3,0, синхронные операции сервера по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="a2da6-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a2da6-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="a2da6-103">Change description</span></span>

<span data-ttu-id="a2da6-104">Параметр `AllowSynchronousIO` включает или отключает на каждом сервере синхронные API ввода-вывода, например `HttpRequest.Body.Read`, `HttpResponse.Body.Write` и `Stream.Flush`.</span><span class="sxs-lookup"><span data-stu-id="a2da6-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="a2da6-105">Эти API-интерфейсы долго были причиной нехватки потоков и зависания приложений.</span><span class="sxs-lookup"><span data-stu-id="a2da6-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="a2da6-106">Начиная с ASP.NET Core 3.0 предварительной версии 3, синхронные операции сервера по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="a2da6-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="a2da6-107">Затрагиваемые службы:</span><span class="sxs-lookup"><span data-stu-id="a2da6-107">Affected servers:</span></span>

- <span data-ttu-id="a2da6-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="a2da6-108">Kestrel</span></span>
- <span data-ttu-id="a2da6-109">HttpSys</span><span class="sxs-lookup"><span data-stu-id="a2da6-109">HttpSys</span></span>
- <span data-ttu-id="a2da6-110">IIS (внутрипроцессный)</span><span class="sxs-lookup"><span data-stu-id="a2da6-110">IIS in-process</span></span>
- <span data-ttu-id="a2da6-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="a2da6-111">TestServer</span></span>

<span data-ttu-id="a2da6-112">Можно ожидать ошибки, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="a2da6-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="a2da6-113">Каждый сервер имеет параметр `AllowSynchronousIO`, который управляет этим поведением, и по умолчанию для всех из них используется значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a2da6-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="a2da6-114">Также в качестве временного решения можно переопределять это поведение для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="a2da6-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="a2da6-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="a2da6-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="a2da6-116">Если у вас возникают проблемы с `TextWriter` или другим потоком, который вызывает синхронный API в `Dispose`, обращайтесь вместо него к новому API-интерфейсу `DisposeAsync`.</span><span class="sxs-lookup"><span data-stu-id="a2da6-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="a2da6-117">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#7644](https://github.com/dotnet/aspnetcore/issues/7644).</span><span class="sxs-lookup"><span data-stu-id="a2da6-117">For discussion, see [dotnet/aspnetcore#7644](https://github.com/dotnet/aspnetcore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a2da6-118">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="a2da6-118">Version introduced</span></span>

<span data-ttu-id="a2da6-119">3.0</span><span class="sxs-lookup"><span data-stu-id="a2da6-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a2da6-120">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="a2da6-120">Old behavior</span></span>

<span data-ttu-id="a2da6-121">По умолчанию были разрешены `HttpRequest.Body.Read`, `HttpResponse.Body.Write` и `Stream.Flush`.</span><span class="sxs-lookup"><span data-stu-id="a2da6-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a2da6-122">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="a2da6-122">New behavior</span></span>

<span data-ttu-id="a2da6-123">Эти синхронные API запрещены по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a2da6-123">These synchronous APIs are disallowed by default:</span></span>

<span data-ttu-id="a2da6-124">Можно ожидать ошибки, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="a2da6-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="a2da6-125">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="a2da6-125">Reason for change</span></span>

<span data-ttu-id="a2da6-126">Эти синхронные API-интерфейсы долго были причиной нехватки потоков и зависания приложений.</span><span class="sxs-lookup"><span data-stu-id="a2da6-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="a2da6-127">Начиная с ASP.NET Core 3.0 предварительной версии 3, синхронные операции сервера по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="a2da6-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a2da6-128">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="a2da6-128">Recommended action</span></span>

<span data-ttu-id="a2da6-129">Используйте асинхронные версии этих методов.</span><span class="sxs-lookup"><span data-stu-id="a2da6-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="a2da6-130">Также в качестве временного решения можно переопределять это поведение для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="a2da6-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="a2da6-131">Категория</span><span class="sxs-lookup"><span data-stu-id="a2da6-131">Category</span></span>

<span data-ttu-id="a2da6-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a2da6-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a2da6-133">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a2da6-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
