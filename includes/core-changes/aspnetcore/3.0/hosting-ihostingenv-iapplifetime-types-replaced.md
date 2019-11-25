---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394338"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a>Размещение. Типы IHostingEnvironment и IApplicationLifetime помечены как устаревшие и удалены

Введены новые типы для замены типов `IHostingEnvironment` и `IApplicationLifetime`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

ранее существовали разные типы `IHostingEnvironment` и `IApplicationLifetime` из `Microsoft.Extensions.Hosting` и `Microsoft.AspNetCore.Hosting`.

#### <a name="new-behavior"></a>Новое поведение

Старые типы помечены как устаревшие и заменены новыми типами.

#### <a name="reason-for-change"></a>Причина изменения

Когда `Microsoft.Extensions.Hosting` был введен в ASP.NET Core 2.1, несколько типов, например `IHostingEnvironment` и `IApplicationLifetime`, были скопированы из `Microsoft.AspNetCore.Hosting`. Некоторые изменения в ASP.NET Core 3.0 привели к том, что в приложения одновременно включаются пространства имен `Microsoft.Extensions.Hosting` и `Microsoft.AspNetCore.Hosting`. Любое использование этих дублирующихся типов приводило к ошибке компилятора "двусмысленная ссылка" при использовании обоих пространств имен.

#### <a name="recommended-action"></a>Рекомендуемое действие

Замените любые использования старых типов новыми типами, как показано ниже:

**Устаревшие типы (предупреждение):**

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

**Новые типы:**

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

Новые методы расширения `IHostEnvironment` `IsDevelopment` и `IsProduction` относятся к пространству имен `Microsoft.Extensions.Hosting`. Возможно, потребуется добавить в проект это пространство имен.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
