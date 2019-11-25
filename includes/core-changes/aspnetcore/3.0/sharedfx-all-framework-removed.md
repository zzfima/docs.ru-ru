---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394438"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a>Общая платформа. Удаление Microsoft.AspNetCore.All

Начиная с ASP.NET Core 3.0, метапакет `Microsoft.AspNetCore.All` и соответствующая общая платформа `Microsoft.AspNetCore.All` больше не создаются. Этот пакет доступен в ASP.NET Core 2.2 и по-прежнему будет принимать обновления для обслуживания в ASP.NET Core 2.1.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Приложения могут использовать метапакет `Microsoft.AspNetCore.All` для целевой общей платформы `Microsoft.AspNetCore.All` в .NET Core.

#### <a name="new-behavior"></a>Новое поведение

.NET Core 3.0 не содержит общую платформу `Microsoft.AspNetCore.All`.

#### <a name="reason-for-change"></a>Причина изменения

Метапакет `Microsoft.AspNetCore.All` включал большое количество внешних зависимостей.

#### <a name="recommended-action"></a>Рекомендуемое действие

Перенесите проект для использования платформы `Microsoft.AspNetCore.App`. Компоненты, которые ранее были доступны в `Microsoft.AspNetCore.All`, по-прежнему будут доступными в NuGet. Теперь эти компоненты развертываются вместе с приложением, а не включаются в общую платформу.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
