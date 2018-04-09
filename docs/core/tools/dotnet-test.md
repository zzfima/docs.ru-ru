---
title: Команда dotnet test — CLI .NET Core
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 6102281c4daf149f31e65ef8360831fe9e0ef4f6
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="dotnet-test"></a>dotnet test

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a>Описание:

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта. Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них. Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>Аргументы

`PROJECT`

Указывает путь к тестовому проекту. Если значение не задано, по умолчанию используется текущий каталог.

## <a name="options"></a>Параметры

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Включает сборщик данных для тестового запуска. Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.

`-f|--framework <FRAMEWORK>`

Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).

`--filter <EXPRESSION>`

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).

`-h|--help`

Выводит краткую справку по команде.

`-l|--logger <LoggerUri/FriendlyName>`

Указывает средство ведения журнала для результатов тестирования.

`--no-build`

Не выполняет сборку тестового проекта перед его запуском.

`--no-restore`

Не выполняет неявное восстановление при выполнении команды.

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-r|--results-directory <PATH>`

Каталог для сохранения результатов тестов. Если указанный каталог не существует, он будет создан.

`-s|--settings <SETTINGS_FILE>`

Параметры, используемые при выполнении тестов.

`-t|--list-tests`

Отображение списка всех обнаруженных тестов в текущем проекте.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.

`-f|--framework <FRAMEWORK>`

Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).

`--filter <EXPRESSION>`

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).

`-h|--help`

Выводит краткую справку по команде.

`-l|--logger <LoggerUri/FriendlyName>`

Указывает средство ведения журнала для результатов тестирования.

`--no-build`

Не выполняет сборку тестового проекта перед его запуском.

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-s|--settings <SETTINGS_FILE>`

Параметры, используемые при выполнении тестов.

`-t|--list-tests`

Отображение списка всех обнаруженных тестов в текущем проекте.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

---

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
| MSTest         | <ul><li>FullyQualifiedName</li><li>name</li><li>ClassName</li><li>Приоритет</li><li>TestCategory</li></ul> |
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
