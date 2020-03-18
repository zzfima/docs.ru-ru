---
ms.openlocfilehash: c5e4b5619394f99a419fe48aee190ad741ea8c0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73041663"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>Удостоверение. Пользовательский интерфейс использует функцию статических веб-ресурсов

В ASP.NET Core 3.0 появился статический компонент веб-ресурсов, и он поддерживается пользовательским интерфейсом удостоверений.

#### <a name="change-description"></a>Описание изменений

Внедрение функции статических веб-ресурсов в пользовательский интерфейс удостоверений принесло следующие результаты.

- Выбор платформы осуществляется с помощью свойства `IdentityUIFrameworkVersion` в файле проекта.
- Bootstrap 4 является инфраструктурой пользовательского интерфейса по умолчанию для пользовательского интерфейса удостоверений. Bootstrap 3 достигла конца жизненного цикла, и мы рекомендуем перейти на поддерживаемую версию.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Инфраструктурой пользовательского интерфейса по умолчанию для пользовательского интерфейса удостоверений была **Bootstrap 3**. Для платформы пользовательского интерфейса можно настроить параметр вызова метода `AddDefaultUI` в `Startup.ConfigureServices`.

#### <a name="new-behavior"></a>Новое поведение

Инфраструктурой пользовательского интерфейса по умолчанию для пользовательского интерфейса удостоверений является **Bootstrap 4**. Платформа пользовательского интерфейса должна настраиваться в файле проекта, а не в вызове метода `AddDefaultUI`.

#### <a name="reason-for-change"></a>Причина изменения

Внедрение функции статических веб-ресурсов, которое потребовало переноса конфигурация платформы пользовательского интерфейса в MSBuild. Решение о том, какая платформа будет внедрена, является решением времени сборки, а не среды выполнения.

#### <a name="recommended-action"></a>Рекомендованное действие

Проверьте пользовательский интерфейс сайта, чтобы убедиться, что новые компоненты Bootstrap 4 совместимы. При необходимости используйте свойство MSBuild `IdentityUIFrameworkVersion`, чтобы вернуться к Bootstrap 3. Добавьте свойство в элемент `<PropertyGroup>` в файле проекта:

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
