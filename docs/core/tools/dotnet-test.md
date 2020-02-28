---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 05/29/2018
ms.openlocfilehash: 909815151265117395c6d8d13b4443a245c05f9e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451198"
---
# <a name="dotnet-test"></a>dotnet test

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.

## <a name="synopsis"></a>Краткий обзор

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта. Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них. Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1. Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>Аргументы

`PROJECT`

Путь к тестовому проекту. Если значение не задано, по умолчанию используется текущий каталог.

## <a name="options"></a>Параметры

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.

`--blame`

Выполнение тестов в режиме обвинения. Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов. Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Включает сборщик данных для тестового запуска. Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.

`-f|--framework <FRAMEWORK>`

Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).

`--filter <EXPRESSION>`

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).

`-h|--help`

Выводит краткую справку по команде.

`-l|--logger <LoggerUri/FriendlyName>`

Указывает средство ведения журнала для результатов тестирования.

`--no-build`

Не выполняет сборку тестового проекта перед запуском. Он также неявно задает флаг `--no-restore`.

`--no-restore`

Не выполняет неявное восстановление при выполнении команды.

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-r|--results-directory <PATH>`

Каталог для сохранения результатов тестов. Если указанный каталог не существует, он создается.

`-s|--settings <SETTINGS_FILE>`

Файл `.runsettings`, который необходимо использовать для проведения тестов. [Настройка модульных тестов с помощью файла `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

Отображение списка всех обнаруженных тестов в текущем проекте.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

`RunSettings arguments`

Аргументы, передаваемые в качестве конфигураций RunSettings для теста. Аргументы задаются в виде пар `[name]=[value]` после "-- " (обратите внимание на пробел после --). Несколько пар `[name]=[value]` разделяются пробелами.

Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

Дополнительные сведения о RunSettings см. в статье о [передаче аргументов RunSettings в командной строке](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

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

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).

`-h|--help`

Выводит краткую справку по команде.

`-l|--logger <LoggerUri/FriendlyName>`

Указывает средство ведения журнала для результатов тестирования.

`--no-build`

Не выполняет сборку тестового проекта перед запуском. Он также неявно задает флаг `--no-restore`.

`--no-restore`

Не выполняет неявное восстановление при выполнении команды.

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-r|--results-directory <PATH>`

Каталог для сохранения результатов тестов. Если указанный каталог не существует, он создается.

`-s|--settings <SETTINGS_FILE>`

Файл `.runsettings`, который необходимо использовать для проведения тестов. [Настройка модульных тестов с помощью файла `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

Отображение списка всех обнаруженных тестов в текущем проекте.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.

`-f|--framework <FRAMEWORK>`

Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).

`--filter <EXPRESSION>`

Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).

`-h|--help`

Выводит краткую справку по команде.

`-l|--logger <LoggerUri/FriendlyName>`

Указывает средство ведения журнала для результатов тестирования.

`--no-build`

Не выполняет сборку тестового проекта перед запуском.

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-s|--settings <SETTINGS_FILE>`

Файл `.runsettings`, который необходимо использовать для проведения тестов. [Настройка модульных тестов с помощью файла `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

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

Выполнение тестов в проекте в текущем каталоге и создание файл результатов теста в формате trx:

`dotnet test --logger trx`

## <a name="filter-option-details"></a>Сведения о параметре "Фильтр"

`--filter <EXPRESSION>`

Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.

`<property>` — это атрибут `Test Case`. Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.

| Тестовая платформа | Поддерживаемые свойства                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>name</li><li>ClassName</li><li>Priority</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Признаки</li></ul>                                   |

`<operator>` описывает связь между свойством и значением:

| Оператор | Функция        |
| :------: | --------------- |
| `=`      | Точное соответствие     |
| `!=`     | Неточное соответствие |
| `~`      | Содержит        |
| `!~`     | Не содержит    |

`<value>` — это строка. Поиск выполняется без учета регистра.

Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).

Выражения можно объединять с условными операторами.

| Оператор            | Функция |
| ------------------- | -------- |
| <code>&#124;</code> | OR       |
| `&`                 | AND      |

При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).

Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).

## <a name="see-also"></a>См. также

- [Платформы и целевые объекты](../../standard/frameworks.md)
- [Каталог идентификаторов сред выполнения (RID) в .NET Core](../rid-catalog.md)
