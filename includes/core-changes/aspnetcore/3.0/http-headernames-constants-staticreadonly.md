---
ms.openlocfilehash: e0d0a680915f14c2d33f1864ad5ad05aff3dde5f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394079"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>HTTP. Изменение констант HeaderNames изменены на статические только для чтения

Начиная с ASP.NET Core 3.0 (предварительная версия 5), поля в <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> изменились с `const` на `static readonly`.

Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#9514](https://github.com/aspnet/AspNetCore/issues/9514).

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

#### <a name="recommended-action"></a>Рекомендуемое действие

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
