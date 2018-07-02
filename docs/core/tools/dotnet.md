---
title: Команда dotnet — CLI .NET Core
description: Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805663"
---
# <a name="dotnet-command"></a><span data-ttu-id="c623e-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="c623e-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c623e-104">name</span><span class="sxs-lookup"><span data-stu-id="c623e-104">Name</span></span>

<span data-ttu-id="c623e-105">`dotnet` — универсальный драйвер для выполнения команд командной строки.</span><span class="sxs-lookup"><span data-stu-id="c623e-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c623e-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c623e-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c623e-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c623e-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c623e-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c623e-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c623e-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c623e-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="c623e-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="c623e-110">Description</span></span>

<span data-ttu-id="c623e-111">`dotnet` — это универсальный драйвер для цепочки инструментов интерфейса командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="c623e-111">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="c623e-112">Если вызвать его без указания команды, выводятся краткие инструкции по использованию.</span><span class="sxs-lookup"><span data-stu-id="c623e-112">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="c623e-113">Каждая отдельная функция реализуется в виде команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-113">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="c623e-114">Чтобы использовать эту функцию, введите команду после `dotnet`, вот так: [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="c623e-114">To use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="c623e-115">Все аргументы после команды относятся именно к ней.</span><span class="sxs-lookup"><span data-stu-id="c623e-115">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="c623e-116">Единственный случай, когда `dotnet` используется в качестве команды самостоятельно, — это запуск [платформозависимых приложений](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c623e-116">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="c623e-117">Просто укажите библиотеку DLL приложения после команды `dotnet`, чтобы выполнить приложение (Например, `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="c623e-117">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="c623e-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="c623e-118">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c623e-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c623e-119">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="c623e-120">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="c623e-120">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c623e-121">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="c623e-121">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c623e-122">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="c623e-122">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c623e-123">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c623e-123">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c623e-124">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c623e-124">Prints out a short help for the command.</span></span> <span data-ttu-id="c623e-125">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="c623e-125">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c623e-126">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="c623e-126">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--list-runtimes`

<span data-ttu-id="c623e-127">Отображает установленные среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-127">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="c623e-128">Отображает установленные пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-128">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c623e-129">Выполняет накат при отсутствии подходящей общей платформы.</span><span class="sxs-lookup"><span data-stu-id="c623e-129">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c623e-130">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c623e-131">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c623e-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c623e-132">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c623e-133">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c623e-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c623e-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="c623e-135">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="c623e-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c623e-136">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="c623e-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c623e-137">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="c623e-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c623e-138">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c623e-138">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c623e-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c623e-139">Prints out a short help for the command.</span></span> <span data-ttu-id="c623e-140">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="c623e-140">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c623e-141">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="c623e-141">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c623e-142">Выполняет накат при отсутствии подходящей общей платформы.</span><span class="sxs-lookup"><span data-stu-id="c623e-142">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c623e-143">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c623e-144">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c623e-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c623e-145">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-145">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c623e-146">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-146">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c623e-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c623e-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="c623e-148">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="c623e-148">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c623e-149">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="c623e-149">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c623e-150">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c623e-150">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c623e-151">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c623e-151">Prints out a short help for the command.</span></span> <span data-ttu-id="c623e-152">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="c623e-152">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c623e-153">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="c623e-153">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c623e-154">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c623e-155">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c623e-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c623e-156">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-156">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c623e-157">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-157">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="c623e-158">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="c623e-158">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c623e-159">Общие</span><span class="sxs-lookup"><span data-stu-id="c623e-159">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c623e-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c623e-160">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="c623e-161">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-161">Command</span></span>                                       | <span data-ttu-id="c623e-162">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-162">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c623e-163">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c623e-163">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="c623e-164">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-164">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c623e-165">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="c623e-165">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="c623e-166">Взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="c623e-166">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="c623e-167">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c623e-167">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="c623e-168">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="c623e-168">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="c623e-169">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c623e-169">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="c623e-170">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-170">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c623e-171">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c623e-171">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="c623e-172">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="c623e-172">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c623e-173">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c623e-173">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="c623e-174">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c623e-174">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c623e-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c623e-175">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="c623e-176">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="c623e-176">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c623e-177">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c623e-177">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="c623e-178">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="c623e-178">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c623e-179">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c623e-179">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="c623e-180">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="c623e-180">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c623e-181">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c623e-181">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="c623e-182">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="c623e-182">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c623e-183">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c623e-183">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="c623e-184">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="c623e-184">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c623e-185">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c623e-185">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="c623e-186">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="c623e-186">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c623e-187">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c623e-187">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="c623e-188">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c623e-188">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c623e-189">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c623e-189">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="c623e-190">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="c623e-190">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c623e-191">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c623e-191">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="c623e-192">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-192">Command</span></span>                             | <span data-ttu-id="c623e-193">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-193">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c623e-194">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c623e-194">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c623e-195">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-195">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c623e-196">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c623e-196">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c623e-197">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="c623e-197">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c623e-198">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c623e-198">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="c623e-199">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="c623e-199">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c623e-200">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c623e-200">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c623e-201">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="c623e-201">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c623e-202">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c623e-202">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c623e-203">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c623e-203">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c623e-204">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c623e-204">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c623e-205">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="c623e-205">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c623e-206">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c623e-206">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c623e-207">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="c623e-207">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c623e-208">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c623e-208">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c623e-209">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="c623e-209">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c623e-210">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c623e-210">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c623e-211">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="c623e-211">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c623e-212">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c623e-212">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c623e-213">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="c623e-213">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c623e-214">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c623e-214">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c623e-215">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="c623e-215">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c623e-216">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c623e-216">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="c623e-217">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c623e-217">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c623e-218">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c623e-218">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c623e-219">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="c623e-219">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c623e-220">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c623e-220">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="c623e-221">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-221">Command</span></span>                             | <span data-ttu-id="c623e-222">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-222">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c623e-223">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c623e-223">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c623e-224">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-224">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c623e-225">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c623e-225">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c623e-226">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="c623e-226">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c623e-227">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c623e-227">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c623e-228">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="c623e-228">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c623e-229">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c623e-229">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c623e-230">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c623e-230">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c623e-231">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c623e-231">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c623e-232">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="c623e-232">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c623e-233">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c623e-233">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c623e-234">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="c623e-234">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c623e-235">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c623e-235">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c623e-236">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="c623e-236">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c623e-237">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c623e-237">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c623e-238">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="c623e-238">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c623e-239">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c623e-239">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c623e-240">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="c623e-240">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c623e-241">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c623e-241">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c623e-242">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="c623e-242">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c623e-243">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c623e-243">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c623e-244">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="c623e-244">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="c623e-245">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="c623e-245">Project references</span></span>

<span data-ttu-id="c623e-246">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-246">Command</span></span> | <span data-ttu-id="c623e-247">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-247">Function</span></span>
--- | ---
[<span data-ttu-id="c623e-248">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c623e-248">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c623e-249">Добавляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="c623e-249">Adds a project reference.</span></span>
[<span data-ttu-id="c623e-250">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c623e-250">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c623e-251">Перечисляет ссылки на проекты.</span><span class="sxs-lookup"><span data-stu-id="c623e-251">Lists project references.</span></span>
[<span data-ttu-id="c623e-252">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c623e-252">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c623e-253">Удаляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="c623e-253">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c623e-254">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="c623e-254">NuGet packages</span></span>

<span data-ttu-id="c623e-255">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-255">Command</span></span> | <span data-ttu-id="c623e-256">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-256">Function</span></span>
--- | ---
[<span data-ttu-id="c623e-257">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c623e-257">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c623e-258">Добавляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="c623e-258">Adds a NuGet package.</span></span>
[<span data-ttu-id="c623e-259">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c623e-259">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c623e-260">Удаляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="c623e-260">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c623e-261">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="c623e-261">NuGet commands</span></span>

<span data-ttu-id="c623e-262">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-262">Command</span></span> | <span data-ttu-id="c623e-263">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-263">Function</span></span>
--- | ---
[<span data-ttu-id="c623e-264">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c623e-264">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c623e-265">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="c623e-265">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c623e-266">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c623e-266">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c623e-267">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="c623e-267">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c623e-268">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c623e-268">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c623e-269">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="c623e-269">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="c623e-270">Команды глобальных средств</span><span class="sxs-lookup"><span data-stu-id="c623e-270">Global Tools commands</span></span>

<span data-ttu-id="c623e-271">[Глобальные средства .NET Core](global-tools.md) появились в пакете SDK для .NET Core, начиная с версии 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="c623e-271">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="c623e-272">Команда</span><span class="sxs-lookup"><span data-stu-id="c623e-272">Command</span></span> | <span data-ttu-id="c623e-273">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-273">Function</span></span>
--- | ---
[<span data-ttu-id="c623e-274">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="c623e-274">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="c623e-275">Устанавливает глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c623e-275">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="c623e-276">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="c623e-276">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="c623e-277">Перечисляет выводит все глобальные средства, установленные на компьютере в каталоге по умолчанию или по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="c623e-277">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="c623e-278">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="c623e-278">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="c623e-279">Удаляет глобальное средство с компьютера.</span><span class="sxs-lookup"><span data-stu-id="c623e-279">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="c623e-280">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="c623e-280">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="c623e-281">Обновляет глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c623e-281">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="c623e-282">Дополнительные инструменты</span><span class="sxs-lookup"><span data-stu-id="c623e-282">Additional tools</span></span>

<span data-ttu-id="c623e-283">Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="c623e-283">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="c623e-284">К ним относятся следующие средства:</span><span class="sxs-lookup"><span data-stu-id="c623e-284">These tools include:</span></span>

| <span data-ttu-id="c623e-285">Средство</span><span class="sxs-lookup"><span data-stu-id="c623e-285">Tool</span></span>                                              | <span data-ttu-id="c623e-286">Функция</span><span class="sxs-lookup"><span data-stu-id="c623e-286">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="c623e-287">dev-certs</span><span class="sxs-lookup"><span data-stu-id="c623e-287">dev-certs</span></span>                                         | <span data-ttu-id="c623e-288">Создает сертификаты разработки и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="c623e-288">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="c623e-289">ef</span><span class="sxs-lookup"><span data-stu-id="c623e-289">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="c623e-290">Средства командной строки для Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="c623e-290">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="c623e-291">sql-cache</span><span class="sxs-lookup"><span data-stu-id="c623e-291">sql-cache</span></span>                                         | <span data-ttu-id="c623e-292">Средства командной строки для кэша SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c623e-292">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="c623e-293">user-secrets</span><span class="sxs-lookup"><span data-stu-id="c623e-293">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="c623e-294">Управляет секретами пользователей для разработки.</span><span class="sxs-lookup"><span data-stu-id="c623e-294">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="c623e-295">watch</span><span class="sxs-lookup"><span data-stu-id="c623e-295">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="c623e-296">Запускает наблюдатель за файлами, который выполняет команду при изменении файлов.</span><span class="sxs-lookup"><span data-stu-id="c623e-296">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="c623e-297">Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="c623e-297">For more information about each tool, execute `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="c623e-298">Примеры</span><span class="sxs-lookup"><span data-stu-id="c623e-298">Examples</span></span>

<span data-ttu-id="c623e-299">Создание проекта консольного приложения .NET Core:</span><span class="sxs-lookup"><span data-stu-id="c623e-299">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="c623e-300">Восстановление зависимостей для данного приложения:</span><span class="sxs-lookup"><span data-stu-id="c623e-300">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c623e-301">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="c623e-301">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="c623e-302">Запуск платформозависимого приложения `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="c623e-302">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="c623e-303">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="c623e-303">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c623e-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c623e-304">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="c623e-305">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="c623e-305">The primary package cache.</span></span> <span data-ttu-id="c623e-306">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="c623e-306">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c623e-307">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c623e-307">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c623e-308">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c623e-308">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c623e-309">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="c623e-309">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c623e-310">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="c623e-310">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c623e-311">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="c623e-311">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="c623e-312">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="c623e-312">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c623e-313">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="c623e-313">If not set, it defaults to `true`.</span></span> <span data-ttu-id="c623e-314">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="c623e-314">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="c623e-315">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="c623e-315">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="c623e-316">Отключает накат дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="c623e-316">Disables minor version roll forward.</span></span> <span data-ttu-id="c623e-317">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="c623e-317">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c623e-318">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c623e-318">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="c623e-319">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="c623e-319">The primary package cache.</span></span> <span data-ttu-id="c623e-320">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="c623e-320">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c623e-321">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c623e-321">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c623e-322">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c623e-322">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c623e-323">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="c623e-323">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c623e-324">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="c623e-324">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c623e-325">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="c623e-325">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="c623e-326">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="c623e-326">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c623e-327">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="c623e-327">If not set, it defaults to `true`.</span></span> <span data-ttu-id="c623e-328">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="c623e-328">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="c623e-329">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="c623e-329">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c623e-330">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c623e-330">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="c623e-331">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="c623e-331">The primary package cache.</span></span> <span data-ttu-id="c623e-332">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="c623e-332">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c623e-333">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c623e-333">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c623e-334">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c623e-334">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c623e-335">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="c623e-335">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c623e-336">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="c623e-336">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c623e-337">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="c623e-337">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
