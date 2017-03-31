---
title: "Команда dotnet-test — CLI .NET Core | Документы Майкрософт"
description: "Команда `dotnet test` служит для выполнения модульных тестов в проекте."
keywords: "dotnet-test, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 26b5834135db8041995a137f5008d00cdf14d820
ms.lasthandoff: 03/22/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Имя

`dotnet-test` — драйвер тестов .NET, используемый для проведения модульных тестов.

## <a name="synopsis"></a>Краткий обзор

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Модульные тесты — это проекты библиотек классов, которые имеют зависимости от среды модульного тестирования (например, MSText, NUnit или xUnit) и средства запуска тестов dotnet для этой среды. Они упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

Для тестовых проектов также нужно указать средство выполнения тестов. Для этого используется обычный элемент `<PackageReference>`, как показано в следующем образце файла проекта:

[!code-xml[Базовый шаблон XUnit](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>Параметры

`PROJECT`
    
Указывает путь к тестовому проекту. Если значение не задано, по умолчанию используется текущий каталог.

`-h|--help`

Выводит краткую справку по команде.

`-s|--settings <SETTINGS_FILE>`

Параметры, используемые при выполнении тестов. 

`-t|--list-tests`

Отображение списка всех обнаруженных тестов в текущем проекте. 

`--filter <EXPRESSION>`

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения о поддержке фильтрации см. в разделе [Запуск выборочных модульных тестов в Visual Studio с помощью TestCaseFilter](https://aka.ms/vstest-filtering).

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске. 

`-l|--logger <LoggerUri/FriendlyName>`

Указывает средство ведения журнала для результатов тестирования. 

`-c|--configuration <CONFIGURATION>`

Конфигурация для сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.

`-f|--framework <FRAMEWORK>`

Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл. 

`--no-build` 

Не выполняет сборку тестового проекта перед его запуском.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

Выполнение тестов в проекте в текущем каталоге:

`dotnet test` 

Выполнение тестов в проекте `test1`:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>См. также

* [Целевые платформы](../../standard/frameworks.md)
* [Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)
