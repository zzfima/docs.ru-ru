---
title: "Команда dotnet-pack | Пакет SDK для .NET Core"
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
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 5aca8db50bf80606ff94562a6014c396b0ef770e

---

#<a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack` — упаковывает код в пакет NuGet

## <a name="synopsis"></a>Краткий обзор

`dotnet pack [--help] [--output]  
    [--no-build] [--include-symbols]
    [--include-source] [--servicable]
    [--configuration]  [--version-suffix]
    [project]`  

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат выполнения команды — пакет nuget. При наличии параметра `--include-symbols` будет создан другой пакет, содержащий символы отладки. 

Зависимости NuGet упаковываемого проекта добавляются в файл nuspec, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. В настоящее время при наличии межпроектных зависимостей требуется один пакет на каждый проект.

`dotnet pack` по умолчанию сначала выполняет сборку проекта. Чтобы избежать этого, передайте параметр `--no-build`. Это может быть полезно, например, в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был только что собран. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`[project]` 
    
Упаковываемый проект. Это может быть путь к файлу [csproj](csproj.md) или каталогу. Если значение не указано, по умолчанию используется текущий каталог. 

`-o|--output <OUTPUT_DIRECTORY>`

Собранные пакеты помещаются в указанный каталог. 

`--no-build`

Не выполняет сборку проекта перед упаковкой. 

`--include-source`

Включает исходные файлы в пакет nuget. Исходные файлы включены в папку `src` пакета nupkg. 

`--include-symbols`

Создание символов nupkg. 

`-c|--configuration <Debug|Release>`

Конфигурация, используемая при сборке проекта. Если значение не задано, по умолчанию используется значение `Debug`.

`--version-suffix`

Заменяет звездочку в суффиксе версии пакета `-*` указанной строкой.

## <a name="examples"></a>Примеры

Упаковка проекта в текущем каталоге:

`dotnet pack`

Упаковка проекта app1:

`dotnet pack ~/projects/app1/project.csproj`
    
Упаковка проекта в текущем каталоге; полученные пакеты помещаются в указанную папку:

`dotnet pack --output nupkgs`

Упаковка проекта в текущем каталоге в указанную папку и пропуск этапа сборки:

`dotnet pack --no-build --output nupkgs`

Упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса. Например, версия `1.0.0-*` будет изменена на `1.0.0-ci-1234`.

`dotnet pack --version-suffix "ci-1234"`



<!--HONumber=Nov16_HO3-->


