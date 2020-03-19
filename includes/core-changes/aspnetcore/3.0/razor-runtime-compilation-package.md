---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344281"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor. Компиляция во время выполнения перемещена в пакет

Компиляция во время выполнения представлений Razor и Razor Pages перемещена в отдельный пакет.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Компиляция во время выполнения не требует дополнительных пакетов.

#### <a name="new-behavior"></a>Новое поведение

Функциональные возможности перенесены в пакет [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/).

Следующие API ранее были доступны в `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` для поддержки компиляции во время выполнения. Теперь эти API доступны через `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.

- `RazorViewEngineOptions.FileProviders` изменено на `MvcRazorRuntimeCompilationOptions.FileProviders`.
- `RazorViewEngineOptions.AdditionalCompilationReferences` изменено на `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`.

Кроме того, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` теперь не используется. Повторная компиляция с учетом изменения файлов включена по умолчанию с использованием ссылки на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение требовалось для удаления ASP.NET Core общей зависимости инфраструктуры от Roslyn.

#### <a name="recommended-action"></a>Рекомендованное действие

Для приложений, требующих компиляции или перекомпиляции файлов Razor во время выполнения, требуются следующие действия:

1. добавьте ссылку на пакет `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`;
1. обновите метод `Startup.ConfigureServices` в проекте, чтобы включить вызов `AddRazorRuntimeCompilation`. Пример:

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
