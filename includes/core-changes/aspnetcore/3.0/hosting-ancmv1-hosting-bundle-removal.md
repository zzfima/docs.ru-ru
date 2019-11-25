---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394294"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Размещение. Модуль AspNetCoreModule версии 1 не входит в пакет размещения Windows

Начиная с ASP.NET Core 3.0, пакет размещения Windows не будет содержать AspNetCoreModule (ANCM) версии 1.

ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.

Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

ANCM версии 1 входит в состав пакета размещения Windows.

#### <a name="new-behavior"></a>Новое поведение

ANCM версии 1 не входит в состав пакета размещения Windows.

#### <a name="reason-for-change"></a>Причина изменения

ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Рекомендуемое действие

Используйте ANCM версии 2 с приложениями ASP.NET Core 3.0.

Если требуется ANCM версии 1, выполните установку с помощью пакета размещения Windows ASP.NET Core 2.1 или 2.2.

Это изменение приведет к нарушению работы приложений ASP.NET Core 3.0, которые:

- явно настроены использовать ANCM версии 1 с `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`;
- имеют пользовательский файл *web.config* с `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
