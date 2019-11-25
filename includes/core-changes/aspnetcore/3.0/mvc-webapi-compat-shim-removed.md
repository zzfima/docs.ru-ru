---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393896"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a>MVC. Удалена оболочка совместимости веб-API

Начиная с пакета SDK для .NET Core 3.0, пакет `Microsoft.AspNetCore.Mvc.WebApiCompatShim` недоступен.

#### <a name="change-description"></a>Описание изменений

Пакет `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) обеспечивает в ASP.NET Core частичную совместимость с веб-API 2 для ASP.NET 4.x, чтобы упростить миграцию существующих реализаций веб-API на ASP.NET Core. Но при этом приложения, которые используют WebApiCompatShim, не могут воспользоваться функциями API из последних выпусков ASP.NET Core. Сюда относятся, среди прочего, улучшенное создание спецификаций Open API, стандартизованная обработка ошибок и создание клиентского кода. Чтобы уделить больше внимания развитию API в версии 3.0, WebApiCompatShim удален. Существующие приложения, которые используют WebApiCompatShim, необходимо перевести на новую модель `[ApiController]`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Оболочка совместимости веб-API являлась временным инструментом для миграции. Она ограничивает доступ пользователей к новым функциям, добавляемым в ASP.NET Core.

#### <a name="recommended-action"></a>Рекомендуемое действие

Прекратите использование оболочки и переходите сразу к использованию аналогичных функций в ASP.NET Core.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
