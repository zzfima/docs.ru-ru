---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901801"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a>Авторизация. IAllowAnonymous удален из AuthorizationFilterContext.Filters

Начиная с ASP.NET Core 3.0, MVC не добавляет [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) для атрибутов [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute), обнаруженных на контроллерах и методах действий. Это изменение локально адресовано для производных <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, но является критическим изменением для реализаций <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> и <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>. Такие реализации, заключенные в атрибут [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute), представляют собой [популярный](https://stackoverflow.com/a/41348219/608220) и поддерживаемый способ обеспечения строго типизированной авторизации на основе атрибутов, когда требуется настройка или внедрение зависимостей.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

<xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> отображался в коллекции [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A). Тестирование наличия интерфейса было правильным подходом к переопределению или отключению фильтра на отдельных методах контроллера.

#### <a name="new-behavior"></a>Новое поведение

`IAllowAnonymous` больше не отображается в коллекции `AuthorizationFilterContext.Filters`. Реализации `IAsyncAuthorizationFilter`, зависящие от прежнего поведения, обычно приводят к периодическим ответам HTTP "401: не санкционировано" или HTTP "403: запрещено".

#### <a name="reason-for-change"></a>Причина изменения

В ASP.NET Core 3.0 введена новая стратегия маршрутизации конечных точек.

#### <a name="recommended-action"></a>Рекомендованное действие

Поиск метаданных конечной точки для `IAllowAnonymous`. Пример:

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

Пример этой техники можно увидеть в [этом методе HasAllowAnonymous](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!--

#### Affected APIs

Not detectable via API analysis

-->
