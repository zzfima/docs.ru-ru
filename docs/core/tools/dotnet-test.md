---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 02/27/2020
ms.openlocfilehash: a11814f9fdc6326e681a09d7d2654b968014f318
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507312"
---
# <a name="dotnet-test"></a><span data-ttu-id="157f1-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="157f1-103">dotnet test</span></span>

<span data-ttu-id="157f1-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="157f1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="157f1-105">name</span><span class="sxs-lookup"><span data-stu-id="157f1-105">Name</span></span>

<span data-ttu-id="157f1-106">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="157f1-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="157f1-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="157f1-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path] [--blame] [-c|--configuration]
    [--collect] [-d|--diag] [-f|--framework] [--filter]
    [--interactive] [-l|--logger] [--no-build] [--nologo]
    [--no-restore] [-o|--output] [-r|--results-directory]
    [--runtime] [-s|--settings] [-t|--list-tests]
    [-v|--verbosity] [[--] <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="157f1-108">Описание</span><span class="sxs-lookup"><span data-stu-id="157f1-108">Description</span></span>

<span data-ttu-id="157f1-109">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="157f1-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="157f1-110">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="157f1-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="157f1-111">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="157f1-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="157f1-112">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="157f1-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="157f1-113">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="157f1-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="157f1-114">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="157f1-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="157f1-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="157f1-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="157f1-116">Путь к тестовому проекту или решению.</span><span class="sxs-lookup"><span data-stu-id="157f1-116">Path to the test project or solution.</span></span> <span data-ttu-id="157f1-117">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="157f1-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="157f1-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="157f1-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="157f1-119">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="157f1-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="157f1-120">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="157f1-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="157f1-121">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="157f1-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="157f1-122">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="157f1-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="157f1-123">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="157f1-123">Defines the build configuration.</span></span> <span data-ttu-id="157f1-124">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="157f1-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="157f1-125">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="157f1-125">Enables data collector for the test run.</span></span> <span data-ttu-id="157f1-126">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="157f1-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="157f1-127">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="157f1-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="157f1-128">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="157f1-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="157f1-129">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="157f1-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="157f1-130">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="157f1-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="157f1-131">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="157f1-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="157f1-132">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="157f1-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="157f1-133">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="157f1-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="157f1-134">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="157f1-134">For example, to complete authentication.</span></span> <span data-ttu-id="157f1-135">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="157f1-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="157f1-136">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="157f1-136">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="157f1-137">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="157f1-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="157f1-138">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="157f1-138">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="157f1-139">Запуск тестов без отображения баннера TestPlatform Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="157f1-139">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="157f1-140">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="157f1-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="157f1-141">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="157f1-141">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="157f1-142">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="157f1-142">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="157f1-143">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="157f1-143">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="157f1-144">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="157f1-144">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="157f1-145">Целевая среда выполнения для тестирования.</span><span class="sxs-lookup"><span data-stu-id="157f1-145">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="157f1-146">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="157f1-146">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="157f1-147">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="157f1-147">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="157f1-148">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="157f1-148">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="157f1-149">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="157f1-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="157f1-150">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="157f1-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="157f1-151">Аргументы `RunSettings`</span><span class="sxs-lookup"><span data-stu-id="157f1-151">`RunSettings` arguments</span></span>

  <span data-ttu-id="157f1-152">Аргументы передаются в качестве конфигураций `RunSettings` для теста.</span><span class="sxs-lookup"><span data-stu-id="157f1-152">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="157f1-153">Аргументы задаются в виде пар `[name]=[value]` после "-- " (обратите внимание на пробел после --).</span><span class="sxs-lookup"><span data-stu-id="157f1-153">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="157f1-154">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="157f1-154">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="157f1-155">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="157f1-155">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="157f1-156">Дополнительные сведения см. в разделе [vstest.console.exe: аргументов RunSettings в командной строке](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="157f1-156">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="157f1-157">Примеры</span><span class="sxs-lookup"><span data-stu-id="157f1-157">Examples</span></span>

- <span data-ttu-id="157f1-158">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="157f1-158">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="157f1-159">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="157f1-159">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="157f1-160">Выполнение тестов в проекте в текущем каталоге и создание файл результатов теста в формате trx:</span><span class="sxs-lookup"><span data-stu-id="157f1-160">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="157f1-161">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="157f1-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="157f1-162">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="157f1-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="157f1-163">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="157f1-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="157f1-164">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="157f1-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="157f1-165">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="157f1-165">Test Framework</span></span> | <span data-ttu-id="157f1-166">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="157f1-166">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="157f1-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="157f1-167">MSTest</span></span>         | <ul><li><span data-ttu-id="157f1-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="157f1-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="157f1-169">name</span><span class="sxs-lookup"><span data-stu-id="157f1-169">Name</span></span></li><li><span data-ttu-id="157f1-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="157f1-170">ClassName</span></span></li><li><span data-ttu-id="157f1-171">Priority</span><span class="sxs-lookup"><span data-stu-id="157f1-171">Priority</span></span></li><li><span data-ttu-id="157f1-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="157f1-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="157f1-173">xUnit</span><span class="sxs-lookup"><span data-stu-id="157f1-173">xUnit</span></span>          | <ul><li><span data-ttu-id="157f1-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="157f1-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="157f1-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="157f1-175">DisplayName</span></span></li><li><span data-ttu-id="157f1-176">Признаки</span><span class="sxs-lookup"><span data-stu-id="157f1-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="157f1-177">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="157f1-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="157f1-178">Оператор</span><span class="sxs-lookup"><span data-stu-id="157f1-178">Operator</span></span> | <span data-ttu-id="157f1-179">Функция</span><span class="sxs-lookup"><span data-stu-id="157f1-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="157f1-180">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="157f1-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="157f1-181">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="157f1-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="157f1-182">Содержит</span><span class="sxs-lookup"><span data-stu-id="157f1-182">Contains</span></span>        |
| `!~`     | <span data-ttu-id="157f1-183">Не содержит</span><span class="sxs-lookup"><span data-stu-id="157f1-183">Not contains</span></span>    |

<span data-ttu-id="157f1-184">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="157f1-184">`<value>` is a string.</span></span> <span data-ttu-id="157f1-185">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="157f1-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="157f1-186">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="157f1-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="157f1-187">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="157f1-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="157f1-188">Оператор</span><span class="sxs-lookup"><span data-stu-id="157f1-188">Operator</span></span>            | <span data-ttu-id="157f1-189">Функция</span><span class="sxs-lookup"><span data-stu-id="157f1-189">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="157f1-190">OR</span><span class="sxs-lookup"><span data-stu-id="157f1-190">OR</span></span>       |
| `&`                 | <span data-ttu-id="157f1-191">AND</span><span class="sxs-lookup"><span data-stu-id="157f1-191">AND</span></span>      |

<span data-ttu-id="157f1-192">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="157f1-192">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="157f1-193">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="157f1-193">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="157f1-194">См. также</span><span class="sxs-lookup"><span data-stu-id="157f1-194">See also</span></span>

- [<span data-ttu-id="157f1-195">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="157f1-195">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="157f1-196">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="157f1-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
