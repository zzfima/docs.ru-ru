---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394234"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor. Компиляция во время выполнения перемещена в пакет

Компиляция во время выполнения представлений Razor и Razor Pages перемещена в отдельный пакет.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Компиляция во время выполнения не требует дополнительных пакетов.

#### <a name="new-behavior"></a>Новое поведение

Функциональные возможности перемещены в пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

Следующие API ранее были доступны в `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` для поддержки компиляции во время выполнения. Теперь эти API доступны через `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Кроме того, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` теперь не используется. Повторная компиляция с учетом изменения файлов включена по умолчанию с использованием ссылки на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение требовалось для удаления ASP.NET Core общей зависимости инфраструктуры от Roslyn.

#### <a name="recommended-action"></a>Рекомендуемое действие

Для приложений, требующих компиляции или перекомпиляции файлов Razor во время выполнения, требуются следующие действия:

1. добавьте ссылку на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`;
1. обновите метод `Startup.ConfigureServices` в проекте, чтобы включить вызов `AddMvcRazorRuntimeCompilation`. Например, для `Startup.ConfigureServices`:

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
