---
title: "Команда dotnet — CLI .NET Core"
description: "Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2eea7d13994bfddc89d8f3513308a6620c53c88c
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="dotnet-command"></a>Команда dotnet

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet` — универсальный драйвер для выполнения команд командной строки.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a>Описание:

`dotnet` — это универсальный драйвер для цепочки инструментов интерфейса командной строки (CLI). Если вызвать его без указания команды, выводятся краткие инструкции по использованию.

Каждая отдельная функция реализуется в виде команды. Для использования функции необходимо указать команду после `dotnet`, например [`dotnet build`](dotnet-build.md). Все аргументы после команды относятся именно к ней.

Единственный случай, когда `dotnet` используется в качестве команды самостоятельно, — это запуск [платформозависимых приложений](../deploying/index.md). Просто укажите библиотеку DLL приложения после команды `dotnet`, чтобы выполнить приложение (Например, `dotnet myapp.dll`).

## <a name="options"></a>Параметры

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--additional-deps <PATH>`

Путь к дополнительному файлу *deps.json*.

`--additionalprobingpath <PATH>`

Путь, содержащий политику проверки и проверяемые сборки.

`-d|--diagnostics`

Включает вывод диагностических данных.

`--fx-version <VERSION>`

Версия установленной среды выполнения .NET Core, используемой для запуска приложения.

`-h|--help`

Выводит краткую справку по команде. При использовании с `dotnet` также выводится список доступных команд.

`--info`

Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.

`--roll-forward-on-no-candidate-fx`

 Выполняет накат при отсутствии подходящей общей платформы.

`-v|--verbose`

Включает подробные выходные данные.

`--version`

Выводит версию используемого пакета SDK для .NET Core.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Путь, содержащий политику проверки и проверяемые сборки.

`-d|--diagnostics`

Включает вывод диагностических данных.

`--fx-version <VERSION>`

Версия установленной среды выполнения .NET Core, используемой для запуска приложения.

`-h|--help`

Выводит краткую справку по команде. При использовании с `dotnet` также выводится список доступных команд.

`--info`

Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.

`-v|--verbose`

Включает подробные выходные данные.

`--version`

Выводит версию используемого пакета SDK для .NET Core.

---

## <a name="dotnet-commands"></a>Команды dotnet

### <a name="general"></a>Общие

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

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
[dotnet add reference](dotnet-add-reference.md) | Добавление ссылки на проект.
[dotnet list reference](dotnet-list-reference.md) | Перечисление ссылок на проект.
[dotnet remove reference](dotnet-remove-reference.md) | Удаление ссылки на проект.

### <a name="nuget-packages"></a>Пакеты NuGet

Команда | Функция
--- | ---
[dotnet add package](dotnet-add-package.md) | Добавление пакета NuGet.
[dotnet remove package](dotnet-remove-package.md) | Удаление пакета NuGet.

### <a name="nuget-commands"></a>Команды NuGet

Команда | Функция
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Удаляет пакет с сервера или из списка.
[dotnet nuget locals](dotnet-nuget-locals.md) | Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.
[dotnet nuget push](dotnet-nuget-push.md) | Отправляет пакет на сервер и публикует его.

## <a name="examples"></a>Примеры

Инициализация образца консольного приложения .NET Core, которое можно скомпилировать и запустить:

`dotnet new console`

Восстановление зависимостей для данного приложения:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Сборка проекта и его зависимостей в указанном каталоге:

`dotnet build`

Запуск платформозависимого приложения `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Переменные среды

`DOTNET_PACKAGES`

Основной кэш пакетов. Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.

`DOTNET_SERVICING`

Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт. Задайте значение `true`, чтобы отказаться от функции телеметрии (принимаются значения `true`, `1` или `yes`), в противном случае задайте значение `false`, чтобы согласиться на функции телеметрии (принимаются значения `false`, `0` или `no`). Если значение не задано, то по умолчанию используется `false` и функция телеметрии включена.
