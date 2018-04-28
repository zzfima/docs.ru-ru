---
title: Команда dotnet restore — CLI .NET Core
description: Вы узнаете, как восстановить зависимости и связанные с проектом средства при помощи команды dotnet restore.
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: b20d9e72fcc754a7538e9c54677a86a1c9bbc2d1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-restore"></a>dotnet restore

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet restore` — восстанавливает зависимости и средства проекта.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a>Описание:

Команда `dotnet restore` использует NuGet для восстановления зависимостей, а также связанных с проектом средств, которые указаны в файле проекта. По умолчанию восстановление зависимостей и средств производится параллельно.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Для восстановления зависимостей NuGet требуются каналы, где находятся пакеты. Каналы обычно предоставляются посредством файла конфигурации *NuGet.config*. Файл конфигурации по умолчанию предоставляется при установке средств CLI. Вы можете указать дополнительные веб-каналы, создав собственный файл *NuGet.config* в каталоге проекта. Можно также указать дополнительные веб-каналы на вызов из командной строки.

Для зависимостей можно указать, куда помещаются восстанавливаемые пакеты во время операции восстановления, с помощью аргумента `--packages`. Если значение не указано, используется кэш пакетов NuGet по умолчанию. Он находится в каталоге `.nuget/packages` в домашнем каталоге пользователя во всех операционных системах (например, */home/user1* в Linux или *C:\Users\user1* в Windows).

Для связанных с проектом средств `dotnet restore` сначала восстанавливает пакет, в котором упаковано средство, а затем — зависимости средства, указанные в файле проекта.

На поведение команды `dotnet restore` влияют некоторые из параметров в файле *Nuget.Config*, если он существует. Например, если установить параметр `globalPackagesFolder` в файле *NuGet.Config*, то восстановленные пакеты NuGet будут помещены в указанную папку. Для получения того же результата можно указать параметр `--packages` команды `dotnet restore`. Дополнительные сведения см. в [справочнике по файлу NuGet.Config](/nuget/schema/nuget-config-file).

## <a name="implicit-dotnet-restore"></a>Неявное выполнение `dotnet restore`

Начиная с версии .NET Core 2.0, команда `dotnet restore` выполняется неявно при выполнении следующих команд:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

В большинстве случаев использовать команду `dotnet restore` явным образом не требуется. 

В некоторых случаях выполнять команду `dotnet restore` явным образом неудобно. Например, некоторые автоматизированные системы, такие как системы сборки, должны явно вызывать `dotnet restore`, чтобы контролировать процесс восстановления и, следовательно, отслеживать использование сетевых ресурсов. Чтобы избежать неявного выполнения команды `dotnet restore`, с любой из приведенных выше команд можно использовать параметр `--no-restore` для отключения неявного восстановления.

## <a name="arguments"></a>Аргументы

`ROOT`

Дополнительный путь к файлу проекта для восстановления.

## <a name="options"></a>Параметры

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--configfile <FILE>`

Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.

`--disable-parallel`

Отключает параллельное восстановление нескольких проектов.

`--force`

Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно. Равносильно удалению файла *project.assets.json*.

`-h|--help`

Выводит краткую справку по команде.

`--ignore-failed-sources`

Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.

`--no-cache`

Отключает кэширование пакетов и HTTP-запросов.

`--no-dependencies`

При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.

`--packages <PACKAGES_DIRECTORY>`

Задает каталог для восстановленных пакетов.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Задает среду выполнения для восстановления пакетов. Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*. Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md). Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.

`-s|--source <SOURCE>`

Указывает источник пакета NuGet для использования во время операции восстановления. Переопределяет все источники, указанные в файлах *NuGet.config*. Чтобы указать несколько источников, задайте этот параметр несколько раз.

`--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--configfile <FILE>`

Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.

`--disable-parallel`

Отключает параллельное восстановление нескольких проектов.

`-h|--help`

Выводит краткую справку по команде.

`--ignore-failed-sources`

Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.

`--no-cache`

Отключает кэширование пакетов и HTTP-запросов.

`--no-dependencies`

При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.

`--packages <PACKAGES_DIRECTORY>`

Задает каталог для восстановленных пакетов.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Задает среду выполнения для восстановления пакетов. Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*. Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md). Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.

`-s|--source <SOURCE>`

Указывает источник пакета NuGet для использования во время операции восстановления. Переопределяет все источники, указанные в файлах *NuGet.config*. Чтобы указать несколько источников, задайте этот параметр несколько раз.

`--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

Восстановление зависимостей и средств для проекта в текущем каталоге:

`dotnet restore`

Восстановление зависимостей и средств для проекта `app1` по указанному пути:

`dotnet restore ~/projects/app1/app1.csproj`

Восстановление зависимостей и средств для проекта в текущем каталоге с использованием пути к файлу, заданного в качестве источника:

`dotnet restore -s c:\packages\mypackages`

Восстановление зависимостей и средств для проекта в текущем каталоге с использованием двух путей к файлу, заданных в качестве источника:

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных:

`dotnet restore --verbosity minimal`
