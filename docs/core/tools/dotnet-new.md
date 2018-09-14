---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512559"
---
# <a name="dotnet-new"></a>dotnet new

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a>Описание:

Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.

Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.

## <a name="arguments"></a>Аргументы

`TEMPLATE`

Шаблон для создания экземпляров при вызове команды. Каждый шаблон может иметь отдельные параметры, доступные для передачи. Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

Команда содержит список шаблонов по умолчанию. Используйте `dotnet new -l`, чтобы получить список доступных шаблонов. В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300. Язык по умолчанию для шаблона указан внутри квадратных скобок.

|Описание шаблона                          | Имя шаблона   | Языки     |
|----------------------------------------------|-----------------|---------------|
| Консольное приложение                          | `console`       | [C#], F#, VB  |
| Библиотека классов                                | `classlib`      | [C#], F#, VB  |
| Проект модульного теста                            | `mstest`        | [C#], F#, VB  |
| Проект теста xUnit                           | `xunit`         | [C#], F#, VB  |
| Страница Razor                                   | `page`          | [C#]          |
| MVC ViewImports                              | `viewimports`   | [C#]          |
| MVC ViewStart                                | `viewstart`     | [C#]          |
| Пустой ASP.NET Core                           | `web`           | [C#], F#      |
| Веб-приложение ASP.NET Core (Model-View-Controller) | `mvc`           | [C#], F#      |
| Веб-приложение ASP.NET Core                         | `razor`         | [C#]          |
| ASP.NET Core с Angular                    | `angular`       | [C#]          |
| ASP.NET Core с React.js                   | `react`         | [C#]          |
| ASP.NET Core с React.js и Redux         | `reactredux`    | [C#]          |
| Веб-API ASP.NET Core                         | `webapi`        | [C#], F#      |
| Библиотека классов Razor                          | `razorclasslib` | [C#]          |
| Файл global.json                             | `globaljson`    |               |
| Конфигурация NuGet                                 | `nugetconfig`   |               |
| Веб-конфигурация                                   | `webconfig`     |               |
| Файл решения                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

Команда содержит список шаблонов по умолчанию. Используйте `dotnet new -l`, чтобы получить список доступных шаблонов. В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0. Язык по умолчанию для шаблона указан внутри квадратных скобок.

|Описание шаблона                          | Имя шаблона | Языки     |
|----------------------------------------------|---------------|---------------|
| Консольное приложение                          | `console`     | [C#], F#, VB  |
| Библиотека классов                                | `classlib`    | [C#], F#, VB  |
| Проект модульного теста                            | `mstest`      | [C#], F#, VB  |
| Проект теста xUnit                           | `xunit`       | [C#], F#, VB  |
| Пустой ASP.NET Core                           | `web`         | [C#], F#      |
| Веб-приложение ASP.NET Core (Model-View-Controller) | `mvc`         | [C#], F#      |
| Веб-приложение ASP.NET Core                         | `razor`       | [C#]          |
| ASP.NET Core с Angular                    | `angular`     | [C#]          |
| ASP.NET Core с React.js                   | `react`       | [C#]          |
| ASP.NET Core с React.js и Redux         | `reactredux`  | [C#]          |
| Веб-API ASP.NET Core                         | `webapi`      | [C#], F#      |
| Файл global.json                             | `globaljson`  |               |
| Конфигурация NuGet                                 | `nugetconfig` |               |
| Веб-конфигурация                                   | `webconfig`   |               |
| Файл решения                                | `sln`         |               |
| Страница Razor                                   | `page`        |               |
| MVC ViewImports                              | `viewimports` |               |
| MVC ViewStart                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Команда содержит список шаблонов по умолчанию. Используйте `dotnet new -all`, чтобы получить список доступных шаблонов. В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x. Язык по умолчанию для шаблона указан внутри квадратных скобок.

|Описание шаблона  | Имя шаблона | Языки |
|----------------------|---------------|-----------|
| Консольное приложение  | `console`     | [C#], F#  |
| Библиотека классов        | `classlib`    | [C#], F#  |
| Проект модульного теста    | `mstest`      | [C#], F#  |
| Проект теста xUnit   | `xunit`       | [C#], F#  |
| Пустой ASP.NET Core   | `web`         | [C#]      |
| Веб-приложение ASP.NET Core | `mvc`         | [C#], F#  |
| Веб-API ASP.NET Core | `webapi`      | [C#]      |
| Конфигурация NuGet         | `nugetconfig` |           |
| Веб-конфигурация           | `webconfig`   |           |
| Файл решения        | `sln`         |           |

---

## <a name="options"></a>Параметры

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--force`

Принудительное создание содержимого, даже если при этом изменяются существующие файлы. Это требуется, когда выходной каталог уже содержит проект.

`-h|--help`

Распечатывает справку для команды. Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`. Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`. По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета. См. пример в разделе [Примеры](#examples).

Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).

`-l|--list`

Перечисляет шаблоны с указанным именем. При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога. Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.

`-lang|--language {C#|F#|VB}`

Язык создаваемого шаблона. Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)). Не является допустимым для некоторых шаблонов.

> [!NOTE]
> Некоторые оболочки интерпретируют `#` как специальный символ. В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Имя создаваемых выходных данных. Если имя не указано, используется имя текущего каталога.

`--nuget-source`

Задает источник пакетов NuGet для использования во время установки.

`-o|--output <OUTPUT_DIRECTORY>`

Расположение, в котором размещаются созданные выходные данные. Значением по умолчанию является текущий каталог.

`--type`

Фильтрует шаблоны по доступным типам. Предварительно определенные значения: project, item и other.

`-u|--uninstall <PATH|NUGET_ID>`

Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.

> [!NOTE]
> Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь. Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.
> Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--force`

Принудительное создание содержимого, даже если при этом изменяются существующие файлы. Это требуется, когда выходной каталог уже содержит проект.

`-h|--help`

Распечатывает справку для команды. Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`. Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`. По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета. См. пример в разделе [Примеры](#examples).

Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).

`-l|--list`

Перечисляет шаблоны с указанным именем. При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога. Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.

`-lang|--language {C#|F#|VB}`

Язык создаваемого шаблона. Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)). Не является допустимым для некоторых шаблонов.

> [!NOTE]
> Некоторые оболочки интерпретируют `#` как специальный символ. В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Имя создаваемых выходных данных. Если имя не указано, используется имя текущего каталога.

`-o|--output <OUTPUT_DIRECTORY>`

Расположение, в котором размещаются созданные выходные данные. Значением по умолчанию является текущий каталог.

`--type`

Фильтрует шаблоны по доступным типам. Предварительно определенные значения: project, item и other.

`-u|--uninstall <PATH|NUGET_ID>`

Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.

> [!NOTE]
> Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь. Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.
> Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-all|--show-all`

Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`. При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания. Это требуется, когда выходной каталог уже содержит проект.

`-h|--help`

Распечатывает справку для команды. Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.

`-l|--list`

Перечисляет шаблоны с указанным именем. При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога. Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.

`-lang|--language {C#|F#}`

Язык создаваемого шаблона. Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)). Не является допустимым для некоторых шаблонов.

> [!NOTE]
> Некоторые оболочки интерпретируют `#` как специальный символ. В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Имя создаваемых выходных данных. Если имя не указано, используется имя текущего каталога.

`-o|--output <OUTPUT_DIRECTORY>`

Расположение, в котором размещаются созданные выходные данные. Значением по умолчанию является текущий каталог.

---

## <a name="template-options"></a>Параметры шаблона

Каждый шаблон проекта может содержать дополнительные доступные параметры. Основные шаблоны имеют следующие дополнительные параметры:

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

**console, angular, react, reactredux, razorclasslib**

  `--no-restore` — во время создания проекта не выполняется неявное восстановление.

**classlib**

`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md). Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET. Значение по умолчанию — `netstandard2.0`.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**mstest, xunit**

`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**globaljson**

`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.

**web**

`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

`--no-https` — проекту не требуется HTTPS. Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности. Допустимые значения:

- `None` — без проверки подлинности (по умолчанию).
- `IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.
- `SingleOrg` — проверка подлинности организации для отдельного клиента.
- `Windows` — проверка подлинности Windows.

`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение. Используется с проверкой подлинности `IndividualB2C`. Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение. Используется с проверкой подлинности `SingleOrg`. Значение по умолчанию — `https://login.microsoftonline.com/`.

`--client-id <ID>` — идентификатор клиента для этого проекта. Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`. Значение по умолчанию — `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>` — домен клиента каталога. Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`. Значение по умолчанию — `qualified.domain.name`.

`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение. Используется с проверкой подлинности `SingleOrg`. Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения. Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.

`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.

`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB. Применяется только при проверке подлинности `Individual` или `IndividualB2C`.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

`--no-https` — проекту не требуется HTTPS. `app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`. Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности. Допустимые значения:

- `None` — без проверки подлинности (по умолчанию).
- `Individual` — индивидуальная проверка подлинности.
- `IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.
- `SingleOrg` — проверка подлинности организации для отдельного клиента.
- `MultiOrg` — проверка подлинности организации для нескольких клиентов.
- `Windows` — проверка подлинности Windows.

`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение. Используется с проверкой подлинности `IndividualB2C`. Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение. Используется с проверкой подлинности `SingleOrg` или `MultiOrg`. Значение по умолчанию — `https://login.microsoftonline.com/`.

`--client-id <ID>` — идентификатор клиента для этого проекта. Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`. Значение по умолчанию — `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>` — домен клиента каталога. Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`. Значение по умолчанию — `qualified.domain.name`.

`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение. Используется с проверкой подлинности `SingleOrg`. Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения. Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`. Значение по умолчанию — `/signin-oidc`.

`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения. Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.

`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.

`--use-browserlink` — включает BrowserLink в проект.

`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB. Применяется только при проверке подлинности `Individual` или `IndividualB2C`.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

`--no-https` — проекту не требуется HTTPS. `app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`. Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.

**page**

`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода. Значение по умолчанию — `MyApp.Namespace`.

`-np|--no-pagemodel` — создает страницу без PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода. Значение по умолчанию — `MyApp.Namespace`.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

**console, angular, react, reactredux**

  `--no-restore` — во время создания проекта не выполняется неявное восстановление.

**classlib**

`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md). Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET. Значение по умолчанию — `netstandard2.0`.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**mstest, xunit**

`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**globaljson**

`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.

**web**

`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности. Допустимые значения:

- `None` — без проверки подлинности (по умолчанию).
- `IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.
- `SingleOrg` — проверка подлинности организации для отдельного клиента.
- `Windows` — проверка подлинности Windows.

`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение. Используется с проверкой подлинности `IndividualB2C`. Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение. Используется с проверкой подлинности `SingleOrg`. Значение по умолчанию — `https://login.microsoftonline.com/`.

`--client-id <ID>` — идентификатор клиента для этого проекта. Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`. Значение по умолчанию — `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>` — домен клиента каталога. Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`. Значение по умолчанию — `qualified.domain.name`.

`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение. Используется с проверкой подлинности `SingleOrg`. Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения. Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.

`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.

`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB. Применяется только при проверке подлинности `Individual` или `IndividualB2C`.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности. Допустимые значения:

- `None` — без проверки подлинности (по умолчанию).
- `Individual` — индивидуальная проверка подлинности.
- `IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.
- `SingleOrg` — проверка подлинности организации для отдельного клиента.
- `MultiOrg` — проверка подлинности организации для нескольких клиентов.
- `Windows` — проверка подлинности Windows.

`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение. Используется с проверкой подлинности `IndividualB2C`. Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта. Используется с проверкой подлинности `IndividualB2C`.

`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение. Используется с проверкой подлинности `SingleOrg` или `MultiOrg`. Значение по умолчанию — `https://login.microsoftonline.com/`.

`--client-id <ID>` — идентификатор клиента для этого проекта. Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`. Значение по умолчанию — `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>` — домен клиента каталога. Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`. Значение по умолчанию — `qualified.domain.name`.

`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение. Используется с проверкой подлинности `SingleOrg`. Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения. Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`. Значение по умолчанию — `/signin-oidc`.

`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения. Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.

`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.

`--use-browserlink` — включает BrowserLink в проект.

`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB. Применяется только при проверке подлинности `Individual` или `IndividualB2C`.

`--no-restore` — во время создания проекта не выполняется неявное восстановление.

**page**

`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода. Значение по умолчанию — `MyApp.Namespace`.

`-np|--no-pagemodel` — создает страницу без PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода. Значение по умолчанию — `MyApp.Namespace`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**console, xunit, mstest, web, webapi**

`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md). Значения: `netcoreapp1.0` или `netcoreapp1.1`. Значение по умолчанию — `netcoreapp1.0`.

**classlib**

`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md). Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`. Значение по умолчанию — `netstandard1.4`.

**mvc**

`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md). Значения: `netcoreapp1.0` или `netcoreapp1.1`. Значение по умолчанию — `netcoreapp1.0`.

`-au|--auth` — тип проверки подлинности. Значения: `None` или `Individual`. Значение по умолчанию — `None`.

`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite. Значения: `true` или `false`. Значение по умолчанию — `false`.

---

## <a name="examples"></a>Примеры

Создание проекта консольного приложения F# в текущем каталоге:

`dotnet new console -lang F#`

Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):

`dotnet new classlib -lang VB -o MyLibrary`

Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:

`dotnet new mvc -au None`

Создание нового приложения xUnit:

`dotnet new xunit`

Перечислите все шаблоны, доступные для MVC:

`dotnet new mvc -l`

Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a>См. также

* [Пользовательские шаблоны для команды dotnet new](custom-templates.md)  
* [Создание пользовательского шаблона для dotnet](~/docs/core/tutorials/create-custom-template.md)  
* [Репозиторий dotnet/dotnet-template-samples в GitHub](https://github.com/dotnet/dotnet-template-samples)  
* [Доступные шаблоны для команды dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
