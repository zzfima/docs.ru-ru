---
ms.openlocfilehash: 3f702febc78488b9413ec9303ded211493650f02
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198553"
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

#### <a name="recommended-action"></a>Рекомендуемое действие

Если вы используете ASP.NET Core версии 2.1 или более поздней версии, обновите систему для применения встроенной поддержки предварительной компиляции в [пакете SDK для Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0). Если ошибки или отсутствующие компоненты препятствуют миграции на пакет SDK для Razor, сообщите о проблеме а [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

### Affected APIs

Not detectable via API analysis

-->
