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
# <a name="dotnet-vstest"></a><span data-ttu-id="a5157-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="a5157-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a5157-104">name</span><span class="sxs-lookup"><span data-stu-id="a5157-104">Name</span></span>

<span data-ttu-id="a5157-105">`dotnet-vstest` — запускает тесты из указанных файлов.</span><span class="sxs-lookup"><span data-stu-id="a5157-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a5157-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a5157-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="a5157-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a5157-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="a5157-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a5157-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="a5157-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a5157-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a><span data-ttu-id="a5157-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a5157-110">Description</span></span>

<span data-ttu-id="a5157-111">Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="a5157-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a5157-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="a5157-113">Запустите тесты из указанных сборок.</span><span class="sxs-lookup"><span data-stu-id="a5157-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="a5157-114">Для разделения имен тестовых сборок используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="a5157-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="a5157-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5157-115">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="a5157-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a5157-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="a5157-117">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="a5157-118">Выполните тесты с именами, которые соответствуют предусмотренным значениям.</span><span class="sxs-lookup"><span data-stu-id="a5157-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="a5157-119">Для разделения значений используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="a5157-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="a5157-120">Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="a5157-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="a5157-121">Архитектура целевой платформы, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="a5157-122">Допустимые значения: `x86`, `x64` и `ARM`.</span><span class="sxs-lookup"><span data-stu-id="a5157-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="a5157-123">Целевая версия платформы .NET Framework, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="a5157-124">Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="a5157-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="a5157-125">Другие поддерживаемые значения: `Framework40`, `Framework45`, `FrameworkCore10` и `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="a5157-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="a5157-126">Выполняйте тесты в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="a5157-126">Execute tests in parallel.</span></span> <span data-ttu-id="a5157-127">По умолчанию для использования все доступные на компьютере ядра.</span><span class="sxs-lookup"><span data-stu-id="a5157-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="a5157-128">Укажите явное число ядер, задав свойство MaxCpuCount в узле RunConfiguration в файле runsettings.</span><span class="sxs-lookup"><span data-stu-id="a5157-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="a5157-129">Запуск тестов, соответствующих заданному выражению.</span><span class="sxs-lookup"><span data-stu-id="a5157-129">Run tests that match the given expression.</span></span> <span data-ttu-id="a5157-130">`<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.</span><span class="sxs-lookup"><span data-stu-id="a5157-130">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="a5157-131">Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="a5157-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="a5157-132">Скобки `()` используются для группировки частей выражений.</span><span class="sxs-lookup"><span data-stu-id="a5157-132">Parenthesis `()` are used to group subexpressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="a5157-133">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a5157-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="a5157-134">Укажите средство ведения журнала результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="a5157-135">Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="a5157-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="a5157-136">Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`.</span><span class="sxs-lookup"><span data-stu-id="a5157-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="a5157-137">Этот параметр создает файл журнала с заданным именем в каталоге результатов теста.</span><span class="sxs-lookup"><span data-stu-id="a5157-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="a5157-138">Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="a5157-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="a5157-139">Перечисление всех обнаруженных тестов из указанного контейнера тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="a5157-140">Идентификатор родительского процесса, отвечающего за запуск текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="a5157-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="a5157-141">Указывает порт для подключения сокета и получения сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="a5157-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="a5157-142">Включает ведение подробных журналов для платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="a5157-143">Журналы записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="a5157-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="a5157-144">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="a5157-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="a5157-145">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="a5157-146">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="a5157-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="a5157-147">Запуск тестов в изолированном процессе.</span><span class="sxs-lookup"><span data-stu-id="a5157-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="a5157-148">Это снижает вероятность остановки процесса *vstest.console.exe* при возникновении ошибки в тестах, однако тесты могут выполняться медленнее.</span><span class="sxs-lookup"><span data-stu-id="a5157-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="a5157-149">Считывает файл ответов с дополнительными параметрами.</span><span class="sxs-lookup"><span data-stu-id="a5157-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="a5157-150">Задает дополнительные аргументы, передаваемые адаптеру.</span><span class="sxs-lookup"><span data-stu-id="a5157-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="a5157-151">Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента.</span><span class="sxs-lookup"><span data-stu-id="a5157-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="a5157-152">Для разделения аргументов используйте пробел.</span><span class="sxs-lookup"><span data-stu-id="a5157-152">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="a5157-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a5157-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="a5157-154">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="a5157-155">Выполните тесты с именами, которые соответствуют предусмотренным значениям.</span><span class="sxs-lookup"><span data-stu-id="a5157-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="a5157-156">Для разделения значений используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="a5157-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="a5157-157">Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="a5157-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="a5157-158">Архитектура целевой платформы, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="a5157-159">Допустимые значения: `x86`, `x64` и `ARM`.</span><span class="sxs-lookup"><span data-stu-id="a5157-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="a5157-160">Целевая версия платформы .NET Framework, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="a5157-161">Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="a5157-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="a5157-162">Другие поддерживаемые значения: `Framework40`, `Framework45` и `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="a5157-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="a5157-163">Выполняйте тесты в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="a5157-163">Execute tests in parallel.</span></span> <span data-ttu-id="a5157-164">По умолчанию для использования все доступные на компьютере ядра.</span><span class="sxs-lookup"><span data-stu-id="a5157-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="a5157-165">Укажите явное число ядер, задав свойство MaxCpuCount в узле RunConfiguration в файле runsettings.</span><span class="sxs-lookup"><span data-stu-id="a5157-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="a5157-166">Запуск тестов, соответствующих заданному выражению.</span><span class="sxs-lookup"><span data-stu-id="a5157-166">Run tests that match the given expression.</span></span> <span data-ttu-id="a5157-167">`<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.</span><span class="sxs-lookup"><span data-stu-id="a5157-167">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="a5157-168">Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="a5157-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="a5157-169">Скобки `()` используются для группировки частей выражений.</span><span class="sxs-lookup"><span data-stu-id="a5157-169">Parenthesis `()` are used to group subexpressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="a5157-170">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a5157-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="a5157-171">Укажите средство ведения журнала результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="a5157-172">Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="a5157-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="a5157-173">Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`.</span><span class="sxs-lookup"><span data-stu-id="a5157-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="a5157-174">Этот параметр создает файл журнала с заданным именем в каталоге результатов теста.</span><span class="sxs-lookup"><span data-stu-id="a5157-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="a5157-175">Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="a5157-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="a5157-176">Перечисление всех обнаруженных тестов из указанного контейнера тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="a5157-177">Идентификатор родительского процесса, отвечающего за запуск текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="a5157-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="a5157-178">Указывает порт для подключения сокета и получения сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="a5157-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="a5157-179">Включает ведение подробных журналов для платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="a5157-180">Журналы записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="a5157-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="a5157-181">Задает дополнительные аргументы, передаваемые адаптеру.</span><span class="sxs-lookup"><span data-stu-id="a5157-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="a5157-182">Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента.</span><span class="sxs-lookup"><span data-stu-id="a5157-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="a5157-183">Для разделения аргументов используйте пробел.</span><span class="sxs-lookup"><span data-stu-id="a5157-183">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="a5157-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a5157-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="a5157-185">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="a5157-186">Выполните тесты с именами, которые соответствуют предусмотренным значениям.</span><span class="sxs-lookup"><span data-stu-id="a5157-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="a5157-187">Для разделения значений используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="a5157-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="a5157-188">Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="a5157-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="a5157-189">Архитектура целевой платформы, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="a5157-190">Допустимые значения: `x86`, `x64` и `ARM`.</span><span class="sxs-lookup"><span data-stu-id="a5157-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="a5157-191">Целевая версия платформы .NET Framework, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="a5157-192">Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="a5157-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="a5157-193">Другие поддерживаемые значения: `Framework40`, `Framework45` и `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="a5157-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="a5157-194">Выполняйте тесты в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="a5157-194">Execute tests in parallel.</span></span> <span data-ttu-id="a5157-195">По умолчанию для использования все доступные на компьютере ядра.</span><span class="sxs-lookup"><span data-stu-id="a5157-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="a5157-196">Укажите явное число ядер, задав свойство MaxCpuCount в узле RunConfiguration в файле runsettings.</span><span class="sxs-lookup"><span data-stu-id="a5157-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="a5157-197">Запуск тестов, соответствующих заданному выражению.</span><span class="sxs-lookup"><span data-stu-id="a5157-197">Run tests that match the given expression.</span></span> <span data-ttu-id="a5157-198">`<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.</span><span class="sxs-lookup"><span data-stu-id="a5157-198">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="a5157-199">Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="a5157-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="a5157-200">Скобки `()` используются для группировки частей выражений.</span><span class="sxs-lookup"><span data-stu-id="a5157-200">Parenthesis `()` are used to group subexpressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="a5157-201">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a5157-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="a5157-202">Укажите средство ведения журнала результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="a5157-203">Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="a5157-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="a5157-204">Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`.</span><span class="sxs-lookup"><span data-stu-id="a5157-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="a5157-205">Этот параметр создает файл журнала с заданным именем в каталоге результатов теста.</span><span class="sxs-lookup"><span data-stu-id="a5157-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="a5157-206">Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="a5157-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="a5157-207">Перечисление всех обнаруженных тестов из указанного контейнера тестов.</span><span class="sxs-lookup"><span data-stu-id="a5157-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="a5157-208">Идентификатор родительского процесса, отвечающего за запуск текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="a5157-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="a5157-209">Указывает порт для подключения сокета и получения сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="a5157-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="a5157-210">Включает ведение подробных журналов для платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="a5157-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="a5157-211">Журналы записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="a5157-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="a5157-212">Задает дополнительные аргументы, передаваемые адаптеру.</span><span class="sxs-lookup"><span data-stu-id="a5157-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="a5157-213">Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента.</span><span class="sxs-lookup"><span data-stu-id="a5157-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="a5157-214">Для разделения аргументов используйте пробел.</span><span class="sxs-lookup"><span data-stu-id="a5157-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="a5157-215">Примеры</span><span class="sxs-lookup"><span data-stu-id="a5157-215">Examples</span></span>

<span data-ttu-id="a5157-216">Запуск тестов в `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="a5157-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="a5157-217">Запуск тестов в `mytestproject.dll` с экспортом в настраиваемую папку с пользовательским именем:</span><span class="sxs-lookup"><span data-stu-id="a5157-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="a5157-218">Запуск тестов в `mytestproject.dll` и `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="a5157-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="a5157-219">Запуск тестов `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="a5157-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="a5157-220">Запуск тестов `TestMethod1` и `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="a5157-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
