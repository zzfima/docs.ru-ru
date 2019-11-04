---
ms.openlocfilehash: 3f702febc78488b9413ec9303ded211493650f02
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198553"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="06942-101">MVC. Средство предварительной компиляции устарело</span><span class="sxs-lookup"><span data-stu-id="06942-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="06942-102">В ASP.NET Core 1.1 был введен пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (средство предварительной компиляции MVC), чтобы организовать поддержку компиляции файлов Razor во время публикации (файлы *.cshtml*).</span><span class="sxs-lookup"><span data-stu-id="06942-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="06942-103">В ASP.NET Core 2.1 добавлен [пакет SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1), который расширил возможности этого средства предварительной компиляции.</span><span class="sxs-lookup"><span data-stu-id="06942-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="06942-104">Этот пакет SDK для Razor добавил поддержку компиляции файлов Razor во время сборки и публикации.</span><span class="sxs-lookup"><span data-stu-id="06942-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="06942-105">Пакет SDK проверяет правильность файлов *.cshtml* во время сборки, что снижает время запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="06942-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="06942-106">Пакет SDK для Razor включен по умолчанию, и для его использования не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="06942-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="06942-107">В ASP.NET Core 3.0 было удалено средство предварительной компиляции MVC, сохранившееся с эпохи ASP.NET Core версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="06942-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="06942-108">Более ранние версии пакетов будут по-прежнему получать важные исправления ошибок и безопасности в выпусках исправлений.</span><span class="sxs-lookup"><span data-stu-id="06942-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="06942-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="06942-109">Version introduced</span></span>

<span data-ttu-id="06942-110">3.0</span><span class="sxs-lookup"><span data-stu-id="06942-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="06942-111">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="06942-111">Old behavior</span></span>

<span data-ttu-id="06942-112">Для предварительной компиляции представлений Razor MVC использовался пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation`.</span><span class="sxs-lookup"><span data-stu-id="06942-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="06942-113">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="06942-113">New behavior</span></span>

<span data-ttu-id="06942-114">Пакет SDK для Razor имеет встроенную поддержку этой возможности.</span><span class="sxs-lookup"><span data-stu-id="06942-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="06942-115">Пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` более не обновляется.</span><span class="sxs-lookup"><span data-stu-id="06942-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="06942-116">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="06942-116">Reason for change</span></span>

<span data-ttu-id="06942-117">Пакет SDK для Razor дает больше возможностей и проверяет правильность файлов *.cshtml* во время сборки.</span><span class="sxs-lookup"><span data-stu-id="06942-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="06942-118">Благодаря этому пакет SDK снижает время запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="06942-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="06942-119">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="06942-119">Recommended action</span></span>

<span data-ttu-id="06942-120">Если вы используете ASP.NET Core версии 2.1 или более поздней версии, обновите систему для применения встроенной поддержки предварительной компиляции в [пакете SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="06942-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="06942-121">Если ошибки или отсутствующие компоненты препятствуют миграции на пакет SDK для Razor, сообщите о проблеме а [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span><span class="sxs-lookup"><span data-stu-id="06942-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="06942-122">Категория</span><span class="sxs-lookup"><span data-stu-id="06942-122">Category</span></span>

<span data-ttu-id="06942-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="06942-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="06942-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="06942-124">Affected APIs</span></span>

<span data-ttu-id="06942-125">Нет</span><span class="sxs-lookup"><span data-stu-id="06942-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
