---
title: "Команда dotnet test — CLI .NET Core"
description: "Команда dotnet test служит для выполнения модульных тестов в проекте."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 55329bed71be21a787d6e77d8c0ea67d607676b8
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-test"></a><span data-ttu-id="d1acc-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="d1acc-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d1acc-104">Имя</span><span class="sxs-lookup"><span data-stu-id="d1acc-104">Name</span></span>

<span data-ttu-id="d1acc-105">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="d1acc-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d1acc-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d1acc-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d1acc-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d1acc-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d1acc-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d1acc-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d1acc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d1acc-109">Description</span></span>

<span data-ttu-id="d1acc-110">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="d1acc-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="d1acc-111">Модульные тесты — это проекты консольных приложений, у которых есть зависимости от среды модульного тестирования (например, MSTest, NUnit или xUnit) и от средства запуска тестов dotnet для этой среды.</span><span class="sxs-lookup"><span data-stu-id="d1acc-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="d1acc-112">Они упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="d1acc-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="d1acc-113">Для тестовых проектов также нужно указать средство выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="d1acc-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="d1acc-114">Для этого используется обычный элемент `<PackageReference>`, как показано в следующем образце файла проекта:</span><span class="sxs-lookup"><span data-stu-id="d1acc-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

<span data-ttu-id="d1acc-115">[!code-xml[Базовый шаблон XUnit](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span><span class="sxs-lookup"><span data-stu-id="d1acc-115">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span></span>

## <a name="arguments"></a><span data-ttu-id="d1acc-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d1acc-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d1acc-117">Указывает путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="d1acc-117">Specifies a path to the test project.</span></span> <span data-ttu-id="d1acc-118">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d1acc-118">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="d1acc-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1acc-119">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d1acc-120">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d1acc-120">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d1acc-121">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="d1acc-121">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d1acc-122">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="d1acc-122">Defines the build configuration.</span></span> <span data-ttu-id="d1acc-123">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1acc-123">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="d1acc-124">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="d1acc-124">Enables data collector for the test run.</span></span> <span data-ttu-id="d1acc-125">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="d1acc-125">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d1acc-126">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="d1acc-126">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d1acc-127">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d1acc-127">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d1acc-128">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="d1acc-128">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d1acc-129">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d1acc-129">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d1acc-130">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d1acc-130">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d1acc-131">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d1acc-131">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d1acc-132">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="d1acc-132">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d1acc-133">Не выполняет сборку тестового проекта перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="d1acc-133">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="d1acc-134">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="d1acc-134">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d1acc-135">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="d1acc-135">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="d1acc-136">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="d1acc-136">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="d1acc-137">Если указанный каталог не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="d1acc-137">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d1acc-138">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="d1acc-138">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d1acc-139">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="d1acc-139">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d1acc-140">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d1acc-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d1acc-141">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d1acc-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d1acc-142">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d1acc-142">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d1acc-143">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="d1acc-143">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d1acc-144">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="d1acc-144">Defines the build configuration.</span></span> <span data-ttu-id="d1acc-145">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1acc-145">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d1acc-146">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="d1acc-146">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d1acc-147">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d1acc-147">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d1acc-148">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="d1acc-148">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d1acc-149">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d1acc-149">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d1acc-150">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d1acc-150">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d1acc-151">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d1acc-151">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d1acc-152">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="d1acc-152">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d1acc-153">Не выполняет сборку тестового проекта перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="d1acc-153">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d1acc-154">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="d1acc-154">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d1acc-155">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="d1acc-155">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d1acc-156">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="d1acc-156">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d1acc-157">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d1acc-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d1acc-158">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d1acc-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d1acc-159">Примеры</span><span class="sxs-lookup"><span data-stu-id="d1acc-159">Examples</span></span>

<span data-ttu-id="d1acc-160">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d1acc-160">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="d1acc-161">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="d1acc-161">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="d1acc-162">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="d1acc-162">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d1acc-163">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="d1acc-163">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="d1acc-164">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="d1acc-164">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="d1acc-165">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="d1acc-165">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="d1acc-166">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="d1acc-166">Test Framework</span></span> | <span data-ttu-id="d1acc-167">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="d1acc-167">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d1acc-168">MSTest</span><span class="sxs-lookup"><span data-stu-id="d1acc-168">MSTest</span></span>         | <ul><li><span data-ttu-id="d1acc-169">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d1acc-169">FullyQualifiedName</span></span></li><li><span data-ttu-id="d1acc-170">Имя</span><span class="sxs-lookup"><span data-stu-id="d1acc-170">Name</span></span></li><li><span data-ttu-id="d1acc-171">ClassName</span><span class="sxs-lookup"><span data-stu-id="d1acc-171">ClassName</span></span></li><li><span data-ttu-id="d1acc-172">Приоритет</span><span class="sxs-lookup"><span data-stu-id="d1acc-172">Priority</span></span></li><li><span data-ttu-id="d1acc-173">TestCategory</span><span class="sxs-lookup"><span data-stu-id="d1acc-173">TestCategory</span></span></li></ul> |
| <span data-ttu-id="d1acc-174">Xunit</span><span class="sxs-lookup"><span data-stu-id="d1acc-174">Xunit</span></span>          | <ul><li><span data-ttu-id="d1acc-175">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d1acc-175">FullyQualifiedName</span></span></li><li><span data-ttu-id="d1acc-176">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d1acc-176">DisplayName</span></span></li><li><span data-ttu-id="d1acc-177">Признаки</span><span class="sxs-lookup"><span data-stu-id="d1acc-177">Traits</span></span></li></ul>                                   |

<span data-ttu-id="d1acc-178">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="d1acc-178">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="d1acc-179">Оператор</span><span class="sxs-lookup"><span data-stu-id="d1acc-179">Operator</span></span> | <span data-ttu-id="d1acc-180">Функция</span><span class="sxs-lookup"><span data-stu-id="d1acc-180">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="d1acc-181">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="d1acc-181">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="d1acc-182">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="d1acc-182">Not exact match</span></span> |
| `~`      | <span data-ttu-id="d1acc-183">Содержит</span><span class="sxs-lookup"><span data-stu-id="d1acc-183">Contains</span></span>        |

<span data-ttu-id="d1acc-184">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="d1acc-184">`<value>` is a string.</span></span> <span data-ttu-id="d1acc-185">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="d1acc-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="d1acc-186">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="d1acc-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="d1acc-187">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="d1acc-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="d1acc-188">Оператор</span><span class="sxs-lookup"><span data-stu-id="d1acc-188">Operator</span></span> | <span data-ttu-id="d1acc-189">Функция</span><span class="sxs-lookup"><span data-stu-id="d1acc-189">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="d1acc-190">OR</span><span class="sxs-lookup"><span data-stu-id="d1acc-190">OR</span></span>       |
| `&`      | <span data-ttu-id="d1acc-191">AND</span><span class="sxs-lookup"><span data-stu-id="d1acc-191">AND</span></span>      |

<span data-ttu-id="d1acc-192">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="d1acc-192">You can enclose expressions in paranthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="d1acc-193">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье о [выполнении выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d1acc-193">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1acc-194">См. также</span><span class="sxs-lookup"><span data-stu-id="d1acc-194">See also</span></span>

 <span data-ttu-id="d1acc-195">[Платформы и целевые объекты](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="d1acc-195">[Frameworks and Targets](../../standard/frameworks.md) </span></span>  
 [<span data-ttu-id="d1acc-196">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1acc-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

