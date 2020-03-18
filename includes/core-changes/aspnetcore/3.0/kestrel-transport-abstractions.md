---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394183"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="a3f66-101">Kestrel. Удаление абстракций транспортировки и их преобразование в общедоступную версию</span><span class="sxs-lookup"><span data-stu-id="a3f66-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="a3f66-102">В рамках перехода от программного интерфейса типа "pubternal" API транспортного уровня Kestrel предоставляются в виде общедоступного интерфейса в библиотеке `Microsoft.AspNetCore.Connections.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="a3f66-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a3f66-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="a3f66-103">Version introduced</span></span>

<span data-ttu-id="a3f66-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a3f66-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a3f66-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="a3f66-105">Old behavior</span></span>

- <span data-ttu-id="a3f66-106">Абстракции, связанные с транспортировкой, были доступны в библиотеке `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="a3f66-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="a3f66-107">Свойство `ListenOptions.NoDelay` было доступно.</span><span class="sxs-lookup"><span data-stu-id="a3f66-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a3f66-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="a3f66-108">New behavior</span></span>

- <span data-ttu-id="a3f66-109">Интерфейс `IConnectionListener` появился в библиотеке `Microsoft.AspNetCore.Connections.Abstractions`, предоставляя наиболее используемые функции из библиотеки `...Transport.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="a3f66-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="a3f66-110">Теперь `NoDelay` можно использовать в параметрах транспорта (`LibuvTransportOptions` и `SocketTransportOptions`).</span><span class="sxs-lookup"><span data-stu-id="a3f66-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="a3f66-111">`SchedulingMode` использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="a3f66-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a3f66-112">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="a3f66-112">Reason for change</span></span>

<span data-ttu-id="a3f66-113">Выполнение переноса ASP.NET Core 3.0 с pubternal API.</span><span class="sxs-lookup"><span data-stu-id="a3f66-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a3f66-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="a3f66-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="a3f66-115">Категория</span><span class="sxs-lookup"><span data-stu-id="a3f66-115">Category</span></span>

<span data-ttu-id="a3f66-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a3f66-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a3f66-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a3f66-117">Affected APIs</span></span>

<span data-ttu-id="a3f66-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="a3f66-118">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
