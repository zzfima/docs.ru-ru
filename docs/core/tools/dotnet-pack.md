---
title: "Команда dotnet-pack | Пакет SDK для .NET Core"
description: "Команда dotnet-pack создает пакеты NuGet для проекта .NET Core."
keywords: "dotnet-pack, CLI, команда CLI, .NET Core"
author: mairaw
manager: wpickett
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8b4b8cef-f56c-4a10-aa01-fde8bfaae53e
translationtype: Human Translation
ms.sourcegitcommit: c6ee3f5663d0a3f62914e8de474cca4d15340c9d
ms.openlocfilehash: e83c8ad302590bcd77129c3ff325e498da751e69

---

#<a name="dotnetpack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack` — упаковывает код в пакет NuGet

## <a name="synopsis"></a>Краткий обзор

`dotnet pack [--help] [--output]  
    [--no-build] [--build-base-path]  
    [--configuration]  [--version-suffix]
    [project]`  

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат этой операции — два пакета с расширением `nupkg`. Один пакет содержит код, а другой — отладочные символы. 

Зависимости NuGet упаковываемого проекта добавляются в файл nuspec, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. В настоящее время при наличии межпроектных зависимостей требуется один пакет на каждый проект.

`dotnet pack` по умолчанию сначала выполняет сборку проекта. Чтобы избежать этого, передайте параметр `--no-build`. Это может быть полезно, например, в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был только что собран. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`[project]` 
    
Упаковываемый проект. Это может быть путь к файлу [project.json](project-json.md) или к каталогу. Если значение не указано, по умолчанию используется текущий каталог. 

`-o|--output <OUTPUT_DIRECTORY>`

Собранные пакеты помещаются в указанный каталог. 

`--no-build`

Не выполняет сборку проекта перед упаковкой. 

`--build-base-path`

Временные артефакты сборки помещаются в указанный каталог. По умолчанию они помещаются в каталог `obj` в текущем каталоге. 

`-c|--configuration <Debug|Release>`

Конфигурация, используемая при сборке проекта. Если значение не задано, по умолчанию используется значение `Debug`.

`--version-suffix`

Заменяет звездочку в суффиксе версии пакета `-*` указанной строкой.

## <a name="examples"></a>Примеры

Упаковка проекта в текущем каталоге:

`dotnet pack`

Упаковка проекта app1:

`dotnet pack ~/projects/app1/project.json`
    
Упаковка проекта в текущем каталоге; полученные пакеты помещаются в указанную папку:

`dotnet pack --output nupkgs`

Упаковка проекта в текущем каталоге в указанную папку и пропуск этапа сборки:

`dotnet pack --no-build --output nupkgs`

Упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса. Например, версия `1.0.0-*` будет изменена на `1.0.0-ci-1234`.

`dotnet pack --version-suffix "ci-1234"`


<!--HONumber=Nov16_HO1-->


