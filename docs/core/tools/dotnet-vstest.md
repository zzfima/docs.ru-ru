---
title: "Команда dotnet-vstest | Документы Майкрософт"
description: "Команда dotnet-vstest выполняет сборку проекта и всех его зависимостей."
keywords: "dotnet-vstest, CLI, команда CLI, .NET Core"
author: guardrex
ms.author: mairaw
ms.date: 03/09/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0e36c070-2242-41d3-96f1-aea0aca48d4d
translationtype: Human Translation
ms.sourcegitcommit: 4a1f0c88fb1ccd6694f8d4f5687431646adbe000
ms.openlocfilehash: 27b96e74ae1abc83ba527cb799db33bec7af35bf
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-vstest"></a>dotnet-vstest

## <a name="name"></a>Имя

`dotnet-vstest` — запускает тесты из указанных файлов.

## <a name="synopsis"></a>Краткий обзор

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a>Описание

Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования и закодированных тестов пользовательского интерфейса.

## <a name="arguments"></a>Аргументы

`TEST_FILE_NAMES`

Запустите тесты из указанных сборок. Для разделения имен тестовых сборок используйте пробелы.

## <a name="options"></a>Параметры

`--Settings|/Settings:<Settings File>`

Параметры, используемые при выполнении тестов.

`--Tests|/Tests:<Test Names>`

Выполните тесты с именами, которые соответствуют предусмотренным значениям. Для разделения значений используйте запятые.

`--TestAdapterPath|/TestAdapterPath`

Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.

`--Platform|/Platform:<Platform type>`

Архитектура целевой платформы, используемая для выполнения тестов. Допустимые значения: `x86`, `x64` и `ARM`.

`--Framework|/Framework:<Framework Version>`

Целевая версия платформы .NET Framework, используемая для выполнения тестов. Примеры допустимых значений: `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` и т. п. Другие поддерживаемые значения: `Framework35`, `Framework40`, `Framework45` и `FrameworkCore10`.

`--Parallel|/Parallel`

Выполняйте тесты в параллельном режиме. По умолчанию для использования все доступные на компьютере ядра. Задайте явное число ядер с помощью файла параметров.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Запуск тестов, соответствующих заданному выражению. `<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.  Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`. Скобки `()` используются для группировки частей выражений.

`-?|--Help|/?|/Help`

Выводит краткую справку по команде.

`--logger|/logger:<Logger Uri/FriendlyName>`

Укажите средство ведения журнала результатов тестирования.  

* Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`. Этот параметр создает файл журнала с заданным именем в каталоге результатов теста. Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Перечисление обнаруженных тестов из указанного контейнера тестов.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Идентификатор родительского процесса, отвечающего за запуск текущего процесса.

`--Port|/Port:<Port>`

Указывает порт для подключения сокета и получения сообщений о событиях.

`--Diag|/Diag:<Path to log file>`

Включает ведение подробных журналов для платформы тестирования. Журналы записываются в указанный файл.

`args`

Задает дополнительные аргументы, передаваемые адаптеру. Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента. Для разделения аргументов используйте пробел.

## <a name="examples"></a>Примеры

Запуск тестов в `mytestproject.dll`:

`dotnet vstest mytestproject.dll`

Запуск тестов в `mytestproject.dll` и `myothertestproject.exe`:

`dotnet vstest mytestproject.dll myothertestproject.exe`

Запуск тестов `TestMethod1`:

`dotnet vstest /Tests:TestMethod1`

Запуск тестов `TestMethod1` и `TestMethod2`:

`dotnet vstest /Tests:TestMethod1,TestMethod2`

