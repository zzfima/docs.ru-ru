---
ms.openlocfilehash: 503d61cb86c83e2f32ad40c60a127ae255ef71b0
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198550"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC. Асинхронный суффикс получается усечением имен действий контроллера

В системе адресации [aspnet/AspNetCore#4849](https://github.com/aspnet/AspNetCore/issues/4849) ASP.NET Core MVC по умолчанию обрезает суффиксы `Async` из имен действий. Начиная с ASP.NET Core 3,0, это изменение влияет на процессы маршрутизации и создания ссылок.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Рассмотрим следующий контроллер ASP.NET Core MVC:

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

Действие маршрутизируется через `Product/ListAsync`. Для создания ссылки необходимо указать суффикс `Async`. Например:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>Новое поведение

В ASP.NET Core 3,0 это действие маршрутизируется через `Product/List`. В коде создания ссылок следует опускать суффикс `Async`. Например:

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

Это изменение не влияет на имена, указанные с атрибутом `[ActionName]`. Это поведение можно отключить, присвоив свойству `MvcOptions.SuppressAsyncSuffixInActionNames` значение `false` в `Startup.ConfigureServices`:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a>Причина изменения

По соглашению асинхронные методы .NET получают суффиксы `Async`. Но если метод определяет действие MVC, нежелательно использовать суффикс `Async`.

#### <a name="recommended-action"></a>Рекомендуемое действие

Если приложение зависит от того, сохранит ли действие MVC суффикс имени `Async`, выберите один из следующих способов устранения рисков:

- примените атрибут `[ActionName]`, чтобы сохранить исходное имя;
- полностью отключите переименование, задав для `MvcOptions.SuppressAsyncSuffixInActionNames` значение `false` в `Startup.ConfigureServices`:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
