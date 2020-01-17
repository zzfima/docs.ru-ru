---
ms.openlocfilehash: 5741e8cdd51e00d5459c4c1032a56682429aab17
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902000"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a>MVC. Типы Pubternal теперь стали внутренними

В ASP.NET Core 3.0 все типы pubternal (MVC) теперь стали `public` в поддерживаемом пространстве имен либо `internal`, если это более уместно.

#### <a name="change-description"></a>Описание изменений

В ASP.NET Core типы pubternal объявляются как `public`, но находятся в пространстве имен с суффиксом `.Internal`. Хотя формально это типы `public`, для них отсутствует политика поддержки и они подвержены критическим изменениям. К сожалению, довольно часто эти типы использовались случайно, что приводило к критическим изменениям в таких проектах и ограничивало возможности, связанные с обслуживанием платформы.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Некоторые типы в MVC имели тип `public`, но существовали в пространстве имен `.Internal`. Для таких типов отсутствует политика поддержки и они подвержены критическим изменениям.

#### <a name="new-behavior"></a>Новое поведение

Все такие типы теперь стали `public` в поддерживаемом пространстве имен, либо помечены как `internal`.

#### <a name="reason-for-change"></a>Причина изменения

Довольно часто типы pubternal использовались случайно, что приводило к критическим изменениям в таких проектах и ограничивало возможности по обслуживанию платформы.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы используете типы, которые стали `public` и перемещены в новое поддерживаемое пространство имен, обновите ссылки на них соответствующим образом.

Если вы используете типы, которые стали `internal`, замените их разумной альтернативой. Общедоступное использование типов pubternal никогда не считалось поддерживаемым сценарием. Если в этих пространствах имен есть типы, которые критически важны для ваших приложений, сообщите об этой проблеме в [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues). Мы готовы рассмотреть возможность преобразовать эти типы в `public`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Это изменение затронуло следующие пространства имен:

- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

-->
