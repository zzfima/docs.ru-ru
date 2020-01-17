---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901854"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="3f960-101">SignalR: методы HubConnection ResetSendPing и ResetTimeout были удалены</span><span class="sxs-lookup"><span data-stu-id="3f960-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="3f960-102">Методы `ResetSendPing` и `ResetTimeout` были удалены из API `HubConnection` в SignalR.</span><span class="sxs-lookup"><span data-stu-id="3f960-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="3f960-103">Эти методы изначально предназначались только для внутреннего использования, но стали общедоступными в ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3f960-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="3f960-104">Эти методы не будут доступны начиная с выпуска ASP.NET Core 3.0 (предварительная версия 4).</span><span class="sxs-lookup"><span data-stu-id="3f960-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="3f960-105">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span><span class="sxs-lookup"><span data-stu-id="3f960-105">For discussion, see [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3f960-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="3f960-106">Version introduced</span></span>

<span data-ttu-id="3f960-107">3.0</span><span class="sxs-lookup"><span data-stu-id="3f960-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3f960-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="3f960-108">Old behavior</span></span>

<span data-ttu-id="3f960-109">Интерфейсы API были доступны.</span><span class="sxs-lookup"><span data-stu-id="3f960-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3f960-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="3f960-110">New behavior</span></span>

<span data-ttu-id="3f960-111">Интерфейсы API удалены.</span><span class="sxs-lookup"><span data-stu-id="3f960-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3f960-112">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="3f960-112">Reason for change</span></span>

<span data-ttu-id="3f960-113">Эти методы изначально предназначались только для внутреннего использования, но стали общедоступными в ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3f960-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3f960-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="3f960-114">Recommended action</span></span>

<span data-ttu-id="3f960-115">Не используйте эти методы.</span><span class="sxs-lookup"><span data-stu-id="3f960-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="3f960-116">Категория</span><span class="sxs-lookup"><span data-stu-id="3f960-116">Category</span></span>

<span data-ttu-id="3f960-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f960-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3f960-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3f960-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
