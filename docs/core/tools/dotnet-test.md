---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 05/29/2018
ms.openlocfilehash: 1b2a3917a930db0c0a49ebea41f568aaf4a58ee3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535286"
---
# <a name="dotnet-test"></a><span data-ttu-id="27433-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="27433-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="27433-104">name</span><span class="sxs-lookup"><span data-stu-id="27433-104">Name</span></span>

<span data-ttu-id="27433-105">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="27433-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="27433-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="27433-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="27433-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="27433-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="27433-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="27433-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="27433-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="27433-110">Описание</span><span class="sxs-lookup"><span data-stu-id="27433-110">Description</span></span>

<span data-ttu-id="27433-111">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="27433-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="27433-112">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="27433-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="27433-113">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="27433-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="27433-114">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="27433-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="27433-115">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="27433-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="27433-116">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="27433-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="27433-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="27433-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="27433-118">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="27433-118">Path to the test project.</span></span> <span data-ttu-id="27433-119">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="27433-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="27433-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="27433-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="27433-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="27433-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="27433-122">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="27433-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="27433-123">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="27433-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="27433-124">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="27433-125">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="27433-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="27433-126">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="27433-126">Defines the build configuration.</span></span> <span data-ttu-id="27433-127">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27433-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="27433-128">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="27433-128">Enables data collector for the test run.</span></span> <span data-ttu-id="27433-129">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="27433-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="27433-130">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="27433-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="27433-131">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="27433-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="27433-132">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="27433-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="27433-133">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="27433-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="27433-134">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="27433-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="27433-135">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="27433-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="27433-136">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="27433-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="27433-137">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="27433-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="27433-138">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="27433-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="27433-139">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="27433-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="27433-140">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="27433-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="27433-141">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="27433-142">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="27433-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="27433-143">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="27433-144">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="27433-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="27433-145">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="27433-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="27433-146">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="27433-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="27433-147">Аргументы, передаваемые в качестве конфигураций RunSettings для теста.</span><span class="sxs-lookup"><span data-stu-id="27433-147">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="27433-148">Аргументы задаются в виде пар `[name]=[value]` после "-- " (обратите внимание на пробел после --).</span><span class="sxs-lookup"><span data-stu-id="27433-148">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="27433-149">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="27433-149">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="27433-150">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="27433-150">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="27433-151">Дополнительные сведения о RunSettings см. в статье о [передаче аргументов RunSettings в командной строке](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="27433-151">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="27433-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="27433-152">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="27433-153">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="27433-153">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="27433-154">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="27433-154">Defines the build configuration.</span></span> <span data-ttu-id="27433-155">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27433-155">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="27433-156">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="27433-156">Enables data collector for the test run.</span></span> <span data-ttu-id="27433-157">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="27433-157">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="27433-158">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="27433-158">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="27433-159">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="27433-159">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="27433-160">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="27433-160">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="27433-161">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="27433-161">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="27433-162">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="27433-162">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="27433-163">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="27433-163">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="27433-164">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="27433-164">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="27433-165">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="27433-165">Doesn't build the test project before running it.</span></span> <span data-ttu-id="27433-166">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="27433-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="27433-167">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="27433-167">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="27433-168">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="27433-168">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="27433-169">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-169">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="27433-170">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="27433-170">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="27433-171">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-171">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="27433-172">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="27433-172">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="27433-173">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="27433-173">Sets the verbosity level of the command.</span></span> <span data-ttu-id="27433-174">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="27433-174">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="27433-175">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="27433-175">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="27433-176">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="27433-176">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="27433-177">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="27433-177">Defines the build configuration.</span></span> <span data-ttu-id="27433-178">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27433-178">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="27433-179">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="27433-179">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="27433-180">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="27433-180">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="27433-181">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="27433-181">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="27433-182">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="27433-182">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="27433-183">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="27433-183">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="27433-184">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="27433-184">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="27433-185">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="27433-185">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="27433-186">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="27433-186">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="27433-187">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="27433-187">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="27433-188">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-188">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="27433-189">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="27433-189">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="27433-190">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="27433-190">Sets the verbosity level of the command.</span></span> <span data-ttu-id="27433-191">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="27433-191">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="27433-192">Примеры</span><span class="sxs-lookup"><span data-stu-id="27433-192">Examples</span></span>

<span data-ttu-id="27433-193">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="27433-193">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="27433-194">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="27433-194">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="27433-195">Выполнение тестов в проекте в текущем каталоге и создание файл результатов теста в формате trx:</span><span class="sxs-lookup"><span data-stu-id="27433-195">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="27433-196">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="27433-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="27433-197">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="27433-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="27433-198">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="27433-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="27433-199">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="27433-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="27433-200">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="27433-200">Test Framework</span></span> | <span data-ttu-id="27433-201">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="27433-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="27433-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="27433-202">MSTest</span></span>         | <ul><li><span data-ttu-id="27433-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="27433-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="27433-204">name</span><span class="sxs-lookup"><span data-stu-id="27433-204">Name</span></span></li><li><span data-ttu-id="27433-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="27433-205">ClassName</span></span></li><li><span data-ttu-id="27433-206">Приоритет</span><span class="sxs-lookup"><span data-stu-id="27433-206">Priority</span></span></li><li><span data-ttu-id="27433-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="27433-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="27433-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="27433-208">xUnit</span></span>          | <ul><li><span data-ttu-id="27433-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="27433-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="27433-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="27433-210">DisplayName</span></span></li><li><span data-ttu-id="27433-211">Признаки</span><span class="sxs-lookup"><span data-stu-id="27433-211">Traits</span></span></li></ul>                                   |

<span data-ttu-id="27433-212">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="27433-212">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="27433-213">Оператор</span><span class="sxs-lookup"><span data-stu-id="27433-213">Operator</span></span> | <span data-ttu-id="27433-214">Функция</span><span class="sxs-lookup"><span data-stu-id="27433-214">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="27433-215">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="27433-215">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="27433-216">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="27433-216">Not exact match</span></span> |
| `~`      | <span data-ttu-id="27433-217">Содержит</span><span class="sxs-lookup"><span data-stu-id="27433-217">Contains</span></span>        |

<span data-ttu-id="27433-218">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="27433-218">`<value>` is a string.</span></span> <span data-ttu-id="27433-219">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="27433-219">All the lookups are case insensitive.</span></span>

<span data-ttu-id="27433-220">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="27433-220">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="27433-221">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="27433-221">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="27433-222">Оператор</span><span class="sxs-lookup"><span data-stu-id="27433-222">Operator</span></span>            | <span data-ttu-id="27433-223">Функция</span><span class="sxs-lookup"><span data-stu-id="27433-223">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="27433-224">OR</span><span class="sxs-lookup"><span data-stu-id="27433-224">OR</span></span>       |
| `&`                 | <span data-ttu-id="27433-225">AND</span><span class="sxs-lookup"><span data-stu-id="27433-225">AND</span></span>      |

<span data-ttu-id="27433-226">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="27433-226">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="27433-227">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="27433-227">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27433-228">См. также</span><span class="sxs-lookup"><span data-stu-id="27433-228">See also</span></span>

- [<span data-ttu-id="27433-229">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="27433-229">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="27433-230">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="27433-230">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
