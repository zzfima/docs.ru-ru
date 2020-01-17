---
ms.openlocfilehash: 1e081c9f37fbd7ab754ce44ba89d7aa5cabfc219
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901945"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="b6a50-101">MVC. Средство предварительной компиляции устарело</span><span class="sxs-lookup"><span data-stu-id="b6a50-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="b6a50-102">В ASP.NET Core 1.1 был введен пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (средство предварительной компиляции MVC), чтобы организовать поддержку компиляции файлов Razor во время публикации (файлы *.cshtml*).</span><span class="sxs-lookup"><span data-stu-id="b6a50-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="b6a50-103">В ASP.NET Core 2.1 добавлен [пакет SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1), который расширил возможности этого средства предварительной компиляции.</span><span class="sxs-lookup"><span data-stu-id="b6a50-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="b6a50-104">Этот пакет SDK для Razor добавил поддержку компиляции файлов Razor во время сборки и публикации.</span><span class="sxs-lookup"><span data-stu-id="b6a50-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="b6a50-105">Пакет SDK проверяет правильность файлов *.cshtml* во время сборки, что снижает время запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b6a50-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="b6a50-106">Пакет SDK для Razor включен по умолчанию, и для его использования не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="b6a50-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="b6a50-107">В ASP.NET Core 3.0 было удалено средство предварительной компиляции MVC, сохранившееся с эпохи ASP.NET Core версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="b6a50-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="b6a50-108">Более ранние версии пакетов будут по-прежнему получать важные исправления ошибок и безопасности в выпусках исправлений.</span><span class="sxs-lookup"><span data-stu-id="b6a50-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b6a50-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b6a50-109">Version introduced</span></span>

<span data-ttu-id="b6a50-110">3.0</span><span class="sxs-lookup"><span data-stu-id="b6a50-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b6a50-111">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="b6a50-111">Old behavior</span></span>

<span data-ttu-id="b6a50-112">Для предварительной компиляции представлений Razor MVC использовался пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation`.</span><span class="sxs-lookup"><span data-stu-id="b6a50-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b6a50-113">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="b6a50-113">New behavior</span></span>

<span data-ttu-id="b6a50-114">Пакет SDK для Razor имеет встроенную поддержку этой возможности.</span><span class="sxs-lookup"><span data-stu-id="b6a50-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="b6a50-115">Пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` более не обновляется.</span><span class="sxs-lookup"><span data-stu-id="b6a50-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b6a50-116">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="b6a50-116">Reason for change</span></span>

<span data-ttu-id="b6a50-117">Пакет SDK для Razor дает больше возможностей и проверяет правильность файлов *.cshtml* во время сборки.</span><span class="sxs-lookup"><span data-stu-id="b6a50-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="b6a50-118">Благодаря этому пакет SDK снижает время запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b6a50-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b6a50-119">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b6a50-119">Recommended action</span></span>

<span data-ttu-id="b6a50-120">Если вы используете ASP.NET Core версии 2.1 или более поздней версии, обновите систему для применения встроенной поддержки предварительной компиляции в [пакете SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="b6a50-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="b6a50-121">Если ошибки или отсутствующие компоненты препятствуют миграции на пакет SDK для Razor, сообщите о проблеме в [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="b6a50-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="b6a50-122">Категория</span><span class="sxs-lookup"><span data-stu-id="b6a50-122">Category</span></span>

<span data-ttu-id="b6a50-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6a50-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b6a50-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b6a50-124">Affected APIs</span></span>

<span data-ttu-id="b6a50-125">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="b6a50-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
