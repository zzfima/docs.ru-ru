---
title: "Команда dotnet-pack | Microsoft Docs"
description: "Команда dotnet-pack создает пакеты NuGet для проекта .NET Core."
keywords: "dotnet-pack, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 88289a09a22bf20ec9089ec6a74269cd682a305b
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Имя

`dotnet-pack` — упаковывает код в пакет NuGet.

## <a name="synopsis"></a>Краткий обзор

```
dotnet pack [project] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix] [-s|--serviceable] [-v|--verbosity]
dotnet pack [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат выполнения команды — пакет NuGet. При наличии параметра `--include-symbols` будет создан другой пакет, содержащий символы отладки. 

Зависимости NuGet упаковываемого проекта добавляются в файл `nuspec`, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. В настоящее время при наличии межпроектных зависимостей требуется один пакет на каждый проект.

`dotnet pack` по умолчанию сначала выполняет сборку проекта. Чтобы избежать этого, передайте параметр `--no-build`. Это может быть полезно, например, в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был только что собран. 

## <a name="arguments"></a>Аргументы

`project` 
    
Упаковываемый проект. Это может быть путь к файлу [csproj](csproj.md) или каталогу. Если значение не указано, по умолчанию используется текущий каталог. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-o|--output <OUTPUT_DIRECTORY>`

Собранные пакеты помещаются в указанный каталог. 

`--no-build`

Не выполняет сборку проекта перед упаковкой. 

`--include-symbols`

Создает символы nupkg. 

`--include-source`

Включает исходные файлы в пакет NuGet. Исходные файлы включены в папку `src` пакета `nupkg`. 

`-c|--configuration <Debug|Release>`

Конфигурация, используемая при сборке проекта. Если значение не задано, по умолчанию используется значение `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Определяет значение для свойства $(VersionSuffix) MSBuild в проекте.

`-s|--serviceable`

Задает флаг "подлежит обслуживанию" в пакете. Дополнительные сведения см. на странице: https://aka.ms/nupkgservicing.

`--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

Упаковка проекта в текущем каталоге:

`dotnet pack`

Упаковка проекта app1:

`dotnet pack ~/projects/app1/project.csproj`
    
Упаковка проекта в текущем каталоге; полученные пакеты помещаются в указанную папку:

`dotnet pack --output nupkgs`

Упаковка проекта в текущем каталоге в указанную папку и пропуск этапа сборки:

`dotnet pack --no-build --output nupkgs`

Упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса. Суффикс версии проекта настраивается как `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` в файле *CSPROJ*.

`dotnet pack --version-suffix "ci-1234"`
