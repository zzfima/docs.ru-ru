---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344281"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="0d822-101">Razor. Компиляция во время выполнения перемещена в пакет</span><span class="sxs-lookup"><span data-stu-id="0d822-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="0d822-102">Компиляция во время выполнения представлений Razor и Razor Pages перемещена в отдельный пакет.</span><span class="sxs-lookup"><span data-stu-id="0d822-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0d822-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="0d822-103">Version introduced</span></span>

<span data-ttu-id="0d822-104">3.0</span><span class="sxs-lookup"><span data-stu-id="0d822-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0d822-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="0d822-105">Old behavior</span></span>

<span data-ttu-id="0d822-106">Компиляция во время выполнения не требует дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="0d822-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0d822-107">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="0d822-107">New behavior</span></span>

<span data-ttu-id="0d822-108">Функциональные возможности перенесены в пакет [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/).</span><span class="sxs-lookup"><span data-stu-id="0d822-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="0d822-109">Следующие API ранее были доступны в `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` для поддержки компиляции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0d822-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="0d822-110">Теперь эти API доступны через `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span><span class="sxs-lookup"><span data-stu-id="0d822-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="0d822-111">`RazorViewEngineOptions.FileProviders` изменено на `MvcRazorRuntimeCompilationOptions.FileProviders`.</span><span class="sxs-lookup"><span data-stu-id="0d822-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="0d822-112">`RazorViewEngineOptions.AdditionalCompilationReferences` изменено на `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`.</span><span class="sxs-lookup"><span data-stu-id="0d822-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="0d822-113">Кроме того, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` теперь не используется.</span><span class="sxs-lookup"><span data-stu-id="0d822-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="0d822-114">Повторная компиляция с учетом изменения файлов включена по умолчанию с использованием ссылки на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="0d822-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0d822-115">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="0d822-115">Reason for change</span></span>

<span data-ttu-id="0d822-116">Это изменение требовалось для удаления ASP.NET Core общей зависимости инфраструктуры от Roslyn.</span><span class="sxs-lookup"><span data-stu-id="0d822-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0d822-117">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="0d822-117">Recommended action</span></span>

<span data-ttu-id="0d822-118">Для приложений, требующих компиляции или перекомпиляции файлов Razor во время выполнения, требуются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0d822-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="0d822-119">добавьте ссылку на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`;</span><span class="sxs-lookup"><span data-stu-id="0d822-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="0d822-120">обновите метод `Startup.ConfigureServices` в проекте, чтобы включить вызов `AddRazorRuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="0d822-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="0d822-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="0d822-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="0d822-122">Категория</span><span class="sxs-lookup"><span data-stu-id="0d822-122">Category</span></span>

<span data-ttu-id="0d822-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0d822-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0d822-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0d822-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
