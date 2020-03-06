---
title: Команда dotnet vstest
description: Команда dotnet vstest выполняет сборку проекта и всех его зависимостей.
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156937"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="fc8b3-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="fc8b3-103">dotnet vstest</span></span>

<span data-ttu-id="fc8b3-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="fc8b3-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fc8b3-105">name</span><span class="sxs-lookup"><span data-stu-id="fc8b3-105">Name</span></span>

<span data-ttu-id="fc8b3-106">`dotnet-vstest` — запускает тесты из указанных файлов.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fc8b3-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fc8b3-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a><span data-ttu-id="fc8b3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fc8b3-108">Description</span></span>

<span data-ttu-id="fc8b3-109">Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="fc8b3-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fc8b3-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="fc8b3-111">Запустите тесты из указанных сборок.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="fc8b3-112">Для разделения имен тестовых сборок используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="fc8b3-113">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="fc8b3-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc8b3-114">Options</span></span>

- **`--Settings <Settings File>`**

  <span data-ttu-id="fc8b3-115">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-115">Settings to use when running tests.</span></span>

- **`--Tests <Test Names>`**

  <span data-ttu-id="fc8b3-116">Выполните тесты с именами, которые соответствуют предусмотренным значениям.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-116">Run tests with names that match the provided values.</span></span> <span data-ttu-id="fc8b3-117">Для разделения значений используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-117">Separate multiple values with commas.</span></span>

- **`--TestAdapterPath`**

  <span data-ttu-id="fc8b3-118">Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-118">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--Platform <Platform type>`**

  <span data-ttu-id="fc8b3-119">Архитектура целевой платформы, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-119">Target platform architecture used for test execution.</span></span> <span data-ttu-id="fc8b3-120">Допустимые значения: `x86`, `x64` и `ARM`.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-120">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Framework <Framework Version>`**

  <span data-ttu-id="fc8b3-121">Целевая версия платформы .NET Framework, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-121">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="fc8b3-122">Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-122">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="fc8b3-123">Другие поддерживаемые значения: `Framework40`, `Framework45`, `FrameworkCore10` и `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-123">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--Parallel`**

  <span data-ttu-id="fc8b3-124">Выполняйте тесты в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-124">Run tests in parallel.</span></span> <span data-ttu-id="fc8b3-125">По умолчанию для использования все доступные на компьютере ядра.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-125">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="fc8b3-126">Укажите явное число ядер, задав свойство `MaxCpuCount` в узле `RunConfiguration` в файле *runsettings*.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-126">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--TestCaseFilter <Expression>`**

  <span data-ttu-id="fc8b3-127">Запуск тестов, соответствующих заданному выражению.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-127">Run tests that match the given expression.</span></span> <span data-ttu-id="fc8b3-128">`<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-128">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="fc8b3-129">Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-129">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="fc8b3-130">Скобки `()` используются для группировки частей выражений.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-130">Parenthesis `()` are used to group subexpressions.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="fc8b3-131">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-131">Prints out a short help for the command.</span></span>

- **`--logger <Logger Uri/FriendlyName>`**

  <span data-ttu-id="fc8b3-132">Укажите средство ведения журнала результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-132">Specify a logger for test results.</span></span>

  - <span data-ttu-id="fc8b3-133">Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="fc8b3-133">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="fc8b3-134">Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-134">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="fc8b3-135">Этот параметр создает файл журнала с заданным именем в каталоге результатов теста.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-135">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="fc8b3-136">Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-136">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  <span data-ttu-id="fc8b3-137">Перечисление всех обнаруженных тестов из указанного контейнера тестов.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-137">Lists all discovered tests from the given test container.</span></span>

- **`--ParentProcessId <ParentProcessId>`**

  <span data-ttu-id="fc8b3-138">Идентификатор родительского процесса, отвечающего за запуск текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-138">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Port <Port>`**

  <span data-ttu-id="fc8b3-139">Указывает порт для подключения сокета и получения сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--Diag <Path to log file>`**

  <span data-ttu-id="fc8b3-140">Включает ведение подробных журналов для платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-140">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="fc8b3-141">Журналы записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-141">Logs are written to the provided file.</span></span>

- **`--Blame`**

  <span data-ttu-id="fc8b3-142">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-142">Runs the tests in blame mode.</span></span> <span data-ttu-id="fc8b3-143">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-143">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="fc8b3-144">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-144">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="fc8b3-145">Запуск тестов в изолированном процессе.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-145">Runs the tests in an isolated process.</span></span> <span data-ttu-id="fc8b3-146">Это снижает вероятность остановки процесса *vstest.console.exe* при возникновении ошибки в тестах, однако тесты могут выполняться медленнее.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-146">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`@<file>`**

  <span data-ttu-id="fc8b3-147">Считывает файл ответов с дополнительными параметрами.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-147">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="fc8b3-148">Задает дополнительные аргументы, передаваемые адаптеру.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-148">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="fc8b3-149">Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-149">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="fc8b3-150">Для разделения аргументов используйте пробел.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-150">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="fc8b3-151">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc8b3-151">Examples</span></span>

<span data-ttu-id="fc8b3-152">Запуск тестов в *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="fc8b3-152">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="fc8b3-153">Запуск тестов в *mytestproject.dll* с экспортом в настраиваемую папку с пользовательским именем:</span><span class="sxs-lookup"><span data-stu-id="fc8b3-153">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="fc8b3-154">Запуск тестов в *mytestproject.dll* и *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="fc8b3-154">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="fc8b3-155">Запуск тестов `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="fc8b3-155">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="fc8b3-156">Запуск тестов `TestMethod1` и `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="fc8b3-156">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
