---
ms.openlocfilehash: da1ec7908b3082fc61313cb805773aa600bc1b5d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393931"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>Локализация. ResourceManagerWithCultureStringLocalizer и WithCulture отмечены как устаревшие

Класс [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) и член-интерфейс [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) часто становились причиной путаницы для пользователей при локализации, особенно при создании собственной реализации `IStringLocalizer`. Эти элементы создают у пользователей ощущение, что экземпляр `IStringLocalizer` создается отдельно для каждого языка и каждого ресурса. На самом деле экземпляры различаются только для ресурсов. Искомый язык определяется `CultureInfo.CurrentUICulture` во время выполнения. Чтобы устранить источник путаницы, эти API помечены как устаревшие в выпуске ASP.NET Core 3.0 предварительной версии 3. Эти API будут удалены в будущем выпуске.

Контекст этого вопроса описан на странице [aspnet/AspNetCore#3324](https://github.com/aspnet/AspNetCore/issues/3324). Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#7756](https://github.com/aspnet/AspNetCore/issues/7756).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Методы не имели отметки `Obsolete`.

#### <a name="new-behavior"></a>Новое поведение

Методы получили отметку `Obsolete`.

#### <a name="reason-for-change"></a>Причина изменения

Эти API представляли нерекомендованный вариант использования. Они создавали путаницу в отношении структуры локализации.

#### <a name="recommended-action"></a>Рекомендуемое действие

Основная рекомендация: использовать вместо них `ResourceManagerStringLocalizer`. Язык и региональные параметры должны устанавливаться в `CurrentCulture`. Если это невозможно, создайте и примените копию [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
