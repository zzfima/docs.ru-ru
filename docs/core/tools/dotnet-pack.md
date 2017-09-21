---
title: "Команда dotnet pack — CLI .NET Core"
description: "Команда dotnet pack создает пакеты NuGet для проекта .NET Core."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 8594c863d67baf0237b63e61f28ca9ee315eeddf
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-pack"></a>dotnet pack

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Имя

`dotnet pack` — упаковывает код в пакет NuGet.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies] [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат выполнения команды — пакет NuGet. При наличии параметра `--include-symbols` создается другой пакет, содержащий отладочные символы.

Зависимости NuGet упакованного проекта добавляются в файл *NUSPEC*, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. Сейчас при наличии межпроектных зависимостей требуется один пакет на каждый проект.

`dotnet pack` по умолчанию сначала выполняет сборку проекта. Чтобы избежать этого, передайте параметр `--no-build`. Это часто бывает полезно, например, в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был собран недавно.

Может предоставлять свойства MSBuild команде `dotnet pack` для процесса упаковки. Дополнительные сведения см. в разделах [Свойства метаданных NuGet](csproj.md#nuget-metadata-properties) и [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

## <a name="arguments"></a>Аргументы

`PROJECT`

Упаковываемый проект. Это путь к файлу [CSPROJ](csproj.md) или каталогу. Если значение не задано, по умолчанию используется текущий каталог.

## <a name="options"></a>Параметры

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`.

`--force` — принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно. Равносильно удалению файла *project.assets.json*.

`-h|--help`

Выводит краткую справку по команде.

`--include-source`

Включает исходные файлы в пакет NuGet. Исходные файлы включены в папку `src` пакета `nupkg`.

`--include-symbols`

Создает символы `nupkg`.

`--no-build`

Не выполняет сборку проекта перед упаковкой.

`--no-dependencies`

Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.

`--no-restore`

Не выполняет неявное восстановление при выполнении команды.

`-o|--output <OUTPUT_DIRECTORY>`

Собранные пакеты помещаются в указанный каталог.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Задает целевую среду выполнения для восстановления пакетов. Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).

`-s|--serviceable`

Задает флаг "подлежит обслуживанию" в пакете. Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).

`--version-suffix <VERSION_SUFFIX>`

Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`.

`-h|--help`

Выводит краткую справку по команде.

`--include-source`

Включает исходные файлы в пакет NuGet. Исходные файлы включены в папку `src` пакета `nupkg`.

`--include-symbols`

Создает символы `nupkg`.

`--no-build`

Не выполняет сборку проекта перед упаковкой.

`-o|--output <OUTPUT_DIRECTORY>`

Собранные пакеты помещаются в указанный каталог.

`-s|--serviceable`

Задает флаг "подлежит обслуживанию" в пакете. Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).

`--version-suffix <VERSION_SUFFIX>`

Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

---

## <a name="examples"></a>Примеры

Упаковка проекта в текущем каталоге:

`dotnet pack`

Упаковка проекта `app1`:

`dotnet pack ~/projects/app1/project.csproj`
    
Упаковка проекта в текущем каталоге; полученные пакеты помещаются в папку `nupkgs`:

`dotnet pack --output nupkgs`

Упаковка проекта в текущем каталоге в папку `nupkgs` и пропуск этапа сборки:

`dotnet pack --no-build --output nupkgs`

Если суффикс версии пакета в файле *CSPROJ* настроен как `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`, упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса:

`dotnet pack --version-suffix "ci-1234"`

Устанавливает версию пакета в `2.1.0` с использованием свойства MSBuild `PackageVersion`:

`dotnet pack /p:PackageVersion=2.1.0`

