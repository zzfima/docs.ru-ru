---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291648"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>SignalR. Методы UseSignalR и UseConnections удалены

В ASP.NET Core 3.0, SignalR приняла построение маршрутов конечных точек. В рамках этого изменения <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, а также некоторые связанные методы были помечены как устаревшие. В ASP.NET Core 5.0 эти устаревшие методы удалены. Полный список методов см. в разделе [Затронутые API](#affected-apis).

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).

#### <a name="version-introduced"></a>Представленная версия

5.0 Предварительная версия 3

#### <a name="old-behavior"></a>Старое поведение

Концентраторы SignalR и обработчики соединений можно зарегистрировать в конвейере ПО промежуточного слоя с помощью методов `UseSignalR` или `UseConnections`.

#### <a name="new-behavior"></a>Новое поведение

Концентраторы SignalR и обработчики соединений следует зарегистрировать в <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> с помощью методов расширения <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> и <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> в <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.

#### <a name="reason-for-change"></a>Причина изменения

Старые методы имели пользовательскую логику построения маршрутов, которая не взаимодействовала с другими компонентами построения маршрутов в ASP.NET Core. В ASP.NET Core 3.0 появилась новая система построения маршрутов общего назначения, называемая построением маршрутов конечных точек. Служба SignalR включила построение маршрутов конечных точек для взаимодействия с другими компонентами построения маршрутов. Переключение на эту модель позволяет пользователям реализовать все преимущества построения маршрутов конечных точек. Следовательно, старые методы были удалены.

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите код, который вызывает `UseSignalR` или `UseConnections` из метода `Startup.Configure` проекта. Замените его вызовами `MapHub` или `MapConnectionHandler`соответственно, в теле вызова `UseEndpoints`. Пример:

**Старый код:**

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

**Новый код:**

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

В целом, предыдущие вызовы `MapHub` и `MapConnectionHandler` можно передать непосредственно из тела `UseSignalR` и `UseConnections` в `UseEndpoints` с минимальными изменениями.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

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
