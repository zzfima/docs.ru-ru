---
ms.openlocfilehash: 8344fdedcff34f102b73f977b688abc15563bd4c
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198555"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a>Общая платформа. Из Microsoft.AspNetCore.App удалены сборки

Начиная с ASP.NET Core версии 3.0 общая платформа ASP.NET Core (`Microsoft.AspNetCore.App`) содержит только сборки, которые полностью разработаны, поддерживаются и обслуживаются корпорацией Майкрософт.

#### <a name="change-description"></a>Описание изменений

Это изменение следует рассматривать как переопределение границ для понятия "платформа ASP.NET Core". Общую платформу [любой желающий может собрать из исходного кода, размещенного в репозитории GitHub](https://github.com/dotnet/source-build), и она по-прежнему предоставляет вашим приложениям все существующие преимущества общих платформ .NET Core. К таким преимуществам относятся меньший размер развертывания, централизованная установка исправлений и сокращенное время запуска.

В рамках этого обновления в `Microsoft.AspNetCore.App` добавлены несколько критических изменений.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Проекты ссылались на `Microsoft.AspNetCore.App` через элемент `<PackageReference>` в файле проекта.

Кроме того, в `Microsoft.AspNetCore.App` содержались следующие вложенные компоненты:

- Json.NET (`Newtonsoft.Json`);
- Entity Framework Core (сборки с префиксом `Microsoft.EntityFrameworkCore.`);
- Roslyn (`Microsoft.CodeAnalysis`).

#### <a name="new-behavior"></a>Новое поведение

Ссылка на `Microsoft.AspNetCore.App` теперь не требует наличия элемента `<PackageReference>` в файле проекта. Пакет SDK для .NET Core поддерживает новый элемент с именем `<FrameworkReference>`, который заменяет собой `<PackageReference>`.

Подробную информацию см. на странице [aspnet/AspNetCore#3612](https://github.com/aspnet/AspNetCore/issues/3612).

Entity Framework Core поставляется в формате пакетов NuGet. Это обновление приводит модель поставки в соответствие со схемой, принятой для всех остальных библиотек доступа к данным в .NET. Теперь в Entity Framework Core доступен самый простой способ продолжать разработку инноваций, пользуясь поддержкой любых платформ .NET. Несмотря на отделение от общей платформы Entity Framework Core остается библиотекой, разработанной, поддерживаемой и обслуживаемой корпорацией Майкрософт. На нее по-прежнему распространяется [политика поддержки .NET Core](https://www.microsoft.com/net/platform/support-policy).

Json.NET и Entity Framework Core будут и дальше работать с ASP.NET Core. Но теперь они не будут входить в состав общей платформы.

Дополнительные сведения см. в статье [о перспективах для JSON в .NET Core 3.0](https://github.com/dotnet/announcements/issues/90). Также обратите внимание на то, что из общей платформы удален [большой список двоичных файлов](https://github.com/aspnet/AspNetCore/issues/3755).

#### <a name="reason-for-change"></a>Причина изменения

Это изменение упрощает использование `Microsoft.AspNetCore.App` и сокращает дублирование функций между пакетами NuGet и общими платформами.

Дополнительные сведения о том, что подтолкнуло нас к этим изменениям, см. в [этой записи блога](https://blogs.msdn.microsoft.com/webdev/2018/10/29/a-first-look-at-changes-coming-in-asp-net-core-3-0).

#### <a name="recommended-action"></a>Рекомендуемое действие

Сборки в `Microsoft.AspNetCore.App` не обязательно используются в проектах именно в виде пакетов NuGet. Чтобы упростить нацеливание и использование общей платформы ASP.NET Core, многие пакеты NuGet, подготовленные с момента выхода ASP.NET Core 1.0, больше не выпускаются. API-интерфейсы, которые предоставлялись в этих пакетах, по-прежнему можно использовать из приложений с помощью ссылки `<FrameworkReference>` на `Microsoft.AspNetCore.App`. Сюда относятся, например, довольно популярные API Kestrel, MVC и Razor.

Это изменение не затрагивает двоичные файлы, которые указываются через `Microsoft.AspNetCore.App` в ASP.NET Core 2.x. Несколько важных исключений:

- Библиотеки `Microsoft.Extensions`, которые по-прежнему нацеливаются на .NET Standard, будут доступны в виде пакетов NuGet (см. https://github.com/aspnet/Extensions).
- API-интерфейсы, которые выпускаются командой разработчиков ASP.NET Core и не входят в `Microsoft.AspNetCore.App`. Например, в формате пакетов NuGet предоставляются следующие компоненты:
  - Entity Framework Core
  - API-интерфейсы, которые обеспечивают интеграцию с решениями сторонних разработчиков;
  - экспериментальные функции;
  - API-интерфейсы с зависимостями, которые не позволяют [выполнить требования для включения в общую платформу](https://github.com/aspnet/AspNetCore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md).
- Расширения MVC, которые сохраняют поддержку Json.NET. API-интерфейс будет предоставляться в виде пакета NuGet для поддержки работы с Json.NET и MVC.
- Клиент SignalR .NET будет и далее поддерживать .NET Standard, а поставляться в виде пакета NuGet. Он нужен для многих сред выполнения .NET, включая Xamarin и UWP.

Подробные сведения см. в объявлении [о прекращении выпуска пакетов для сборок общей платформы начиная с версии 3.0](https://github.com/aspnet/AspNetCore/issues/3756). Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#3757](https://github.com/aspnet/AspNetCore/issues/3757).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
