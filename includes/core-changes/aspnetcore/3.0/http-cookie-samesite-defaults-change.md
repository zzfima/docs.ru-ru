---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74282523"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a>HTTP. Некоторые значения по умолчанию параметра SameSite для файлов cookie изменены на None

`SameSite` — это параметр для файлов cookie, который помогает предотвращать некоторые атаки с подделкой межсайтовых запросов. Когда этот параметр изначально появился, в разных интерфейсах API ASP.NET Core использовались несогласованные значения по умолчанию. Это приводило к путанице в результатах. Начиная с версии ASP.NET Core 3.0, значения по умолчанию стали более согласованными. Эту функцию необходимо включать отдельно для каждого метода.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

В похожих интерфейсах API ASP.NET Core использовались разные значения по умолчанию параметра <xref:Microsoft.AspNetCore.Http.SameSiteMode>. Примером несогласованности могут служить методы `HttpResponse.Cookies.Append(String, String)` и `HttpResponse.Cookies.Append(String, String, CookieOptions)` со значениями по умолчанию `SameSiteMode.None` и `SameSiteMode.Lax`соответственно.

#### <a name="new-behavior"></a>Новое поведение

Во всех затронутых интерфейсах API по умолчанию используется значение `SameSiteMode.None`.

#### <a name="reason-for-change"></a>Причина изменения

Значение по умолчанию было изменено, чтобы сделать функцию `SameSite` необязательной.

#### <a name="recommended-action"></a>Рекомендованное действие

Для каждого компонента, создающего файлы cookie, необходимо принять решение об использовании параметра `SameSite`. Проверьте использование затронутых интерфейсов API и при необходимости перенастройте параметр `SameSite`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
