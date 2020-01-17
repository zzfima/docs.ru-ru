---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901873"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC. JsonResult перемещен в Microsoft.AspNetCore.Mvc.Core

`JsonResult` перемещен в сборку `Microsoft.AspNetCore.Mvc.Core`. Этот тип используется для определения в [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json). Чтобы устранить эту ошибку для большинства пользователей, атрибут уровня сборки [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) добавлен в `Microsoft.AspNetCore.Mvc.Formatters.Json`. В приложениях, использующих сторонние библиотеки, могут возникать проблемы.

#### <a name="version-introduced"></a>Представленная версия

6 предварительная версия 3.0

#### <a name="old-behavior"></a>Старое поведение

Сборка приложения, использующего библиотеку на основе версии 2.2, проходит успешно.

#### <a name="new-behavior"></a>Новое поведение

Приложение, использующее библиотеку на основе версии 2.2 не может выполнить компиляцию. Указана ошибка, содержащая разновидность следующего текста:

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Пример такой проблемы см. в разделе [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).

#### <a name="reason-for-change"></a>Причина изменения

Изменения на уровне платформы для композиции ASP.NET Core, как описано в разделе [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).

#### <a name="recommended-action"></a>Рекомендованное действие

Чтобы устранить проблему для всех потребителей, для библиотек, скомпилированных `Microsoft.AspNetCore.Mvc.Formatters.Json` версии 2.2, может потребоваться повторная компиляция. Если это произошло, обратитесь к автору библиотеки. Запросите перекомпиляцию библиотеки в целевой ASP.NET Core 3.0.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
