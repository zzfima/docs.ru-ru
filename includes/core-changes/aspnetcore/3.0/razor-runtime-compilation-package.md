---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394234"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="72e0d-101">Razor. Компиляция во время выполнения перемещена в пакет</span><span class="sxs-lookup"><span data-stu-id="72e0d-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="72e0d-102">Компиляция во время выполнения представлений Razor и Razor Pages перемещена в отдельный пакет.</span><span class="sxs-lookup"><span data-stu-id="72e0d-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="72e0d-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="72e0d-103">Version introduced</span></span>

<span data-ttu-id="72e0d-104">3.0</span><span class="sxs-lookup"><span data-stu-id="72e0d-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="72e0d-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="72e0d-105">Old behavior</span></span>

<span data-ttu-id="72e0d-106">Компиляция во время выполнения не требует дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="72e0d-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="72e0d-107">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="72e0d-107">New behavior</span></span>

<span data-ttu-id="72e0d-108">Функциональные возможности перемещены в пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="72e0d-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="72e0d-109">Следующие API ранее были доступны в `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` для поддержки компиляции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="72e0d-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="72e0d-110">Теперь эти API доступны через `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span><span class="sxs-lookup"><span data-stu-id="72e0d-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="72e0d-111">Кроме того, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` теперь не используется.</span><span class="sxs-lookup"><span data-stu-id="72e0d-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="72e0d-112">Повторная компиляция с учетом изменения файлов включена по умолчанию с использованием ссылки на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="72e0d-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="72e0d-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="72e0d-113">Reason for change</span></span>

<span data-ttu-id="72e0d-114">Это изменение требовалось для удаления ASP.NET Core общей зависимости инфраструктуры от Roslyn.</span><span class="sxs-lookup"><span data-stu-id="72e0d-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="72e0d-115">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="72e0d-115">Recommended action</span></span>

<span data-ttu-id="72e0d-116">Для приложений, требующих компиляции или перекомпиляции файлов Razor во время выполнения, требуются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="72e0d-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="72e0d-117">добавьте ссылку на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`;</span><span class="sxs-lookup"><span data-stu-id="72e0d-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="72e0d-118">обновите метод `Startup.ConfigureServices` в проекте, чтобы включить вызов `AddMvcRazorRuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="72e0d-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="72e0d-119">Например, для `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="72e0d-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="72e0d-120">Категория</span><span class="sxs-lookup"><span data-stu-id="72e0d-120">Category</span></span>

<span data-ttu-id="72e0d-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72e0d-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="72e0d-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="72e0d-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
