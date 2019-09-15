---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 05/29/2018
ms.openlocfilehash: 49926b35b418e93237a159758903c535ec6c4006
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988554"
---
# <a name="dotnet-test"></a><span data-ttu-id="1ca7c-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1ca7c-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1ca7c-104">name</span><span class="sxs-lookup"><span data-stu-id="1ca7c-104">Name</span></span>

<span data-ttu-id="1ca7c-105">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1ca7c-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1ca7c-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1ca7c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1ca7c-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1ca7c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1ca7c-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1ca7c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1ca7c-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="1ca7c-110">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="1ca7c-110">Description</span></span>

<span data-ttu-id="1ca7c-111">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="1ca7c-112">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="1ca7c-113">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="1ca7c-114">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="1ca7c-115">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="1ca7c-116">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="1ca7c-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="1ca7c-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1ca7c-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="1ca7c-118">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-118">Path to the test project.</span></span> <span data-ttu-id="1ca7c-119">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="1ca7c-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ca7c-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1ca7c-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1ca7c-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="1ca7c-122">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="1ca7c-123">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="1ca7c-124">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="1ca7c-125">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1ca7c-126">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-126">Defines the build configuration.</span></span> <span data-ttu-id="1ca7c-127">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="1ca7c-128">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-128">Enables data collector for the test run.</span></span> <span data-ttu-id="1ca7c-129">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="1ca7c-130">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1ca7c-131">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1ca7c-132">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1ca7c-133">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1ca7c-134">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="1ca7c-135">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="1ca7c-136">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="1ca7c-137">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1ca7c-138">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="1ca7c-139">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1ca7c-140">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="1ca7c-141">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1ca7c-142">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="1ca7c-143">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="1ca7c-144">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="1ca7c-145">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1ca7c-146">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1ca7c-147">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="1ca7c-148">Аргументы, передаваемые в качестве конфигураций RunSettings для теста.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="1ca7c-149">Аргументы задаются в виде пар `[name]=[value]` после "-- " (обратите внимание на пробел после --).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="1ca7c-150">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="1ca7c-151">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="1ca7c-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="1ca7c-152">Дополнительные сведения о RunSettings см. в статье о [передаче аргументов RunSettings в командной строке](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1ca7c-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1ca7c-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="1ca7c-154">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1ca7c-155">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-155">Defines the build configuration.</span></span> <span data-ttu-id="1ca7c-156">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="1ca7c-157">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-157">Enables data collector for the test run.</span></span> <span data-ttu-id="1ca7c-158">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="1ca7c-159">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1ca7c-160">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1ca7c-161">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1ca7c-162">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1ca7c-163">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="1ca7c-164">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="1ca7c-165">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="1ca7c-166">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1ca7c-167">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="1ca7c-168">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1ca7c-169">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="1ca7c-170">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1ca7c-171">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="1ca7c-172">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="1ca7c-173">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="1ca7c-174">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1ca7c-175">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1ca7c-176">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1ca7c-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1ca7c-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="1ca7c-178">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1ca7c-179">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-179">Defines the build configuration.</span></span> <span data-ttu-id="1ca7c-180">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="1ca7c-181">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1ca7c-182">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1ca7c-183">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1ca7c-184">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1ca7c-185">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="1ca7c-186">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="1ca7c-187">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="1ca7c-188">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1ca7c-189">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="1ca7c-190">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="1ca7c-191">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="1ca7c-192">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1ca7c-193">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1ca7c-194">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="1ca7c-195">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ca7c-195">Examples</span></span>

<span data-ttu-id="1ca7c-196">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="1ca7c-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="1ca7c-197">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="1ca7c-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="1ca7c-198">Выполнение тестов в проекте в текущем каталоге и создание файл результатов теста в формате trx:</span><span class="sxs-lookup"><span data-stu-id="1ca7c-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger trx`

## <a name="filter-option-details"></a><span data-ttu-id="1ca7c-199">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="1ca7c-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1ca7c-200">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="1ca7c-201">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="1ca7c-202">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="1ca7c-203">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="1ca7c-203">Test Framework</span></span> | <span data-ttu-id="1ca7c-204">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="1ca7c-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1ca7c-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="1ca7c-205">MSTest</span></span>         | <ul><li><span data-ttu-id="1ca7c-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1ca7c-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="1ca7c-207">name</span><span class="sxs-lookup"><span data-stu-id="1ca7c-207">Name</span></span></li><li><span data-ttu-id="1ca7c-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="1ca7c-208">ClassName</span></span></li><li><span data-ttu-id="1ca7c-209">Приоритет</span><span class="sxs-lookup"><span data-stu-id="1ca7c-209">Priority</span></span></li><li><span data-ttu-id="1ca7c-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="1ca7c-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="1ca7c-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="1ca7c-211">xUnit</span></span>          | <ul><li><span data-ttu-id="1ca7c-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1ca7c-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="1ca7c-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1ca7c-213">DisplayName</span></span></li><li><span data-ttu-id="1ca7c-214">Признаки</span><span class="sxs-lookup"><span data-stu-id="1ca7c-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="1ca7c-215">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="1ca7c-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="1ca7c-216">Оператор</span><span class="sxs-lookup"><span data-stu-id="1ca7c-216">Operator</span></span> | <span data-ttu-id="1ca7c-217">Функция</span><span class="sxs-lookup"><span data-stu-id="1ca7c-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="1ca7c-218">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="1ca7c-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="1ca7c-219">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="1ca7c-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="1ca7c-220">Содержит</span><span class="sxs-lookup"><span data-stu-id="1ca7c-220">Contains</span></span>        |

<span data-ttu-id="1ca7c-221">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-221">`<value>` is a string.</span></span> <span data-ttu-id="1ca7c-222">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="1ca7c-223">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="1ca7c-224">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="1ca7c-225">Оператор</span><span class="sxs-lookup"><span data-stu-id="1ca7c-225">Operator</span></span>            | <span data-ttu-id="1ca7c-226">Функция</span><span class="sxs-lookup"><span data-stu-id="1ca7c-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="1ca7c-227">OR</span><span class="sxs-lookup"><span data-stu-id="1ca7c-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="1ca7c-228">AND</span><span class="sxs-lookup"><span data-stu-id="1ca7c-228">AND</span></span>      |

<span data-ttu-id="1ca7c-229">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="1ca7c-230">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1ca7c-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ca7c-231">См. также</span><span class="sxs-lookup"><span data-stu-id="1ca7c-231">See also</span></span>

- [<span data-ttu-id="1ca7c-232">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="1ca7c-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="1ca7c-233">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="1ca7c-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
