---
title: Команда dotnet vstest
description: Команда dotnet vstest выполняет сборку проекта и всех его зависимостей.
ms.date: 05/30/2018
ms.openlocfilehash: 3fdb5443d6d0cfbe1e7e88bc824cbb930f211260
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451185"
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet-vstest` — запускает тесты из указанных файлов.

## <a name="synopsis"></a>Краткий обзор

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a>Описание

Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования.

## <a name="arguments"></a>Аргументы

`TEST_FILE_NAMES`

Запустите тесты из указанных сборок. Для разделения имен тестовых сборок используйте пробелы.

## <a name="options"></a>Параметры

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

Параметры, используемые при выполнении тестов.

`--Tests|/Tests:<Test Names>`

Выполните тесты с именами, которые соответствуют предусмотренным значениям. Для разделения значений используйте запятые.

`--TestAdapterPath|/TestAdapterPath`

Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.

`--Platform|/Platform:<Platform type>`

Архитектура целевой платформы, используемая для выполнения тестов. Допустимые значения: `x86`, `x64` и `ARM`.

`--Framework|/Framework:<Framework Version>`

Целевая версия платформы .NET Framework, используемая для выполнения тестов. Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`. Другие поддерживаемые значения: `Framework40`, `Framework45`, `FrameworkCore10` и `FrameworkUap10`.

`--Parallel|/Parallel`

Выполняйте тесты в параллельном режиме. По умолчанию для использования все доступные на компьютере ядра. Укажите явное число ядер, задав свойство MaxCpuCount в узле RunConfiguration в файле runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Запуск тестов, соответствующих заданному выражению. `<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`. Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`. Скобки `()` используются для группировки частей выражений.

`-?|--Help|/?|/Help`

Выводит краткую справку по команде.

`--logger|/logger:<Logger Uri/FriendlyName>`

Укажите средство ведения журнала результатов тестирования.

* Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`. Этот параметр создает файл журнала с заданным именем в каталоге результатов теста. Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Перечисление всех обнаруженных тестов из указанного контейнера тестов.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Идентификатор родительского процесса, отвечающего за запуск текущего процесса.

`--Port|/Port:<Port>`

Указывает порт для подключения сокета и получения сообщений о событиях.

`--Diag|/Diag:<Path to log file>`

Включает ведение подробных журналов для платформы тестирования. Журналы записываются в указанный файл.

`--Blame|/Blame`

Выполнение тестов в режиме обвинения. Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов. Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.

`--InIsolation|/InIsolation`

Запуск тестов в изолированном процессе. Это снижает вероятность остановки процесса *vstest.console.exe* при возникновении ошибки в тестах, однако тесты могут выполняться медленнее.

`@<file>`

Считывает файл ответов с дополнительными параметрами.

`args`

Задает дополнительные аргументы, передаваемые адаптеру. Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента. Для разделения аргументов используйте пробел.

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

Параметры, используемые при выполнении тестов.

`--Tests|/Tests:<Test Names>`

Выполните тесты с именами, которые соответствуют предусмотренным значениям. Для разделения значений используйте запятые.

`--TestAdapterPath|/TestAdapterPath`

Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.

`--Platform|/Platform:<Platform type>`

Архитектура целевой платформы, используемая для выполнения тестов. Допустимые значения: `x86`, `x64` и `ARM`.

`--Framework|/Framework:<Framework Version>`

Целевая версия платформы .NET Framework, используемая для выполнения тестов. Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`. Другие поддерживаемые значения: `Framework40`, `Framework45` и `FrameworkCore10`.

`--Parallel|/Parallel`

Выполняйте тесты в параллельном режиме. По умолчанию для использования все доступные на компьютере ядра. Укажите явное число ядер, задав свойство MaxCpuCount в узле RunConfiguration в файле runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Запуск тестов, соответствующих заданному выражению. `<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`. Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`. Скобки `()` используются для группировки частей выражений.

`-?|--Help|/?|/Help`

Выводит краткую справку по команде.

`--logger|/logger:<Logger Uri/FriendlyName>`

Укажите средство ведения журнала результатов тестирования.

* Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`. Этот параметр создает файл журнала с заданным именем в каталоге результатов теста. Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Перечисление всех обнаруженных тестов из указанного контейнера тестов.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Идентификатор родительского процесса, отвечающего за запуск текущего процесса.

`--Port|/Port:<Port>`

Указывает порт для подключения сокета и получения сообщений о событиях.

`--Diag|/Diag:<Path to log file>`

Включает ведение подробных журналов для платформы тестирования. Журналы записываются в указанный файл.

`args`

Задает дополнительные аргументы, передаваемые адаптеру. Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента. Для разделения аргументов используйте пробел.

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

Параметры, используемые при выполнении тестов.

`--Tests|/Tests:<Test Names>`

Выполните тесты с именами, которые соответствуют предусмотренным значениям. Для разделения значений используйте запятые.

`--TestAdapterPath|/TestAdapterPath`

Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.

`--Platform|/Platform:<Platform type>`

Архитектура целевой платформы, используемая для выполнения тестов. Допустимые значения: `x86`, `x64` и `ARM`.

`--Framework|/Framework:<Framework Version>`

Целевая версия платформы .NET Framework, используемая для выполнения тестов. Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`. Другие поддерживаемые значения: `Framework40`, `Framework45` и `FrameworkCore10`.

`--Parallel|/Parallel`

Выполняйте тесты в параллельном режиме. По умолчанию для использования все доступные на компьютере ядра. Укажите явное число ядер, задав свойство MaxCpuCount в узле RunConfiguration в файле runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Запуск тестов, соответствующих заданному выражению. `<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`. Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`. Скобки `()` используются для группировки частей выражений.

`-?|--Help|/?|/Help`

Выводит краткую справку по команде.

`--logger|/logger:<Logger Uri/FriendlyName>`

Укажите средство ведения журнала результатов тестирования.

* Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`. Этот параметр создает файл журнала с заданным именем в каталоге результатов теста. Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Перечисление всех обнаруженных тестов из указанного контейнера тестов.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Идентификатор родительского процесса, отвечающего за запуск текущего процесса.

`--Port|/Port:<Port>`

Указывает порт для подключения сокета и получения сообщений о событиях.

`--Diag|/Diag:<Path to log file>`

Включает ведение подробных журналов для платформы тестирования. Журналы записываются в указанный файл.

`args`

Задает дополнительные аргументы, передаваемые адаптеру. Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента. Для разделения аргументов используйте пробел.

---

## <a name="examples"></a>Примеры

Запуск тестов в `mytestproject.dll`:

`dotnet vstest mytestproject.dll`

Запуск тестов в `mytestproject.dll` с экспортом в настраиваемую папку с пользовательским именем:

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

Запуск тестов в `mytestproject.dll` и `myothertestproject.exe`:

`dotnet vstest mytestproject.dll myothertestproject.exe`

Запуск тестов `TestMethod1`:

`dotnet vstest /Tests:TestMethod1`

Запуск тестов `TestMethod1` и `TestMethod2`:

`dotnet vstest /Tests:TestMethod1,TestMethod2`
