---
title: "Команда dotnet-pack | Microsoft Docs"
description: "Команда dotnet-pack создает пакеты NuGet для проекта .NET Core."
keywords: "dotnet-pack, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8b4b8cef-f56c-4a10-aa01-fde8bfaae53e
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 227bdaabc88bddbf2014788d72ef87e75f956795

---

#<a name="dotnet-pack"></a>dotnet-pack

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Информацию об инструментах .NET Core (предварительная версия 4) для версии-кандидата Visual Studio 2017 см. в статье [dotnet-pack (предварительная версия 4 инструментов)](../preview3/tools/dotnet-pack.md).

## <a name="name"></a>Имя

`dotnet-pack` — упаковывает код в пакет NuGet.

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


<!--HONumber=Jan17_HO3-->


