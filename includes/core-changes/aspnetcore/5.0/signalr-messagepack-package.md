---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345213"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="163c2-101">SignalR. Протокол MessagePack для концентратора перемещен в пакет MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="163c2-101">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="163c2-102">[Протокол концентратора MessagePack](/aspnet/core/signalr/messagepackhubprotocol) для ASP.NET Core SignalR использует [пакет NuGet MessagePack](https://www.nuget.org/packages/MessagePack) для сериализации MessagePack.</span><span class="sxs-lookup"><span data-stu-id="163c2-102">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="163c2-103">ASP.NET Core 5.0 обновляет пакет с 1.x до последней версии пакета 2.x.</span><span class="sxs-lookup"><span data-stu-id="163c2-103">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="163c2-104">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="163c2-104">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="163c2-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="163c2-105">Version introduced</span></span>

<span data-ttu-id="163c2-106">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="163c2-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="163c2-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="163c2-107">Old behavior</span></span>

<span data-ttu-id="163c2-108">Чтобы сериализовать и десериализировать сообщения MessagePack, ASP.NET Core SignalR использовал пакет MessagePack 1.x.</span><span class="sxs-lookup"><span data-stu-id="163c2-108">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="163c2-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="163c2-109">New behavior</span></span>

<span data-ttu-id="163c2-110">ASP.NET Core SignalR использует для сериализации и десериализации сообщений MessagePack пакет MessagePack версии 2.x.</span><span class="sxs-lookup"><span data-stu-id="163c2-110">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="163c2-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="163c2-111">Reason for change</span></span>

<span data-ttu-id="163c2-112">Последние улучшения в пакете MessagePack версии 2.x принесли полезные функции.</span><span class="sxs-lookup"><span data-stu-id="163c2-112">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="163c2-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="163c2-113">Recommended action</span></span>

<span data-ttu-id="163c2-114">Это критическое изменение применяется в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="163c2-114">This breaking change applies when:</span></span>

* <span data-ttu-id="163c2-115">При установке или настройке значений на <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span><span class="sxs-lookup"><span data-stu-id="163c2-115">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="163c2-116">При использовании API MessagePack напрямую и протокола концентратора ASP.NET Core MessagePack SignalR в одном проекте.</span><span class="sxs-lookup"><span data-stu-id="163c2-116">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="163c2-117">Вместо предыдущей версии будет загружена новая версия.</span><span class="sxs-lookup"><span data-stu-id="163c2-117">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="163c2-118">Руководство по миграции от авторов пакетов см. в статье [Переход с MessagePack версии 1.x на MessagePack версии 2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="163c2-118">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="163c2-119">Затрагиваются некоторые аспекты сериализации и десериализации сообщений.</span><span class="sxs-lookup"><span data-stu-id="163c2-119">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="163c2-120">В частности, имеются [изменения поведения, определяющие порядок сериализации значений DateTime](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="163c2-120">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

#### <a name="category"></a><span data-ttu-id="163c2-121">Категория</span><span class="sxs-lookup"><span data-stu-id="163c2-121">Category</span></span>

<span data-ttu-id="163c2-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="163c2-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="163c2-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="163c2-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
