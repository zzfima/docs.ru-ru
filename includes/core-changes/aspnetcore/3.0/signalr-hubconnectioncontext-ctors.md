---
ms.openlocfilehash: 8979b7ffc09726c6588fe3ba60b916202697648f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522668"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="dbaa4-101">SignalR. Изменение конструкторов HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="dbaa4-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="dbaa4-102">Конструкторы `HubConnectionContext` SignalR были изменены, чтобы принимать тип параметров, а не несколько параметров, для добавления параметров в будущем.</span><span class="sxs-lookup"><span data-stu-id="dbaa4-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="dbaa4-103">Это изменение заменяет два конструктора одним конструктором, принимающим тип параметров.</span><span class="sxs-lookup"><span data-stu-id="dbaa4-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dbaa4-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="dbaa4-104">Version introduced</span></span>

<span data-ttu-id="dbaa4-105">3.0</span><span class="sxs-lookup"><span data-stu-id="dbaa4-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="dbaa4-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="dbaa4-106">Old behavior</span></span>

<span data-ttu-id="dbaa4-107">`HubConnectionContext` имеет два конструктора:</span><span class="sxs-lookup"><span data-stu-id="dbaa4-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="dbaa4-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="dbaa4-108">New behavior</span></span>

<span data-ttu-id="dbaa4-109">Два конструктора были удалены и заменены одним конструктором:</span><span class="sxs-lookup"><span data-stu-id="dbaa4-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="dbaa4-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="dbaa4-110">Reason for change</span></span>

<span data-ttu-id="dbaa4-111">Новый конструктор использует новый объект параметров.</span><span class="sxs-lookup"><span data-stu-id="dbaa4-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="dbaa4-112">Следовательно, функции `HubConnectionContext` можно расширить в будущем, не создавая дополнительные конструкторы и не внося критические изменения.</span><span class="sxs-lookup"><span data-stu-id="dbaa4-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dbaa4-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="dbaa4-113">Recommended action</span></span>

<span data-ttu-id="dbaa4-114">Вместо использования следующего конструктора:</span><span class="sxs-lookup"><span data-stu-id="dbaa4-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="dbaa4-115">Используйте следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="dbaa4-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="dbaa4-116">Категория</span><span class="sxs-lookup"><span data-stu-id="dbaa4-116">Category</span></span>

<span data-ttu-id="dbaa4-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dbaa4-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dbaa4-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="dbaa4-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
