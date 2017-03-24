---
title: "Команда dotnet-test | Microsoft Docs"
description: "Команда `dotnet test` служит для выполнения модульных тестов в проекте."
keywords: "dotnet-test, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 21f3850520b922f16c77f831a045ec58bdf1b5c1
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Имя

`dotnet-test` — .NET драйвер тестов

## <a name="synopsis"></a>Краткий обзор

```
dotnet test [project] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity]
dotnet test [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Модульные тесты — это проекты библиотек классов, которые имеют зависимости от среды модульного тестирования (например, NUnit или xUnit) и средства запуска тестов dotnet для этой среды. Они упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

Для тестирования проектов также нужно указать средство выполнения тестов. Для этого используется обычный элемент `<PackageReference>`, как показано в следующем образце файла проекта:

[!code-xml[Базовый шаблон XUnit](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>Параметры

`project`
    
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

`-c|--configuration <Debug|Release>`

Конфигурация для сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить параметр SDK по умолчанию.

`-f|--framework <FRAMEWORK>`

Поиск тестовых двоичных файлов для определенной платформы.

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

Выполнение тестов в проекте test1:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>См. также

[Платформы](../../standard/frameworks.md)

[Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)
