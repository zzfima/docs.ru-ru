---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522657"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="9b8e7-101">Одностраничные приложения: SpaServices и NodeServices больше не переключаются на средство ведения журнала консоли</span><span class="sxs-lookup"><span data-stu-id="9b8e7-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="9b8e7-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> и <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> больше не отображают журналы консоли, если ведение журналов не настроено.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9b8e7-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="9b8e7-103">Version introduced</span></span>

<span data-ttu-id="9b8e7-104">3.0</span><span class="sxs-lookup"><span data-stu-id="9b8e7-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9b8e7-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="9b8e7-105">Old behavior</span></span>

<span data-ttu-id="9b8e7-106">`Microsoft.AspNetCore.SpaServices` и `Microsoft.AspNetCore.NodeServices` использовались для автоматического создания средства для ведения журналов консоли в тех случаях, если ведение журналов не было настроено.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9b8e7-107">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="9b8e7-107">New behavior</span></span>

<span data-ttu-id="9b8e7-108">`Microsoft.AspNetCore.SpaServices` и `Microsoft.AspNetCore.NodeServices` больше не отображают журналы консоли, если ведение журналов не настроено.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9b8e7-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="9b8e7-109">Reason for change</span></span>

<span data-ttu-id="9b8e7-110">Необходимость в согласованной реализации ведения журналов с другими пакетами ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9b8e7-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="9b8e7-111">Recommended action</span></span>

<span data-ttu-id="9b8e7-112">Если вам нужно воспроизвести старое поведение, добавьте `services.AddLogging(builder => builder.AddConsole())` к своему методу `Setup.ConfigureServices`, чтобы настроить ведение журнала консоли.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="9b8e7-113">Категория</span><span class="sxs-lookup"><span data-stu-id="9b8e7-113">Category</span></span>

<span data-ttu-id="9b8e7-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b8e7-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9b8e7-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9b8e7-115">Affected APIs</span></span>

<span data-ttu-id="9b8e7-116">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9b8e7-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
