---
title: Команда dotnet test — CLI .NET Core
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 04af96bb53cc4fdac2e52311f9197eb1ee2b112d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="36b75-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="36b75-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="36b75-104">name</span><span class="sxs-lookup"><span data-stu-id="36b75-104">Name</span></span>

<span data-ttu-id="36b75-105">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="36b75-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="36b75-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="36b75-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="36b75-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="36b75-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="36b75-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="36b75-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="36b75-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="36b75-109">Description</span></span>

<span data-ttu-id="36b75-110">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="36b75-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="36b75-111">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="36b75-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="36b75-112">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="36b75-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="36b75-113">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="36b75-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="36b75-114">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="36b75-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="36b75-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="36b75-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="36b75-116">Указывает путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="36b75-116">Specifies a path to the test project.</span></span> <span data-ttu-id="36b75-117">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="36b75-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="36b75-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="36b75-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="36b75-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="36b75-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="36b75-120">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="36b75-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="36b75-121">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="36b75-121">Defines the build configuration.</span></span> <span data-ttu-id="36b75-122">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36b75-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="36b75-123">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="36b75-123">Enables data collector for the test run.</span></span> <span data-ttu-id="36b75-124">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="36b75-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="36b75-125">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="36b75-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="36b75-126">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="36b75-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="36b75-127">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="36b75-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="36b75-128">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="36b75-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="36b75-129">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="36b75-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="36b75-130">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="36b75-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="36b75-131">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="36b75-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="36b75-132">Не выполняет сборку тестового проекта перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="36b75-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="36b75-133">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="36b75-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="36b75-134">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="36b75-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="36b75-135">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="36b75-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="36b75-136">Если указанный каталог не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="36b75-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="36b75-137">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="36b75-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="36b75-138">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="36b75-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="36b75-139">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="36b75-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="36b75-140">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="36b75-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="36b75-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="36b75-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="36b75-142">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="36b75-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="36b75-143">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="36b75-143">Defines the build configuration.</span></span> <span data-ttu-id="36b75-144">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36b75-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="36b75-145">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="36b75-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="36b75-146">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="36b75-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="36b75-147">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="36b75-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="36b75-148">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="36b75-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="36b75-149">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="36b75-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="36b75-150">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="36b75-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="36b75-151">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="36b75-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="36b75-152">Не выполняет сборку тестового проекта перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="36b75-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="36b75-153">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="36b75-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="36b75-154">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="36b75-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="36b75-155">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="36b75-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="36b75-156">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="36b75-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="36b75-157">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="36b75-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="36b75-158">Примеры</span><span class="sxs-lookup"><span data-stu-id="36b75-158">Examples</span></span>

<span data-ttu-id="36b75-159">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="36b75-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="36b75-160">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="36b75-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="36b75-161">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="36b75-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="36b75-162">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="36b75-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="36b75-163">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="36b75-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="36b75-164">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="36b75-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="36b75-165">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="36b75-165">Test Framework</span></span> | <span data-ttu-id="36b75-166">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="36b75-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="36b75-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="36b75-167">MSTest</span></span>         | <ul><li><span data-ttu-id="36b75-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="36b75-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="36b75-169">name</span><span class="sxs-lookup"><span data-stu-id="36b75-169">Name</span></span></li><li><span data-ttu-id="36b75-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="36b75-170">ClassName</span></span></li><li><span data-ttu-id="36b75-171">Приоритет</span><span class="sxs-lookup"><span data-stu-id="36b75-171">Priority</span></span></li><li><span data-ttu-id="36b75-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="36b75-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="36b75-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="36b75-173">Xunit</span></span>          | <ul><li><span data-ttu-id="36b75-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="36b75-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="36b75-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="36b75-175">DisplayName</span></span></li><li><span data-ttu-id="36b75-176">Признаки</span><span class="sxs-lookup"><span data-stu-id="36b75-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="36b75-177">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="36b75-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="36b75-178">Оператор</span><span class="sxs-lookup"><span data-stu-id="36b75-178">Operator</span></span> | <span data-ttu-id="36b75-179">Функция</span><span class="sxs-lookup"><span data-stu-id="36b75-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="36b75-180">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="36b75-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="36b75-181">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="36b75-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="36b75-182">Содержит</span><span class="sxs-lookup"><span data-stu-id="36b75-182">Contains</span></span>        |

<span data-ttu-id="36b75-183">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="36b75-183">`<value>` is a string.</span></span> <span data-ttu-id="36b75-184">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="36b75-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="36b75-185">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="36b75-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="36b75-186">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="36b75-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="36b75-187">Оператор</span><span class="sxs-lookup"><span data-stu-id="36b75-187">Operator</span></span> | <span data-ttu-id="36b75-188">Функция</span><span class="sxs-lookup"><span data-stu-id="36b75-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="36b75-189">OR</span><span class="sxs-lookup"><span data-stu-id="36b75-189">OR</span></span>       |
| `&`      | <span data-ttu-id="36b75-190">AND</span><span class="sxs-lookup"><span data-stu-id="36b75-190">AND</span></span>      |

<span data-ttu-id="36b75-191">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="36b75-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="36b75-192">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="36b75-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36b75-193">См. также</span><span class="sxs-lookup"><span data-stu-id="36b75-193">See also</span></span>

 [<span data-ttu-id="36b75-194">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="36b75-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="36b75-195">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="36b75-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
