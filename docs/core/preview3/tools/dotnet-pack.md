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
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 8e266f9b34923b0ab69140d78a20afeca00e0b7c

---

#<a name="dotnet-pack-net-core-tools-rc4"></a>dotnet-pack (версия-кандидат 4 средств .NET Core)

> [!WARNING]
> Эта статья применима к версии-кандидату 4 средств .NET Core. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [dotnet-pack](../../tools/dotnet-pack.md).

## <a name="name"></a>Имя

`dotnet-pack` — упаковывает код в пакет NuGet.

## <a name="synopsis"></a>Краткий обзор

`dotnet pack [--help] [--output]  
    [--no-build] [--include-symbols]
    [--include-source] [--servicable]
    [--configuration]  [--version-suffix]
    [project]`  

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат выполнения команды — пакет NuGet. При наличии параметра `--include-symbols` будет создан другой пакет, содержащий символы отладки. 

Зависимости NuGet упаковываемого проекта добавляются в файл `nuspec`, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. В настоящее время при наличии межпроектных зависимостей требуется один пакет на каждый проект.

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

Включает исходные файлы в пакет NuGet. Исходные файлы включены в папку `src` пакета `nupkg`. 

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


<!--HONumber=Feb17_HO2-->


