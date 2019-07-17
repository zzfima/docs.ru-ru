---
title: Команда dotnet
description: Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании.
ms.date: 06/04/2018
ms.openlocfilehash: 2134bf8ed66157619499b027f01d39e03e84411f
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859550"
---
# <a name="dotnet-command"></a><span data-ttu-id="470dd-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="470dd-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="470dd-104">name</span><span class="sxs-lookup"><span data-stu-id="470dd-104">Name</span></span>

<span data-ttu-id="470dd-105">`dotnet` — средство для управления исходным кодом .NET и двоичными объектами.</span><span class="sxs-lookup"><span data-stu-id="470dd-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="470dd-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="470dd-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="470dd-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="470dd-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="470dd-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="470dd-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="470dd-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="470dd-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="470dd-110">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="470dd-110">Description</span></span>

<span data-ttu-id="470dd-111">`dotnet` — это средство для управления исходным кодом .NET и двоичными объектами.</span><span class="sxs-lookup"><span data-stu-id="470dd-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="470dd-112">Он предоставляет команды, выполняющие определенные задачи, такие как [`dotnet build`](dotnet-build.md) и [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="470dd-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="470dd-113">Каждая команда определяет свои аргументы.</span><span class="sxs-lookup"><span data-stu-id="470dd-113">Each command defines its own arguments.</span></span> <span data-ttu-id="470dd-114">Введите `--help` после каждой команды для доступа к краткой справочной документации.</span><span class="sxs-lookup"><span data-stu-id="470dd-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="470dd-115">`dotnet` можно использовать для запуска приложений путем указания библиотеки DLL приложения, например `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="470dd-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="470dd-116">Дополнительные сведения о параметрах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="470dd-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="470dd-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="470dd-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="470dd-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="470dd-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="470dd-119">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="470dd-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="470dd-120">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="470dd-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="470dd-121">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="470dd-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="470dd-122">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="470dd-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="470dd-123">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="470dd-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="470dd-124">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="470dd-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="470dd-125">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="470dd-126">Отображает установленные среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="470dd-127">Отображает установленные пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="470dd-128">Определяет поведение, когда требуемая общая платформа недоступна.</span><span class="sxs-lookup"><span data-stu-id="470dd-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="470dd-129">Параметр `N` может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="470dd-129">`N` can be:</span></span>
* <span data-ttu-id="470dd-130">`0` — отключает увеличение дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="470dd-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="470dd-131">`1` — позволяет увеличивать дополнительный номер версии, но не основной.</span><span class="sxs-lookup"><span data-stu-id="470dd-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="470dd-132">Это поведение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="470dd-132">This is the default behavior.</span></span>
* <span data-ttu-id="470dd-133">`2` — включает увеличение основных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="470dd-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="470dd-134">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="470dd-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="470dd-135">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="470dd-136">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="470dd-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="470dd-137">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="470dd-138">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="470dd-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="470dd-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="470dd-140">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="470dd-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="470dd-141">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="470dd-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="470dd-142">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="470dd-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="470dd-143">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="470dd-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="470dd-144">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="470dd-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="470dd-145">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="470dd-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="470dd-146">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="470dd-147">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="470dd-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="470dd-148">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="470dd-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="470dd-149">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="470dd-150">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="470dd-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="470dd-151">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="470dd-152">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="470dd-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="470dd-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="470dd-154">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="470dd-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="470dd-155">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="470dd-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="470dd-156">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="470dd-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="470dd-157">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="470dd-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="470dd-158">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="470dd-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="470dd-159">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="470dd-160">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="470dd-161">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="470dd-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="470dd-162">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="470dd-163">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="470dd-164">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="470dd-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="470dd-165">Общие</span><span class="sxs-lookup"><span data-stu-id="470dd-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="470dd-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="470dd-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="470dd-167">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-167">Command</span></span>                                       | <span data-ttu-id="470dd-168">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="470dd-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="470dd-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="470dd-170">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="470dd-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="470dd-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="470dd-172">Взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="470dd-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="470dd-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="470dd-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="470dd-174">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="470dd-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="470dd-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="470dd-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="470dd-176">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="470dd-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="470dd-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="470dd-178">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="470dd-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="470dd-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="470dd-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="470dd-180">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="470dd-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="470dd-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="470dd-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="470dd-182">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="470dd-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="470dd-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="470dd-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="470dd-184">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="470dd-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="470dd-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="470dd-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="470dd-186">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="470dd-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="470dd-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="470dd-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="470dd-188">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="470dd-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="470dd-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="470dd-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="470dd-190">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="470dd-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="470dd-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="470dd-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="470dd-192">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="470dd-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="470dd-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="470dd-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="470dd-194">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="470dd-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="470dd-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="470dd-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="470dd-196">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="470dd-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="470dd-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="470dd-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="470dd-198">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-198">Command</span></span>                             | <span data-ttu-id="470dd-199">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="470dd-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="470dd-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="470dd-201">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="470dd-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="470dd-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="470dd-203">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="470dd-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="470dd-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="470dd-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="470dd-205">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="470dd-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="470dd-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="470dd-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="470dd-207">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="470dd-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="470dd-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="470dd-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="470dd-209">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="470dd-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="470dd-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="470dd-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="470dd-211">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="470dd-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="470dd-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="470dd-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="470dd-213">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="470dd-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="470dd-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="470dd-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="470dd-215">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="470dd-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="470dd-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="470dd-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="470dd-217">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="470dd-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="470dd-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="470dd-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="470dd-219">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="470dd-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="470dd-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="470dd-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="470dd-221">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="470dd-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="470dd-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="470dd-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="470dd-223">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="470dd-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="470dd-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="470dd-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="470dd-225">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="470dd-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="470dd-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="470dd-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="470dd-227">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-227">Command</span></span>                             | <span data-ttu-id="470dd-228">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="470dd-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="470dd-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="470dd-230">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="470dd-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="470dd-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="470dd-232">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="470dd-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="470dd-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="470dd-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="470dd-234">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="470dd-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="470dd-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="470dd-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="470dd-236">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="470dd-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="470dd-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="470dd-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="470dd-238">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="470dd-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="470dd-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="470dd-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="470dd-240">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="470dd-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="470dd-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="470dd-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="470dd-242">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="470dd-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="470dd-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="470dd-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="470dd-244">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="470dd-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="470dd-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="470dd-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="470dd-246">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="470dd-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="470dd-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="470dd-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="470dd-248">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="470dd-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="470dd-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="470dd-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="470dd-250">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="470dd-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="470dd-251">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="470dd-251">Project references</span></span>

<span data-ttu-id="470dd-252">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-252">Command</span></span> | <span data-ttu-id="470dd-253">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-253">Function</span></span>
--- | ---
[<span data-ttu-id="470dd-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="470dd-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="470dd-255">Добавляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="470dd-255">Adds a project reference.</span></span>
[<span data-ttu-id="470dd-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="470dd-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="470dd-257">Перечисляет ссылки на проекты.</span><span class="sxs-lookup"><span data-stu-id="470dd-257">Lists project references.</span></span>
[<span data-ttu-id="470dd-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="470dd-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="470dd-259">Удаляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="470dd-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="470dd-260">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="470dd-260">NuGet packages</span></span>

<span data-ttu-id="470dd-261">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-261">Command</span></span> | <span data-ttu-id="470dd-262">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-262">Function</span></span>
--- | ---
[<span data-ttu-id="470dd-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="470dd-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="470dd-264">Добавляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="470dd-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="470dd-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="470dd-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="470dd-266">Удаляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="470dd-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="470dd-267">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="470dd-267">NuGet commands</span></span>

<span data-ttu-id="470dd-268">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-268">Command</span></span> | <span data-ttu-id="470dd-269">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-269">Function</span></span>
--- | ---
[<span data-ttu-id="470dd-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="470dd-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="470dd-271">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="470dd-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="470dd-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="470dd-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="470dd-273">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="470dd-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="470dd-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="470dd-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="470dd-275">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="470dd-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="470dd-276">Команды глобальных средств</span><span class="sxs-lookup"><span data-stu-id="470dd-276">Global Tools commands</span></span>

<span data-ttu-id="470dd-277">[Глобальные средства .NET Core](global-tools.md) появились в пакете SDK для .NET Core, начиная с версии 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="470dd-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="470dd-278">Команда</span><span class="sxs-lookup"><span data-stu-id="470dd-278">Command</span></span> | <span data-ttu-id="470dd-279">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-279">Function</span></span>
--- | ---
[<span data-ttu-id="470dd-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="470dd-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="470dd-281">Устанавливает глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="470dd-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="470dd-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="470dd-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="470dd-283">Перечисляет выводит все глобальные средства, установленные на компьютере в каталоге по умолчанию или по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="470dd-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="470dd-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="470dd-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="470dd-285">Удаляет глобальное средство с компьютера.</span><span class="sxs-lookup"><span data-stu-id="470dd-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="470dd-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="470dd-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="470dd-287">Обновляет глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="470dd-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="470dd-288">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="470dd-288">Additional tools</span></span>

<span data-ttu-id="470dd-289">Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="470dd-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="470dd-290">Эти средства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="470dd-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="470dd-291">Средство</span><span class="sxs-lookup"><span data-stu-id="470dd-291">Tool</span></span>                                              | <span data-ttu-id="470dd-292">Функция</span><span class="sxs-lookup"><span data-stu-id="470dd-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="470dd-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="470dd-293">dev-certs</span></span>                                         | <span data-ttu-id="470dd-294">Создает сертификаты разработки и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="470dd-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="470dd-295">ef</span><span class="sxs-lookup"><span data-stu-id="470dd-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="470dd-296">Средства командной строки для Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="470dd-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="470dd-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="470dd-297">sql-cache</span></span>                                         | <span data-ttu-id="470dd-298">Средства командной строки для кэша SQL Server.</span><span class="sxs-lookup"><span data-stu-id="470dd-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="470dd-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="470dd-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="470dd-300">Управляет секретами пользователей для разработки.</span><span class="sxs-lookup"><span data-stu-id="470dd-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="470dd-301">watch</span><span class="sxs-lookup"><span data-stu-id="470dd-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="470dd-302">Запускает наблюдатель за файлами, который выполняет команду при изменении файлов.</span><span class="sxs-lookup"><span data-stu-id="470dd-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="470dd-303">Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="470dd-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="470dd-304">Примеры</span><span class="sxs-lookup"><span data-stu-id="470dd-304">Examples</span></span>

<span data-ttu-id="470dd-305">Создание проекта консольного приложения .NET Core:</span><span class="sxs-lookup"><span data-stu-id="470dd-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="470dd-306">Восстановление зависимостей для данного приложения:</span><span class="sxs-lookup"><span data-stu-id="470dd-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="470dd-307">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="470dd-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="470dd-308">Запустите библиотеку DLL приложения, например `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="470dd-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="470dd-309">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="470dd-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="470dd-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="470dd-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="470dd-311">Папка глобальных пакетов.</span><span class="sxs-lookup"><span data-stu-id="470dd-311">The global packages folder.</span></span> <span data-ttu-id="470dd-312">Если значение не задано, то по умолчанию в Unix используется `~/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="470dd-312">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="470dd-313">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="470dd-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="470dd-314">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="470dd-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="470dd-315">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="470dd-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="470dd-316">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="470dd-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="470dd-317">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="470dd-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="470dd-318">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="470dd-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="470dd-319">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="470dd-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="470dd-320">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="470dd-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="470dd-321">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="470dd-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="470dd-322">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="470dd-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="470dd-323">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="470dd-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="470dd-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="470dd-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="470dd-325">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="470dd-325">The primary package cache.</span></span> <span data-ttu-id="470dd-326">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="470dd-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="470dd-327">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="470dd-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="470dd-328">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="470dd-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="470dd-329">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="470dd-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="470dd-330">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="470dd-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="470dd-331">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="470dd-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="470dd-332">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="470dd-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="470dd-333">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="470dd-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="470dd-334">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="470dd-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="470dd-335">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="470dd-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="470dd-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="470dd-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="470dd-337">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="470dd-337">The primary package cache.</span></span> <span data-ttu-id="470dd-338">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="470dd-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="470dd-339">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="470dd-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="470dd-340">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="470dd-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="470dd-341">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="470dd-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="470dd-342">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="470dd-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="470dd-343">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="470dd-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
