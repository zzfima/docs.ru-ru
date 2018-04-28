---
title: Команда dotnet vstest — CLI .NET Core
description: Команда dotnet vstest выполняет сборку проекта и всех его зависимостей.
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: e11b193ff7a8c639078c5cf279b7fbbeab553c92
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-vstest"></a><span data-ttu-id="d914f-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="d914f-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d914f-104">name</span><span class="sxs-lookup"><span data-stu-id="d914f-104">Name</span></span>

<span data-ttu-id="d914f-105">`dotnet-vstest` — запускает тесты из указанных файлов.</span><span class="sxs-lookup"><span data-stu-id="d914f-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d914f-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d914f-106">Synopsis</span></span>

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a><span data-ttu-id="d914f-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d914f-107">Description</span></span>

<span data-ttu-id="d914f-108">Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования и закодированных тестов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d914f-108">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit and coded UI application tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="d914f-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d914f-109">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="d914f-110">Запустите тесты из указанных сборок.</span><span class="sxs-lookup"><span data-stu-id="d914f-110">Run tests from the specified assemblies.</span></span> <span data-ttu-id="d914f-111">Для разделения имен тестовых сборок используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="d914f-111">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="d914f-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="d914f-112">Options</span></span>

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="d914f-113">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="d914f-113">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="d914f-114">Выполните тесты с именами, которые соответствуют предусмотренным значениям.</span><span class="sxs-lookup"><span data-stu-id="d914f-114">Run tests with names that match the provided values.</span></span> <span data-ttu-id="d914f-115">Для разделения значений используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="d914f-115">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="d914f-116">Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="d914f-116">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="d914f-117">Архитектура целевой платформы, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="d914f-117">Target platform architecture used for test execution.</span></span> <span data-ttu-id="d914f-118">Допустимые значения: `x86`, `x64` и `ARM`.</span><span class="sxs-lookup"><span data-stu-id="d914f-118">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="d914f-119">Целевая версия платформы .NET Framework, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="d914f-119">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="d914f-120">Примеры допустимых значений: `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` и т. п. Другие поддерживаемые значения: `Framework35`, `Framework40`, `Framework45` и `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="d914f-120">Examples of valid values are `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Other supported values are `Framework35`, `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="d914f-121">Выполняйте тесты в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="d914f-121">Execute tests in parallel.</span></span> <span data-ttu-id="d914f-122">По умолчанию для использования все доступные на компьютере ядра.</span><span class="sxs-lookup"><span data-stu-id="d914f-122">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="d914f-123">Задайте явное число ядер с помощью файла параметров.</span><span class="sxs-lookup"><span data-stu-id="d914f-123">Set an explicit number of cores with a settings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="d914f-124">Запуск тестов, соответствующих заданному выражению.</span><span class="sxs-lookup"><span data-stu-id="d914f-124">Run tests that match the given expression.</span></span> <span data-ttu-id="d914f-125">`<Expression>` имеет формат `<property>Operator<value>[|&<Expression>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.</span><span class="sxs-lookup"><span data-stu-id="d914f-125">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span>  <span data-ttu-id="d914f-126">Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="d914f-126">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="d914f-127">Скобки `()` используются для группировки частей выражений.</span><span class="sxs-lookup"><span data-stu-id="d914f-127">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="d914f-128">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d914f-128">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="d914f-129">Укажите средство ведения журнала результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="d914f-129">Specify a logger for test results.</span></span>  

* <span data-ttu-id="d914f-130">Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="d914f-130">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="d914f-131">Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`.</span><span class="sxs-lookup"><span data-stu-id="d914f-131">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="d914f-132">Этот параметр создает файл журнала с заданным именем в каталоге результатов теста.</span><span class="sxs-lookup"><span data-stu-id="d914f-132">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="d914f-133">Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="d914f-133">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="d914f-134">Перечисление обнаруженных тестов из указанного контейнера тестов.</span><span class="sxs-lookup"><span data-stu-id="d914f-134">Lists discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="d914f-135">Идентификатор родительского процесса, отвечающего за запуск текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="d914f-135">Process Id of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="d914f-136">Указывает порт для подключения сокета и получения сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="d914f-136">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="d914f-137">Включает ведение подробных журналов для платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="d914f-137">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="d914f-138">Журналы записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="d914f-138">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="d914f-139">Задает дополнительные аргументы, передаваемые адаптеру.</span><span class="sxs-lookup"><span data-stu-id="d914f-139">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="d914f-140">Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента.</span><span class="sxs-lookup"><span data-stu-id="d914f-140">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="d914f-141">Для разделения аргументов используйте пробел.</span><span class="sxs-lookup"><span data-stu-id="d914f-141">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="d914f-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="d914f-142">Examples</span></span>

<span data-ttu-id="d914f-143">Запуск тестов в `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="d914f-143">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="d914f-144">Запуск тестов в `mytestproject.dll` с экспортом в настраиваемую папку с пользовательским именем:</span><span class="sxs-lookup"><span data-stu-id="d914f-144">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="d914f-145">Запуск тестов в `mytestproject.dll` и `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="d914f-145">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="d914f-146">Запуск тестов `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="d914f-146">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="d914f-147">Запуск тестов `TestMethod1` и `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="d914f-147">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`

