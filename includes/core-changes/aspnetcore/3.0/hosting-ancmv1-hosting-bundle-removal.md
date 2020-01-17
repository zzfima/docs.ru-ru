---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901910"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Размещение. Модуль AspNetCoreModule версии 1 не входит в пакет размещения Windows

Начиная с ASP.NET Core 3.0, пакет размещения Windows не будет содержать AspNetCoreModule (ANCM) версии 1.

ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

ANCM версии 1 входит в состав пакета размещения Windows.

#### <a name="new-behavior"></a>Новое поведение

ANCM версии 1 не входит в состав пакета размещения Windows.

#### <a name="reason-for-change"></a>Причина изменения

ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Рекомендованное действие

Используйте ANCM версии 2 с приложениями ASP.NET Core 3.0.

Если требуется ANCM версии 1, выполните установку с помощью пакета размещения Windows ASP.NET Core 2.1 или 2.2.

Это изменение приведет к нарушению работы приложений ASP.NET Core 3.0, которые:

- явно настроены использовать ANCM версии 1 с `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`;
- имеют пользовательский файл *web.config* с `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
