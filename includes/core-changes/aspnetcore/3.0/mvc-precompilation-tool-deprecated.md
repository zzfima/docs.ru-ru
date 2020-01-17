---
ms.openlocfilehash: 1e081c9f37fbd7ab754ce44ba89d7aa5cabfc219
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901945"
---
### <a name="mvc-precompilation-tool-deprecated"></a>MVC. Средство предварительной компиляции устарело

В ASP.NET Core 1.1 был введен пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (средство предварительной компиляции MVC), чтобы организовать поддержку компиляции файлов Razor во время публикации (файлы *.cshtml*). В ASP.NET Core 2.1 добавлен [пакет SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1), который расширил возможности этого средства предварительной компиляции. Этот пакет SDK для Razor добавил поддержку компиляции файлов Razor во время сборки и публикации. Пакет SDK проверяет правильность файлов *.cshtml* во время сборки, что снижает время запуска приложения. Пакет SDK для Razor включен по умолчанию, и для его использования не требуется никаких действий.

В ASP.NET Core 3.0 было удалено средство предварительной компиляции MVC, сохранившееся с эпохи ASP.NET Core версии 1.1. Более ранние версии пакетов будут по-прежнему получать важные исправления ошибок и безопасности в выпусках исправлений.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Для предварительной компиляции представлений Razor MVC использовался пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation`.

#### <a name="new-behavior"></a>Новое поведение

Пакет SDK для Razor имеет встроенную поддержку этой возможности. Пакет `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` более не обновляется.

#### <a name="reason-for-change"></a>Причина изменения

Пакет SDK для Razor дает больше возможностей и проверяет правильность файлов *.cshtml* во время сборки. Благодаря этому пакет SDK снижает время запуска приложения.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы используете ASP.NET Core версии 2.1 или более поздней версии, обновите систему для применения встроенной поддержки предварительной компиляции в [пакете SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0). Если ошибки или отсутствующие компоненты препятствуют миграции на пакет SDK для Razor, сообщите о проблеме в [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

### Affected APIs

Not detectable via API analysis

-->
