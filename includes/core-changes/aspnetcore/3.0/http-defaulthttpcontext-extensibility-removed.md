---
ms.openlocfilehash: 7b5ae84d02b83a10a4b9e002fc2ed4ee0833b84c
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198554"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP. Удаление расширяемости DefaultHttpContext

В рамках повышения производительности ASP.NET Core 3.0 расширяемость `DefaultHttpContext` была удалена. Теперь класс является `sealed`. Подробную информацию см. на странице [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).

Если модульные тесты используют `Mock<DefaultHttpContext>`, используйте вместо этого `Mock<HttpContext>`.

Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Классы могут быть производными от `DefaultHttpContext`.

#### <a name="new-behavior"></a>Новое поведение

Классы не могут быть производными от `DefaultHttpContext`.

#### <a name="reason-for-change"></a>Причина изменения

Изначально была предоставлена расширяемость, позволяющая выполнять группировку `HttpContext`, но в ней появились ненужные сложности и другие нарушения, влияющие на оптимизацию.

#### <a name="recommended-action"></a>Рекомендуемое действие

Если вы используете `Mock<DefaultHttpContext>` в модульных тестах, используйте вместо этого `Mock<HttpContext>`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
