---
title: Команда dotnet test — CLI .NET Core
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e80ba874ec8d0fbc49858719dc3b9b6e02254c78
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696460"
---
# <a name="dotnet-test"></a><span data-ttu-id="21ed7-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="21ed7-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="21ed7-104">name</span><span class="sxs-lookup"><span data-stu-id="21ed7-104">Name</span></span>

<span data-ttu-id="21ed7-105">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="21ed7-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="21ed7-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="21ed7-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21ed7-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="21ed7-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="21ed7-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="21ed7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="21ed7-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="21ed7-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="21ed7-110">Description</span></span>

<span data-ttu-id="21ed7-111">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="21ed7-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="21ed7-112">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="21ed7-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="21ed7-113">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="21ed7-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="21ed7-114">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="21ed7-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="21ed7-115">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="21ed7-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="21ed7-116">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="21ed7-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="21ed7-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="21ed7-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="21ed7-118">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="21ed7-118">Path to the test project.</span></span> <span data-ttu-id="21ed7-119">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="21ed7-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="21ed7-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="21ed7-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="21ed7-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21ed7-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="21ed7-122">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="21ed7-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="21ed7-123">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="21ed7-124">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="21ed7-125">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="21ed7-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="21ed7-126">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="21ed7-126">Defines the build configuration.</span></span> <span data-ttu-id="21ed7-127">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="21ed7-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="21ed7-128">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="21ed7-128">Enables data collector for the test run.</span></span> <span data-ttu-id="21ed7-129">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="21ed7-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="21ed7-130">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="21ed7-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="21ed7-131">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="21ed7-132">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="21ed7-133">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="21ed7-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="21ed7-134">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="21ed7-135">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="21ed7-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="21ed7-136">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="21ed7-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="21ed7-137">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="21ed7-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="21ed7-138">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="21ed7-139">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="21ed7-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="21ed7-140">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="21ed7-141">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="21ed7-142">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="21ed7-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="21ed7-143">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="21ed7-144">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="21ed7-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="21ed7-145">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="21ed7-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="21ed7-146">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="21ed7-147">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="21ed7-147">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="21ed7-148">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="21ed7-148">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="21ed7-149">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="21ed7-149">Defines the build configuration.</span></span> <span data-ttu-id="21ed7-150">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="21ed7-150">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="21ed7-151">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="21ed7-151">Enables data collector for the test run.</span></span> <span data-ttu-id="21ed7-152">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="21ed7-152">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="21ed7-153">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="21ed7-153">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="21ed7-154">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-154">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="21ed7-155">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-155">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="21ed7-156">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="21ed7-156">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="21ed7-157">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-157">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="21ed7-158">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="21ed7-158">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="21ed7-159">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="21ed7-159">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="21ed7-160">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="21ed7-160">Doesn't build the test project before running it.</span></span> <span data-ttu-id="21ed7-161">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-161">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="21ed7-162">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="21ed7-162">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="21ed7-163">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-163">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="21ed7-164">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-164">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="21ed7-165">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="21ed7-165">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="21ed7-166">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-166">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="21ed7-167">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="21ed7-167">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="21ed7-168">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="21ed7-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="21ed7-169">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="21ed7-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="21ed7-170">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="21ed7-171">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="21ed7-171">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="21ed7-172">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="21ed7-172">Defines the build configuration.</span></span> <span data-ttu-id="21ed7-173">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="21ed7-173">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="21ed7-174">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="21ed7-174">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="21ed7-175">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-175">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="21ed7-176">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-176">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="21ed7-177">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="21ed7-177">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="21ed7-178">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-178">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="21ed7-179">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="21ed7-179">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="21ed7-180">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="21ed7-180">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="21ed7-181">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="21ed7-181">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="21ed7-182">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="21ed7-182">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="21ed7-183">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-183">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="21ed7-184">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="21ed7-184">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="21ed7-185">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="21ed7-185">Sets the verbosity level of the command.</span></span> <span data-ttu-id="21ed7-186">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="21ed7-187">Примеры</span><span class="sxs-lookup"><span data-stu-id="21ed7-187">Examples</span></span>

<span data-ttu-id="21ed7-188">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="21ed7-188">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="21ed7-189">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="21ed7-189">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="21ed7-190">Выполнение тестов в проекте в текущем каталоге и создание файл результатов теста в формате trx:</span><span class="sxs-lookup"><span data-stu-id="21ed7-190">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="21ed7-191">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="21ed7-191">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="21ed7-192">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-192">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="21ed7-193">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="21ed7-193">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="21ed7-194">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="21ed7-194">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="21ed7-195">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="21ed7-195">Test Framework</span></span> | <span data-ttu-id="21ed7-196">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="21ed7-196">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="21ed7-197">MSTest</span><span class="sxs-lookup"><span data-stu-id="21ed7-197">MSTest</span></span>         | <ul><li><span data-ttu-id="21ed7-198">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="21ed7-198">FullyQualifiedName</span></span></li><li><span data-ttu-id="21ed7-199">name</span><span class="sxs-lookup"><span data-stu-id="21ed7-199">Name</span></span></li><li><span data-ttu-id="21ed7-200">ClassName</span><span class="sxs-lookup"><span data-stu-id="21ed7-200">ClassName</span></span></li><li><span data-ttu-id="21ed7-201">Приоритет</span><span class="sxs-lookup"><span data-stu-id="21ed7-201">Priority</span></span></li><li><span data-ttu-id="21ed7-202">TestCategory</span><span class="sxs-lookup"><span data-stu-id="21ed7-202">TestCategory</span></span></li></ul> |
| <span data-ttu-id="21ed7-203">xUnit</span><span class="sxs-lookup"><span data-stu-id="21ed7-203">xUnit</span></span>          | <ul><li><span data-ttu-id="21ed7-204">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="21ed7-204">FullyQualifiedName</span></span></li><li><span data-ttu-id="21ed7-205">DisplayName</span><span class="sxs-lookup"><span data-stu-id="21ed7-205">DisplayName</span></span></li><li><span data-ttu-id="21ed7-206">Признаки</span><span class="sxs-lookup"><span data-stu-id="21ed7-206">Traits</span></span></li></ul>                                   |

<span data-ttu-id="21ed7-207">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="21ed7-207">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="21ed7-208">Оператор</span><span class="sxs-lookup"><span data-stu-id="21ed7-208">Operator</span></span> | <span data-ttu-id="21ed7-209">Функция</span><span class="sxs-lookup"><span data-stu-id="21ed7-209">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="21ed7-210">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="21ed7-210">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="21ed7-211">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="21ed7-211">Not exact match</span></span> |
| `~`      | <span data-ttu-id="21ed7-212">Содержит</span><span class="sxs-lookup"><span data-stu-id="21ed7-212">Contains</span></span>        |

<span data-ttu-id="21ed7-213">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="21ed7-213">`<value>` is a string.</span></span> <span data-ttu-id="21ed7-214">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="21ed7-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="21ed7-215">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="21ed7-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="21ed7-216">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="21ed7-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="21ed7-217">Оператор</span><span class="sxs-lookup"><span data-stu-id="21ed7-217">Operator</span></span>            | <span data-ttu-id="21ed7-218">Функция</span><span class="sxs-lookup"><span data-stu-id="21ed7-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="21ed7-219">OR</span><span class="sxs-lookup"><span data-stu-id="21ed7-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="21ed7-220">AND</span><span class="sxs-lookup"><span data-stu-id="21ed7-220">AND</span></span>      |

<span data-ttu-id="21ed7-221">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="21ed7-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="21ed7-222">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="21ed7-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21ed7-223">См. также</span><span class="sxs-lookup"><span data-stu-id="21ed7-223">See also</span></span>

* [<span data-ttu-id="21ed7-224">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="21ed7-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="21ed7-225">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="21ed7-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
