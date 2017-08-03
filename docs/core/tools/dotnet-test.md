---
title: "Команда dotnet-test — CLI .NET Core"
description: "Команда dotnet test служит для выполнения модульных тестов в проекте."
keywords: "dotnet-test, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3308488672df2621c04de40f642c732f81284019
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Имя

`dotnet-test` — драйвер тестов .NET, используемый для проведения модульных тестов.

## <a name="synopsis"></a>Краткий обзор

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Модульные тесты — это проекты консольных приложений, у которых есть зависимости от среды модульного тестирования (например, MSTest, NUnit или xUnit) и от средства запуска тестов dotnet для этой среды. Они упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

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

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).

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

## <a name="filter-option-details"></a>Сведения о параметре "Фильтр"

`--filter <EXPRESSION>`

Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.

`<property>` — это атрибут `Test Case`. Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.

| Тестовая платформа | Поддерживаемые свойства                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>Имя</li><li>ClassName</li><li>Приоритет</li><li>TestCategory</li></ul> |
| Xunit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Признаки</li></ul>                                   |

`<operator>` описывает связь между свойством и значением:

| Оператор | Функция        |
| :------: | --------------- |
| `=`      | Точное соответствие     |
| `!=`     | Неточное соответствие |
| `~`      | Содержит        |

`<value>` — это строка. Поиск выполняется без учета регистра.

Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).

Выражения можно объединять с условными операторами.

| Оператор | Функция |
| :------: | :------: |
| <code>&#124;</code>      | OR       |
| `&`      | AND      |

При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).

Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).

## <a name="see-also"></a>См. также

[Платформы и целевые объекты](../../standard/frameworks.md)   
[Каталог идентификаторов сред выполнения (RID) в .NET Core](../rid-catalog.md)

