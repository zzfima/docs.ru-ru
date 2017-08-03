---
title: "Команда dotnet-pack — CLI .NET Core"
description: "Команда dotnet-pack создает пакеты NuGet для проекта .NET Core."
keywords: "dotnet-pack, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 04b967fdf6578098caae8c21604c5d6160eb6775
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Имя

`dotnet-pack` — упаковывает код в пакет NuGet.

## <a name="synopsis"></a>Краткий обзор

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат выполнения команды — пакет NuGet. При наличии параметра `--include-symbols` создается другой пакет, содержащий отладочные символы. 

Зависимости NuGet упакованного проекта добавляются в файл *NUSPEC*, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. Сейчас при наличии межпроектных зависимостей требуется один пакет на каждый проект.

`dotnet pack` по умолчанию сначала выполняет сборку проекта. Чтобы избежать этого, передайте параметр `--no-build`. Это часто бывает полезно, например, в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был собран недавно.

Может предоставлять свойства MSBuild команде `dotnet pack` для процесса упаковки. Дополнительные сведения см. в разделах [Свойства метаданных NuGet](csproj.md#nuget-metadata-properties) и [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

## <a name="arguments"></a>Аргументы

`PROJECT` 
    
Упаковываемый проект. Это путь к файлу [CSPROJ](csproj.md) или каталогу. Если значение не задано, по умолчанию используется текущий каталог. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-o|--output <OUTPUT_DIRECTORY>`

Собранные пакеты помещаются в указанный каталог. 

`--no-build`

Не выполняет сборку проекта перед упаковкой. 

`--include-symbols`

Создает символы `nupkg`. 

`--include-source`

Включает исходные файлы в пакет NuGet. Исходные файлы включены в папку `src` пакета `nupkg`. 

`-c|--configuration <CONFIGURATION>`

Конфигурация, используемая при сборке проекта. Если значение не указано, по умолчанию используется конфигурация `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.

`-s|--serviceable`

Задает флаг "подлежит обслуживанию" в пакете. Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).

`--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

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

