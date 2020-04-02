---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291648"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="508dc-101">SignalR. Методы UseSignalR и UseConnections удалены</span><span class="sxs-lookup"><span data-stu-id="508dc-101">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="508dc-102">В ASP.NET Core 3.0, SignalR приняла построение маршрутов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="508dc-102">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="508dc-103">В рамках этого изменения <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, а также некоторые связанные методы были помечены как устаревшие.</span><span class="sxs-lookup"><span data-stu-id="508dc-103">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="508dc-104">В ASP.NET Core 5.0 эти устаревшие методы удалены.</span><span class="sxs-lookup"><span data-stu-id="508dc-104">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="508dc-105">Полный список методов см. в разделе [Затронутые API](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="508dc-105">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="508dc-106">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="508dc-106">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="508dc-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="508dc-107">Version introduced</span></span>

<span data-ttu-id="508dc-108">5.0 Предварительная версия 3</span><span class="sxs-lookup"><span data-stu-id="508dc-108">5.0 Preview 3</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="508dc-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="508dc-109">Old behavior</span></span>

<span data-ttu-id="508dc-110">Концентраторы SignalR и обработчики соединений можно зарегистрировать в конвейере ПО промежуточного слоя с помощью методов `UseSignalR` или `UseConnections`.</span><span class="sxs-lookup"><span data-stu-id="508dc-110">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="508dc-111">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="508dc-111">New behavior</span></span>

<span data-ttu-id="508dc-112">Концентраторы SignalR и обработчики соединений следует зарегистрировать в <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> с помощью методов расширения <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> и <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> в <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span><span class="sxs-lookup"><span data-stu-id="508dc-112">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="508dc-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="508dc-113">Reason for change</span></span>

<span data-ttu-id="508dc-114">Старые методы имели пользовательскую логику построения маршрутов, которая не взаимодействовала с другими компонентами построения маршрутов в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="508dc-114">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="508dc-115">В ASP.NET Core 3.0 появилась новая система построения маршрутов общего назначения, называемая построением маршрутов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="508dc-115">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="508dc-116">Служба SignalR включила построение маршрутов конечных точек для взаимодействия с другими компонентами построения маршрутов.</span><span class="sxs-lookup"><span data-stu-id="508dc-116">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="508dc-117">Переключение на эту модель позволяет пользователям реализовать все преимущества построения маршрутов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="508dc-117">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="508dc-118">Следовательно, старые методы были удалены.</span><span class="sxs-lookup"><span data-stu-id="508dc-118">Consequently, the old methods have been removed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="508dc-119">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="508dc-119">Recommended action</span></span>

<span data-ttu-id="508dc-120">Удалите код, который вызывает `UseSignalR` или `UseConnections` из метода `Startup.Configure` проекта.</span><span class="sxs-lookup"><span data-stu-id="508dc-120">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="508dc-121">Замените его вызовами `MapHub` или `MapConnectionHandler`соответственно, в теле вызова `UseEndpoints`.</span><span class="sxs-lookup"><span data-stu-id="508dc-121">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="508dc-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="508dc-122">For example:</span></span>

<span data-ttu-id="508dc-123">**Старый код:**</span><span class="sxs-lookup"><span data-stu-id="508dc-123">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="508dc-124">**Новый код:**</span><span class="sxs-lookup"><span data-stu-id="508dc-124">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="508dc-125">В целом, предыдущие вызовы `MapHub` и `MapConnectionHandler` можно передать непосредственно из тела `UseSignalR` и `UseConnections` в `UseEndpoints` с минимальными изменениями.</span><span class="sxs-lookup"><span data-stu-id="508dc-125">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

#### <a name="category"></a><span data-ttu-id="508dc-126">Категория</span><span class="sxs-lookup"><span data-stu-id="508dc-126">Category</span></span>

<span data-ttu-id="508dc-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="508dc-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="508dc-128">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="508dc-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
