---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901754"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>HTTP. Изменение констант HeaderNames изменены на статические только для чтения

Начиная с ASP.NET Core 3.0 (предварительная версия 5), поля в <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> изменились с `const` на `static readonly`.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Эти поля использовались для `const`.

#### <a name="new-behavior"></a>Новое поведение

Теперь эти поля являются `static readonly`.

#### <a name="reason-for-change"></a>Причина изменения

Изменение:

* предотвращает встраивание значений между границами сборки, что позволяет корректировать значения по мере необходимости.
* обеспечивает более быстрые проверки равенства ссылок.

#### <a name="recommended-action"></a>Рекомендованное действие

Выполните перекомпиляцию для версии 3.0. Исходный код, использующий эти поля следующими способами, больше не поддерживает эту возможность:

* как аргумент атрибута;
* как `case` в операторе `switch`;
* при определении `const`.

Чтобы обойти критическое изменение, переключитесь на использование самостоятельно определенных констант имен заголовков или строковых литералов.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
