---
title: Команда dotnet test — CLI .NET Core
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 8a10ac9175ee5fcf8649efbb07d8d382ac3afdc7
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696274"
---
# <a name="dotnet-test"></a><span data-ttu-id="572ca-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="572ca-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="572ca-104">name</span><span class="sxs-lookup"><span data-stu-id="572ca-104">Name</span></span>

<span data-ttu-id="572ca-105">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="572ca-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="572ca-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="572ca-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="572ca-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="572ca-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="572ca-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="572ca-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="572ca-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="572ca-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="572ca-110">Description</span></span>

<span data-ttu-id="572ca-111">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="572ca-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="572ca-112">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="572ca-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="572ca-113">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="572ca-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="572ca-114">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="572ca-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="572ca-115">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="572ca-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="572ca-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="572ca-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="572ca-117">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="572ca-117">Path to the test project.</span></span> <span data-ttu-id="572ca-118">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="572ca-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="572ca-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="572ca-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="572ca-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="572ca-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="572ca-121">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="572ca-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="572ca-122">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="572ca-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="572ca-123">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="572ca-124">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="572ca-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="572ca-125">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="572ca-125">Defines the build configuration.</span></span> <span data-ttu-id="572ca-126">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="572ca-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="572ca-127">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="572ca-127">Enables data collector for the test run.</span></span> <span data-ttu-id="572ca-128">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="572ca-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="572ca-129">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="572ca-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="572ca-130">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="572ca-131">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="572ca-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="572ca-132">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="572ca-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="572ca-133">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="572ca-134">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="572ca-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="572ca-135">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="572ca-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="572ca-136">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="572ca-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="572ca-137">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="572ca-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="572ca-138">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="572ca-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="572ca-139">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="572ca-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="572ca-140">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="572ca-141">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="572ca-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="572ca-142">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="572ca-143">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="572ca-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="572ca-144">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="572ca-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="572ca-145">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="572ca-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="572ca-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="572ca-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="572ca-147">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="572ca-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="572ca-148">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="572ca-148">Defines the build configuration.</span></span> <span data-ttu-id="572ca-149">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="572ca-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="572ca-150">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="572ca-150">Enables data collector for the test run.</span></span> <span data-ttu-id="572ca-151">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="572ca-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="572ca-152">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="572ca-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="572ca-153">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="572ca-154">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="572ca-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="572ca-155">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="572ca-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="572ca-156">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="572ca-157">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="572ca-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="572ca-158">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="572ca-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="572ca-159">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="572ca-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="572ca-160">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="572ca-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="572ca-161">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="572ca-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="572ca-162">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="572ca-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="572ca-163">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="572ca-164">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="572ca-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="572ca-165">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="572ca-166">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="572ca-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="572ca-167">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="572ca-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="572ca-168">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="572ca-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="572ca-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="572ca-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="572ca-170">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="572ca-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="572ca-171">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="572ca-171">Defines the build configuration.</span></span> <span data-ttu-id="572ca-172">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="572ca-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="572ca-173">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="572ca-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="572ca-174">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="572ca-175">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="572ca-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="572ca-176">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="572ca-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="572ca-177">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="572ca-178">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="572ca-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="572ca-179">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="572ca-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="572ca-180">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="572ca-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="572ca-181">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="572ca-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="572ca-182">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="572ca-183">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="572ca-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="572ca-184">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="572ca-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="572ca-185">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="572ca-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="572ca-186">Примеры</span><span class="sxs-lookup"><span data-stu-id="572ca-186">Examples</span></span>

<span data-ttu-id="572ca-187">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="572ca-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="572ca-188">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="572ca-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="572ca-189">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="572ca-189">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="572ca-190">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="572ca-190">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="572ca-191">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="572ca-191">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="572ca-192">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="572ca-192">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="572ca-193">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="572ca-193">Test Framework</span></span> | <span data-ttu-id="572ca-194">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="572ca-194">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="572ca-195">MSTest</span><span class="sxs-lookup"><span data-stu-id="572ca-195">MSTest</span></span>         | <ul><li><span data-ttu-id="572ca-196">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="572ca-196">FullyQualifiedName</span></span></li><li><span data-ttu-id="572ca-197">name</span><span class="sxs-lookup"><span data-stu-id="572ca-197">Name</span></span></li><li><span data-ttu-id="572ca-198">ClassName</span><span class="sxs-lookup"><span data-stu-id="572ca-198">ClassName</span></span></li><li><span data-ttu-id="572ca-199">Приоритет</span><span class="sxs-lookup"><span data-stu-id="572ca-199">Priority</span></span></li><li><span data-ttu-id="572ca-200">TestCategory</span><span class="sxs-lookup"><span data-stu-id="572ca-200">TestCategory</span></span></li></ul> |
| <span data-ttu-id="572ca-201">xUnit</span><span class="sxs-lookup"><span data-stu-id="572ca-201">xUnit</span></span>          | <ul><li><span data-ttu-id="572ca-202">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="572ca-202">FullyQualifiedName</span></span></li><li><span data-ttu-id="572ca-203">DisplayName</span><span class="sxs-lookup"><span data-stu-id="572ca-203">DisplayName</span></span></li><li><span data-ttu-id="572ca-204">Признаки</span><span class="sxs-lookup"><span data-stu-id="572ca-204">Traits</span></span></li></ul>                                   |

<span data-ttu-id="572ca-205">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="572ca-205">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="572ca-206">Оператор</span><span class="sxs-lookup"><span data-stu-id="572ca-206">Operator</span></span> | <span data-ttu-id="572ca-207">Функция</span><span class="sxs-lookup"><span data-stu-id="572ca-207">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="572ca-208">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="572ca-208">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="572ca-209">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="572ca-209">Not exact match</span></span> |
| `~`      | <span data-ttu-id="572ca-210">Содержит</span><span class="sxs-lookup"><span data-stu-id="572ca-210">Contains</span></span>        |

<span data-ttu-id="572ca-211">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="572ca-211">`<value>` is a string.</span></span> <span data-ttu-id="572ca-212">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="572ca-212">All the lookups are case insensitive.</span></span>

<span data-ttu-id="572ca-213">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="572ca-213">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="572ca-214">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="572ca-214">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="572ca-215">Оператор</span><span class="sxs-lookup"><span data-stu-id="572ca-215">Operator</span></span>            | <span data-ttu-id="572ca-216">Функция</span><span class="sxs-lookup"><span data-stu-id="572ca-216">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="572ca-217">OR</span><span class="sxs-lookup"><span data-stu-id="572ca-217">OR</span></span>       |
| `&`                 | <span data-ttu-id="572ca-218">AND</span><span class="sxs-lookup"><span data-stu-id="572ca-218">AND</span></span>      |

<span data-ttu-id="572ca-219">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="572ca-219">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="572ca-220">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="572ca-220">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="572ca-221">См. также</span><span class="sxs-lookup"><span data-stu-id="572ca-221">See also</span></span>

[<span data-ttu-id="572ca-222">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="572ca-222">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
[<span data-ttu-id="572ca-223">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="572ca-223">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
