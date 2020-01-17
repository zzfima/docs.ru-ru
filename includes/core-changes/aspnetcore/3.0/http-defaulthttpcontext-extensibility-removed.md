---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901606"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP. Удаление расширяемости DefaultHttpContext

В рамках повышения производительности ASP.NET Core 3.0 расширяемость `DefaultHttpContext` была удалена. Теперь класс является `sealed`. Подробную информацию см. на странице [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).

Если модульные тесты используют `Mock<DefaultHttpContext>`, используйте вместо этого `Mock<HttpContext>`.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Классы могут быть производными от `DefaultHttpContext`.

#### <a name="new-behavior"></a>Новое поведение

Классы не могут быть производными от `DefaultHttpContext`.

#### <a name="reason-for-change"></a>Причина изменения

Изначально была предоставлена расширяемость, позволяющая выполнять группировку `HttpContext`, но в ней появились ненужные сложности и другие нарушения, влияющие на оптимизацию.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы используете `Mock<DefaultHttpContext>` в модульных тестах, используйте вместо этого `Mock<HttpContext>`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
