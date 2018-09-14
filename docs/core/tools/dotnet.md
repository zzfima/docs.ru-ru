---
title: Команда dotnet — CLI .NET Core
description: Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 53e8f8bab1cbaabaa7926aa68197c18843b0b637
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44079820"
---
# <a name="dotnet-command"></a><span data-ttu-id="14d0c-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="14d0c-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="14d0c-104">name</span><span class="sxs-lookup"><span data-stu-id="14d0c-104">Name</span></span>

<span data-ttu-id="14d0c-105">`dotnet` — средство для управления исходным кодом .NET и двоичными объектами.</span><span class="sxs-lookup"><span data-stu-id="14d0c-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="14d0c-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="14d0c-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="14d0c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="14d0c-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="14d0c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="14d0c-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="14d0c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="14d0c-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="14d0c-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="14d0c-110">Description</span></span>

<span data-ttu-id="14d0c-111">`dotnet` — это средство для управления исходным кодом .NET и двоичными объектами.</span><span class="sxs-lookup"><span data-stu-id="14d0c-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="14d0c-112">Он предоставляет команды, выполняющие определенные задачи, такие как [`dotnet build`](dotnet-build.md) и [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="14d0c-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="14d0c-113">Каждая команда определяет свои аргументы.</span><span class="sxs-lookup"><span data-stu-id="14d0c-113">Each command defines its own arguments.</span></span> <span data-ttu-id="14d0c-114">Введите `--help` после каждой команды для доступа к краткой справочной документации.</span><span class="sxs-lookup"><span data-stu-id="14d0c-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="14d0c-115">`dotnet` можно использовать для запуска приложений путем указания библиотеки DLL приложения, например `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="14d0c-116">Дополнительные сведения о параметрах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="14d0c-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="14d0c-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="14d0c-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="14d0c-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="14d0c-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="14d0c-119">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="14d0c-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="14d0c-120">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="14d0c-121">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="14d0c-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="14d0c-122">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="14d0c-123">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="14d0c-124">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="14d0c-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="14d0c-125">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="14d0c-126">Отображает установленные среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="14d0c-127">Отображает установленные пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="14d0c-128">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="14d0c-129">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="14d0c-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="14d0c-130">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="14d0c-131">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="14d0c-132">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="14d0c-133">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="14d0c-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="14d0c-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="14d0c-135">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="14d0c-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="14d0c-136">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="14d0c-137">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="14d0c-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="14d0c-138">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="14d0c-139">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="14d0c-140">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="14d0c-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="14d0c-141">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="14d0c-142">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="14d0c-143">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="14d0c-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="14d0c-144">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="14d0c-145">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="14d0c-146">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="14d0c-147">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="14d0c-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="14d0c-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="14d0c-149">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="14d0c-150">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="14d0c-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="14d0c-151">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="14d0c-152">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="14d0c-153">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="14d0c-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="14d0c-154">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="14d0c-155">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="14d0c-156">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="14d0c-157">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="14d0c-158">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="14d0c-159">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="14d0c-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="14d0c-160">Общие</span><span class="sxs-lookup"><span data-stu-id="14d0c-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="14d0c-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="14d0c-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="14d0c-162">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-162">Command</span></span>                                       | <span data-ttu-id="14d0c-163">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="14d0c-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="14d0c-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="14d0c-165">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="14d0c-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="14d0c-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="14d0c-167">Взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="14d0c-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="14d0c-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="14d0c-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="14d0c-169">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="14d0c-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="14d0c-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="14d0c-171">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="14d0c-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="14d0c-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="14d0c-173">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="14d0c-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="14d0c-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="14d0c-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="14d0c-175">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="14d0c-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="14d0c-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="14d0c-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="14d0c-177">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="14d0c-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="14d0c-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="14d0c-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="14d0c-179">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="14d0c-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="14d0c-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="14d0c-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="14d0c-181">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="14d0c-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="14d0c-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="14d0c-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="14d0c-183">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="14d0c-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="14d0c-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="14d0c-185">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="14d0c-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="14d0c-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="14d0c-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="14d0c-187">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="14d0c-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="14d0c-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="14d0c-189">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="14d0c-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="14d0c-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="14d0c-191">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="14d0c-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="14d0c-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="14d0c-193">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-193">Command</span></span>                             | <span data-ttu-id="14d0c-194">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="14d0c-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="14d0c-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="14d0c-196">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="14d0c-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="14d0c-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="14d0c-198">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="14d0c-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="14d0c-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="14d0c-200">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="14d0c-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="14d0c-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="14d0c-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="14d0c-202">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="14d0c-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="14d0c-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="14d0c-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="14d0c-204">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="14d0c-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="14d0c-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="14d0c-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="14d0c-206">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="14d0c-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="14d0c-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="14d0c-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="14d0c-208">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="14d0c-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="14d0c-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="14d0c-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="14d0c-210">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="14d0c-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="14d0c-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="14d0c-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="14d0c-212">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="14d0c-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="14d0c-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="14d0c-214">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="14d0c-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="14d0c-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="14d0c-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="14d0c-216">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="14d0c-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="14d0c-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="14d0c-218">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="14d0c-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="14d0c-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="14d0c-220">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="14d0c-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="14d0c-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="14d0c-222">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-222">Command</span></span>                             | <span data-ttu-id="14d0c-223">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="14d0c-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="14d0c-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="14d0c-225">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="14d0c-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="14d0c-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="14d0c-227">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="14d0c-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="14d0c-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="14d0c-229">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="14d0c-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="14d0c-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="14d0c-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="14d0c-231">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="14d0c-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="14d0c-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="14d0c-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="14d0c-233">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="14d0c-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="14d0c-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="14d0c-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="14d0c-235">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="14d0c-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="14d0c-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="14d0c-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="14d0c-237">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="14d0c-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="14d0c-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="14d0c-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="14d0c-239">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="14d0c-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="14d0c-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="14d0c-241">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="14d0c-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="14d0c-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="14d0c-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="14d0c-243">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="14d0c-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="14d0c-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="14d0c-245">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="14d0c-246">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="14d0c-246">Project references</span></span>

<span data-ttu-id="14d0c-247">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-247">Command</span></span> | <span data-ttu-id="14d0c-248">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-248">Function</span></span>
--- | ---
[<span data-ttu-id="14d0c-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="14d0c-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="14d0c-250">Добавляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="14d0c-250">Adds a project reference.</span></span>
[<span data-ttu-id="14d0c-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="14d0c-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="14d0c-252">Перечисляет ссылки на проекты.</span><span class="sxs-lookup"><span data-stu-id="14d0c-252">Lists project references.</span></span>
[<span data-ttu-id="14d0c-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="14d0c-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="14d0c-254">Удаляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="14d0c-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="14d0c-255">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="14d0c-255">NuGet packages</span></span>

<span data-ttu-id="14d0c-256">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-256">Command</span></span> | <span data-ttu-id="14d0c-257">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-257">Function</span></span>
--- | ---
[<span data-ttu-id="14d0c-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="14d0c-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="14d0c-259">Добавляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="14d0c-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="14d0c-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="14d0c-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="14d0c-261">Удаляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="14d0c-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="14d0c-262">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="14d0c-262">NuGet commands</span></span>

<span data-ttu-id="14d0c-263">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-263">Command</span></span> | <span data-ttu-id="14d0c-264">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-264">Function</span></span>
--- | ---
[<span data-ttu-id="14d0c-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="14d0c-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="14d0c-266">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="14d0c-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="14d0c-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="14d0c-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="14d0c-268">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="14d0c-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="14d0c-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="14d0c-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="14d0c-270">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="14d0c-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="14d0c-271">Команды глобальных средств</span><span class="sxs-lookup"><span data-stu-id="14d0c-271">Global Tools commands</span></span>

<span data-ttu-id="14d0c-272">[Глобальные средства .NET Core](global-tools.md) появились в пакете SDK для .NET Core, начиная с версии 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="14d0c-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="14d0c-273">Команда</span><span class="sxs-lookup"><span data-stu-id="14d0c-273">Command</span></span> | <span data-ttu-id="14d0c-274">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-274">Function</span></span>
--- | ---
[<span data-ttu-id="14d0c-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="14d0c-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="14d0c-276">Устанавливает глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="14d0c-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="14d0c-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="14d0c-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="14d0c-278">Перечисляет выводит все глобальные средства, установленные на компьютере в каталоге по умолчанию или по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="14d0c-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="14d0c-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="14d0c-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="14d0c-280">Удаляет глобальное средство с компьютера.</span><span class="sxs-lookup"><span data-stu-id="14d0c-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="14d0c-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="14d0c-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="14d0c-282">Обновляет глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="14d0c-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="14d0c-283">Дополнительные инструменты</span><span class="sxs-lookup"><span data-stu-id="14d0c-283">Additional tools</span></span>

<span data-ttu-id="14d0c-284">Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="14d0c-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="14d0c-285">Эти средства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="14d0c-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="14d0c-286">Средство</span><span class="sxs-lookup"><span data-stu-id="14d0c-286">Tool</span></span>                                              | <span data-ttu-id="14d0c-287">Функция</span><span class="sxs-lookup"><span data-stu-id="14d0c-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="14d0c-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="14d0c-288">dev-certs</span></span>                                         | <span data-ttu-id="14d0c-289">Создает сертификаты разработки и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="14d0c-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="14d0c-290">ef</span><span class="sxs-lookup"><span data-stu-id="14d0c-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="14d0c-291">Средства командной строки для Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="14d0c-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="14d0c-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="14d0c-292">sql-cache</span></span>                                         | <span data-ttu-id="14d0c-293">Средства командной строки для кэша SQL Server.</span><span class="sxs-lookup"><span data-stu-id="14d0c-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="14d0c-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="14d0c-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="14d0c-295">Управляет секретами пользователей для разработки.</span><span class="sxs-lookup"><span data-stu-id="14d0c-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="14d0c-296">watch</span><span class="sxs-lookup"><span data-stu-id="14d0c-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="14d0c-297">Запускает наблюдатель за файлами, который выполняет команду при изменении файлов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="14d0c-298">Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="14d0c-299">Примеры</span><span class="sxs-lookup"><span data-stu-id="14d0c-299">Examples</span></span>

<span data-ttu-id="14d0c-300">Создание проекта консольного приложения .NET Core:</span><span class="sxs-lookup"><span data-stu-id="14d0c-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="14d0c-301">Восстановление зависимостей для данного приложения:</span><span class="sxs-lookup"><span data-stu-id="14d0c-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="14d0c-302">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="14d0c-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="14d0c-303">Запустите библиотеку DLL приложения, например `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="14d0c-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="14d0c-304">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="14d0c-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="14d0c-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="14d0c-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="14d0c-306">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-306">The primary package cache.</span></span> <span data-ttu-id="14d0c-307">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="14d0c-308">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="14d0c-309">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="14d0c-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="14d0c-310">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="14d0c-311">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="14d0c-312">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="14d0c-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="14d0c-313">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="14d0c-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="14d0c-314">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="14d0c-315">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="14d0c-316">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="14d0c-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="14d0c-317">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="14d0c-318">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="14d0c-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="14d0c-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="14d0c-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="14d0c-320">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-320">The primary package cache.</span></span> <span data-ttu-id="14d0c-321">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="14d0c-322">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="14d0c-323">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="14d0c-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="14d0c-324">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="14d0c-325">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="14d0c-326">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="14d0c-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="14d0c-327">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="14d0c-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="14d0c-328">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="14d0c-329">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="14d0c-330">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="14d0c-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="14d0c-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="14d0c-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="14d0c-332">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="14d0c-332">The primary package cache.</span></span> <span data-ttu-id="14d0c-333">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="14d0c-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="14d0c-334">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14d0c-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="14d0c-335">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="14d0c-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="14d0c-336">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="14d0c-337">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="14d0c-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="14d0c-338">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="14d0c-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
