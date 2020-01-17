---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901744"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC. Асинхронный суффикс получается усечением имен действий контроллера

В системе адресации [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849) ASP.NET Core MVC по умолчанию обрезает суффиксы `Async` в именах действий. Начиная с ASP.NET Core 3,0, это изменение влияет на процессы маршрутизации и создания ссылок.

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

Действие маршрутизируется через `Product/ListAsync`. Для создания ссылки необходимо указать суффикс `Async`. Пример:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>Новое поведение

В ASP.NET Core 3,0 это действие маршрутизируется через `Product/List`. В коде создания ссылок следует опускать суффикс `Async`. Пример:

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

#### <a name="recommended-action"></a>Рекомендованное действие

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

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
