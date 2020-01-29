---
title: Команда dotnet
description: Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании.
ms.date: 06/04/2018
ms.openlocfilehash: fe90968560b58471c279fcd2097741ea476cef0b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734063"
---
# <a name="dotnet-command"></a>Команда dotnet

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet` — средство для управления исходным кодом .NET и двоичными объектами.

## <a name="synopsis"></a>Краткий обзор

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a>Описание

`dotnet` — это средство для управления исходным кодом .NET и двоичными объектами. Он предоставляет команды, выполняющие определенные задачи, такие как [`dotnet build`](dotnet-build.md) и [`dotnet run`](dotnet-run.md). Каждая команда определяет свои аргументы. Введите `--help` после каждой команды для доступа к краткой справочной документации.

`dotnet` можно использовать для запуска приложений путем указания библиотеки DLL приложения, например `dotnet myapp.dll`. Дополнительные сведения о параметрах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).

## <a name="options"></a>Параметры

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--additional-deps <PATH>`

Путь к дополнительному файлу *.deps.json*.

`--additionalprobingpath <PATH>`

Путь, содержащий политику проверки и проверяемые сборки.

`--depsfile`

Путь к файлу *deps.json*.

Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок. Дополнительные сведения об этом файле см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.

`-d|--diagnostics`

Включает вывод диагностических данных.

`--fx-version <VERSION>`

Версия среды выполнения .NET Core, используемой для запуска приложения.

`-h|--help`

Выводит на экран документацию для определенной команды, например `dotnet build --help`. `dotnet --help` выводит список доступных команд.

`--info`

Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.

`--list-runtimes`

Отображает установленные среды выполнения .NET Core.

`--list-sdks`

Отображает установленные пакеты SDK для .NET Core.

`--roll-forward-on-no-candidate-fx <N>`

Определяет поведение, когда требуемая общая платформа недоступна. Параметр `N` может принимать следующие значения:

- `0` — отключает увеличение дополнительных версий.
- `1` — позволяет увеличивать дополнительный номер версии, но не основной. Это поведение установлено по умолчанию.
- `2` — включает увеличение основных и дополнительных версий.

 Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).

`--runtimeconfig`

Путь к файлу *runtimeconfig.json*.

Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения. Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`. Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.

`--version`

Выводит версию используемого пакета SDK для .NET Core.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--additional-deps <PATH>`

Путь к дополнительному файлу *.deps.json*.

`--additionalprobingpath <PATH>`

Путь, содержащий политику проверки и проверяемые сборки.

`--depsfile`

Путь к файлу *deps.json*.

Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок. Дополнительные сведения об этом файле см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.

`-d|--diagnostics`

Включает вывод диагностических данных.

`--fx-version <VERSION>`

Версия среды выполнения .NET Core, используемой для запуска приложения.

`-h|--help`

Выводит на экран документацию для определенной команды, например `dotnet build --help`. `dotnet --help` выводит список доступных команд.

`--info`

Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.

`--roll-forward-on-no-candidate-fx`

 Отключает накат дополнительных версий, если установлено `0`. Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).

`--runtimeconfig`

Путь к файлу *runtimeconfig.json*.

Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения. Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`. Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.

`--version`

Выводит версию используемого пакета SDK для .NET Core.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Путь, содержащий политику проверки и проверяемые сборки.

`--depsfile`

Путь к файлу *deps.json*.

Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок. Дополнительные сведения об этом файле см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.

`-d|--diagnostics`

Включает вывод диагностических данных.

`--fx-version <VERSION>`

Версия среды выполнения .NET Core, используемой для запуска приложения.

`-h|--help`

Выводит на экран документацию для определенной команды, например `dotnet build --help`. `dotnet --help` выводит список доступных команд.

`--info`

Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.

`--runtimeconfig`

Путь к файлу *runtimeconfig.json*.

Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения. Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`. Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.

`--version`

Выводит версию используемого пакета SDK для .NET Core.

---

## <a name="dotnet-commands"></a>Команды dotnet

### <a name="general"></a>Общее

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

| Команда                                       | Функция                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | Выполняет сборку приложения .NET Core.                                     |
| [dotnet build-server](dotnet-build-server.md) | Взаимодействует с серверами, запущенными сборкой.                          |
| [dotnet clean](dotnet-clean.md)               | Очищает выходные данные сборки.                                                |
| [dotnet help](dotnet-help.md)                 | Выводит более подробную документацию из Интернета для команды.           |
| [dotnet migrate](dotnet-migrate.md)           | Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.  |
| [dotnet msbuild](dotnet-msbuild.md)           | Обеспечивает доступ к командной строке MSBuild.                        |
| [dotnet new](dotnet-new.md)                   | Инициализирует проект C# или F# для заданного шаблона.                |
| [dotnet pack](dotnet-pack.md)                 | Создает пакет NuGet с кодом.                               |
| [dotnet publish](dotnet-publish.md)           | Публикует платформозависимое или автономное приложение .NET. |
| [dotnet restore](dotnet-restore.md)           | Восстанавливает зависимости для данного приложения.                  |
| [dotnet run](dotnet-run.md)                   | Запускает приложение из источника.                                   |
| [dotnet sln](dotnet-sln.md)                   | Параметры для добавления, удаления и перечисления проектов в файле решения.       |
| [dotnet store](dotnet-store.md)               | Сохраняет сборки в хранилище пакетов среды выполнения.                     |
| [dotnet test](dotnet-test.md)                 | Выполняет тесты с помощью средства запуска тестов.                                     |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

| Команда                             | Функция                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Выполняет сборку приложения .NET Core.                                     |
| [dotnet clean](dotnet-clean.md)     | Очищает выходные данные сборки.                                              |
| [dotnet help](dotnet-help.md)       | Выводит более подробную документацию из Интернета для команды.           |
| [dotnet migrate](dotnet-migrate.md) | Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.  |
| [dotnet msbuild](dotnet-msbuild.md) | Обеспечивает доступ к командной строке MSBuild.                        |
| [dotnet new](dotnet-new.md)         | Инициализирует проект C# или F# для заданного шаблона.                |
| [dotnet pack](dotnet-pack.md)       | Создает пакет NuGet с кодом.                               |
| [dotnet publish](dotnet-publish.md) | Публикует платформозависимое или автономное приложение .NET. |
| [dotnet restore](dotnet-restore.md) | Восстанавливает зависимости для данного приложения.                  |
| [dotnet run](dotnet-run.md)         | Запускает приложение из источника.                                   |
| [dotnet sln](dotnet-sln.md)         | Параметры для добавления, удаления и перечисления проектов в файле решения.       |
| [dotnet store](dotnet-store.md)     | Сохраняет сборки в хранилище пакетов среды выполнения.                     |
| [dotnet test](dotnet-test.md)       | Выполняет тесты с помощью средства запуска тестов.                                     |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

| Команда                             | Функция                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Выполняет сборку приложения .NET Core.                                     |
| [dotnet clean](dotnet-clean.md)     | Очищает выходные данные сборки.                                              |
| [dotnet migrate](dotnet-migrate.md) | Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.  |
| [dotnet msbuild](dotnet-msbuild.md) | Обеспечивает доступ к командной строке MSBuild.                        |
| [dotnet new](dotnet-new.md)         | Инициализирует проект C# или F# для заданного шаблона.                |
| [dotnet pack](dotnet-pack.md)       | Создает пакет NuGet с кодом.                               |
| [dotnet publish](dotnet-publish.md) | Публикует платформозависимое или автономное приложение .NET. |
| [dotnet restore](dotnet-restore.md) | Восстанавливает зависимости для данного приложения.                  |
| [dotnet run](dotnet-run.md)         | Запускает приложение из источника.                                   |
| [dotnet sln](dotnet-sln.md)         | Параметры для добавления, удаления и перечисления проектов в файле решения.       |
| [dotnet test](dotnet-test.md)       | Выполняет тесты с помощью средства запуска тестов.                                     |

---

### <a name="project-references"></a>Ссылки на проекты

Команда | Функция
--- | ---
[dotnet add reference](dotnet-add-reference.md) | Добавляет ссылку на проект.
[dotnet list reference](dotnet-list-reference.md) | Перечисляет ссылки на проекты.
[dotnet remove reference](dotnet-remove-reference.md) | Удаляет ссылку на проект.

### <a name="nuget-packages"></a>Пакеты NuGet

Команда | Функция
--- | ---
[dotnet add package](dotnet-add-package.md) | Добавляет пакет NuGet.
[dotnet remove package](dotnet-remove-package.md) | Удаляет пакет NuGet.

### <a name="nuget-commands"></a>Команды NuGet

Команда | Функция
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Удаляет пакет с сервера или из списка.
[dotnet nuget locals](dotnet-nuget-locals.md) | Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.
[dotnet nuget push](dotnet-nuget-push.md) | Отправляет пакет на сервер и публикует его.

### <a name="global-tools-commands"></a>Команды глобальных средств

[Глобальные средства .NET Core](global-tools.md) появились в пакете SDK для .NET Core, начиная с версии 2.1.300:

Команда | Функция
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Устанавливает глобальное средство на локальном компьютере.
[dotnet tool list](dotnet-tool-list.md) | Перечисляет выводит все глобальные средства, установленные на компьютере в каталоге по умолчанию или по указанному пути.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Удаляет глобальное средство с компьютера.
[dotnet tool update](dotnet-tool-update.md) | Обновляет глобальное средство на локальном компьютере.

### <a name="additional-tools"></a>Дополнительные средства

Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300. Эти средства перечислены в следующей таблице.

| Средство                                              | Функция                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Создает сертификаты разработки и управляет ими.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Средства командной строки для Entity Framework Core.                    |
| sql-cache                                         | Средства командной строки для кэша SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Управляет секретами пользователей для разработки.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Запускает наблюдатель за файлами, который выполняет команду при изменении файлов. |

Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.

## <a name="examples"></a>Примеры

Создание проекта консольного приложения .NET Core:

`dotnet new console`

Восстановление зависимостей для данного приложения:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Сборка проекта и его зависимостей в указанном каталоге:

`dotnet build`

Запустите библиотеку DLL приложения, например `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Переменные среды

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`DOTNET_PACKAGES`

Папка глобальных пакетов. Если значение не задано, то по умолчанию в Unix используется `~/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.

`DOTNET_SERVICING`

Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт. Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`). Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`). Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.

`DOTNET_MULTILEVEL_LOOKUP`

Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK. Если не задано, используется значение по умолчанию `true`. Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`). Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

Отключает накат дополнительных версий, если установлено `0`. Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`DOTNET_PACKAGES`

Основной кэш пакетов. Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.

`DOTNET_SERVICING`

Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт. Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`). Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`). Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.

`DOTNET_MULTILEVEL_LOOKUP`

Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK. Если не задано, используется значение по умолчанию `true`. Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`). Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`DOTNET_PACKAGES`

Основной кэш пакетов. Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.

`DOTNET_SERVICING`

Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт. Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`). Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`). Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.

---

## <a name="see-also"></a>См. также

- [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md)
