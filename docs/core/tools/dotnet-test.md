---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 02/27/2020
ms.openlocfilehash: 6e906ab396a788905c99f50e73390b765b240efc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157015"
---
# <a name="dotnet-test"></a><span data-ttu-id="4d7f3-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4d7f3-103">dotnet test</span></span>

<span data-ttu-id="4d7f3-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="4d7f3-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4d7f3-105">name</span><span class="sxs-lookup"><span data-stu-id="4d7f3-105">Name</span></span>

<span data-ttu-id="4d7f3-106">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4d7f3-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4d7f3-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame]
    [-c|--configuration] [--collect] [-d|--diag] [-f|--framework]
    [--filter] [-l|--logger] [--no-build] [--no-restore]
    [-o|--output] [-r|--results-directory] [-s|--settings]
    [-t|--list-tests] [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="4d7f3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4d7f3-108">Description</span></span>

<span data-ttu-id="4d7f3-109">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="4d7f3-110">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="4d7f3-111">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="4d7f3-112">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="4d7f3-113">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="4d7f3-114">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="4d7f3-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="4d7f3-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4d7f3-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="4d7f3-116">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-116">Path to the test project.</span></span> <span data-ttu-id="4d7f3-117">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="4d7f3-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d7f3-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="4d7f3-119">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`-blame`**

  <span data-ttu-id="4d7f3-120">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="4d7f3-121">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="4d7f3-122">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration {Debug|Release}`**

  <span data-ttu-id="4d7f3-123">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-123">Defines the build configuration.</span></span> <span data-ttu-id="4d7f3-124">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="4d7f3-125">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-125">Enables data collector for the test run.</span></span> <span data-ttu-id="4d7f3-126">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="4d7f3-127">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="4d7f3-128">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="4d7f3-129">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="4d7f3-130">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="4d7f3-131">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="4d7f3-132">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-132">Prints out a short help for the command.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="4d7f3-133">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-133">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="4d7f3-134">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-134">Doesn't build the test project before running it.</span></span> <span data-ttu-id="4d7f3-135">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-135">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--no-restore`**

  <span data-ttu-id="4d7f3-136">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-136">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="4d7f3-137">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-137">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="4d7f3-138">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-138">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="4d7f3-139">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-139">If the specified directory doesn't exist, it's created.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="4d7f3-140">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-140">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="4d7f3-141">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-141">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="4d7f3-142">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-142">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="4d7f3-143">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4d7f3-144">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="4d7f3-145">Аргументы `RunSettings`</span><span class="sxs-lookup"><span data-stu-id="4d7f3-145">`RunSettings` arguments</span></span>

  <span data-ttu-id="4d7f3-146">Аргументы передаются в качестве конфигураций `RunSettings` для теста.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-146">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="4d7f3-147">Аргументы задаются в виде пар `[name]=[value]` после "-- " (обратите внимание на пробел после --).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-147">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="4d7f3-148">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-148">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="4d7f3-149">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="4d7f3-149">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="4d7f3-150">Дополнительные сведения см. в разделе [vstest.console.exe: аргументов RunSettings в командной строке](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-150">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="4d7f3-151">Примеры</span><span class="sxs-lookup"><span data-stu-id="4d7f3-151">Examples</span></span>

- <span data-ttu-id="4d7f3-152">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="4d7f3-152">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="4d7f3-153">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="4d7f3-153">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="4d7f3-154">Выполнение тестов в проекте в текущем каталоге и создание файл результатов теста в формате trx:</span><span class="sxs-lookup"><span data-stu-id="4d7f3-154">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="4d7f3-155">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="4d7f3-155">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="4d7f3-156">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-156">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="4d7f3-157">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-157">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="4d7f3-158">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-158">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="4d7f3-159">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="4d7f3-159">Test Framework</span></span> | <span data-ttu-id="4d7f3-160">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="4d7f3-160">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="4d7f3-161">MSTest</span><span class="sxs-lookup"><span data-stu-id="4d7f3-161">MSTest</span></span>         | <ul><li><span data-ttu-id="4d7f3-162">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="4d7f3-162">FullyQualifiedName</span></span></li><li><span data-ttu-id="4d7f3-163">name</span><span class="sxs-lookup"><span data-stu-id="4d7f3-163">Name</span></span></li><li><span data-ttu-id="4d7f3-164">ClassName</span><span class="sxs-lookup"><span data-stu-id="4d7f3-164">ClassName</span></span></li><li><span data-ttu-id="4d7f3-165">Priority</span><span class="sxs-lookup"><span data-stu-id="4d7f3-165">Priority</span></span></li><li><span data-ttu-id="4d7f3-166">TestCategory</span><span class="sxs-lookup"><span data-stu-id="4d7f3-166">TestCategory</span></span></li></ul> |
| <span data-ttu-id="4d7f3-167">xUnit</span><span class="sxs-lookup"><span data-stu-id="4d7f3-167">xUnit</span></span>          | <ul><li><span data-ttu-id="4d7f3-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="4d7f3-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="4d7f3-169">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4d7f3-169">DisplayName</span></span></li><li><span data-ttu-id="4d7f3-170">Признаки</span><span class="sxs-lookup"><span data-stu-id="4d7f3-170">Traits</span></span></li></ul>                                   |

<span data-ttu-id="4d7f3-171">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="4d7f3-171">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="4d7f3-172">Оператор</span><span class="sxs-lookup"><span data-stu-id="4d7f3-172">Operator</span></span> | <span data-ttu-id="4d7f3-173">Функция</span><span class="sxs-lookup"><span data-stu-id="4d7f3-173">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="4d7f3-174">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="4d7f3-174">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="4d7f3-175">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="4d7f3-175">Not exact match</span></span> |
| `~`      | <span data-ttu-id="4d7f3-176">Содержит</span><span class="sxs-lookup"><span data-stu-id="4d7f3-176">Contains</span></span>        |
| `!~`     | <span data-ttu-id="4d7f3-177">Не содержит</span><span class="sxs-lookup"><span data-stu-id="4d7f3-177">Not contains</span></span>    |

<span data-ttu-id="4d7f3-178">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-178">`<value>` is a string.</span></span> <span data-ttu-id="4d7f3-179">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-179">All the lookups are case insensitive.</span></span>

<span data-ttu-id="4d7f3-180">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-180">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="4d7f3-181">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="4d7f3-181">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="4d7f3-182">Оператор</span><span class="sxs-lookup"><span data-stu-id="4d7f3-182">Operator</span></span>            | <span data-ttu-id="4d7f3-183">Функция</span><span class="sxs-lookup"><span data-stu-id="4d7f3-183">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="4d7f3-184">OR</span><span class="sxs-lookup"><span data-stu-id="4d7f3-184">OR</span></span>       |
| `&`                 | <span data-ttu-id="4d7f3-185">AND</span><span class="sxs-lookup"><span data-stu-id="4d7f3-185">AND</span></span>      |

<span data-ttu-id="4d7f3-186">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-186">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="4d7f3-187">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f3-187">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d7f3-188">См. также</span><span class="sxs-lookup"><span data-stu-id="4d7f3-188">See also</span></span>

- [<span data-ttu-id="4d7f3-189">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="4d7f3-189">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="4d7f3-190">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="4d7f3-190">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
