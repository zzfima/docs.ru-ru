---
title: Команда dotnet — CLI .NET Core
description: Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании.
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: bf69be7eb8dfe454823236012113fa53ed39f2f4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="8f75a-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="8f75a-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8f75a-104">name</span><span class="sxs-lookup"><span data-stu-id="8f75a-104">Name</span></span>

<span data-ttu-id="8f75a-105">`dotnet` — универсальный драйвер для выполнения команд командной строки.</span><span class="sxs-lookup"><span data-stu-id="8f75a-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8f75a-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8f75a-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8f75a-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8f75a-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="8f75a-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="8f75a-109">Description</span></span>

<span data-ttu-id="8f75a-110">`dotnet` — это универсальный драйвер для цепочки инструментов интерфейса командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="8f75a-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="8f75a-111">Если вызвать его без указания команды, выводятся краткие инструкции по использованию.</span><span class="sxs-lookup"><span data-stu-id="8f75a-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="8f75a-112">Каждая отдельная функция реализуется в виде команды.</span><span class="sxs-lookup"><span data-stu-id="8f75a-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="8f75a-113">Для использования функции необходимо указать команду после `dotnet`, например [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="8f75a-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="8f75a-114">Все аргументы после команды относятся именно к ней.</span><span class="sxs-lookup"><span data-stu-id="8f75a-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="8f75a-115">Единственный случай, когда `dotnet` используется в качестве команды самостоятельно, — это запуск [платформозависимых приложений](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f75a-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="8f75a-116">Просто укажите библиотеку DLL приложения после команды `dotnet`, чтобы выполнить приложение (Например, `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="8f75a-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="8f75a-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f75a-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8f75a-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="8f75a-119">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="8f75a-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="8f75a-120">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="8f75a-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="8f75a-121">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="8f75a-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="8f75a-122">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="8f75a-123">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8f75a-123">Prints out a short help for the command.</span></span> <span data-ttu-id="8f75a-124">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="8f75a-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="8f75a-125">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="8f75a-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="8f75a-126">Выполняет накат при отсутствии подходящей общей платформы.</span><span class="sxs-lookup"><span data-stu-id="8f75a-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="8f75a-127">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="8f75a-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8f75a-128">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8f75a-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8f75a-129">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="8f75a-129">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="8f75a-130">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f75a-130">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8f75a-131">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-131">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="8f75a-132">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="8f75a-132">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="8f75a-133">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="8f75a-133">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="8f75a-134">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-134">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="8f75a-135">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8f75a-135">Prints out a short help for the command.</span></span> <span data-ttu-id="8f75a-136">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="8f75a-136">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="8f75a-137">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="8f75a-137">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="8f75a-138">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="8f75a-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8f75a-139">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8f75a-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8f75a-140">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="8f75a-140">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="8f75a-141">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f75a-141">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="8f75a-142">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="8f75a-142">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="8f75a-143">Общие</span><span class="sxs-lookup"><span data-stu-id="8f75a-143">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8f75a-144">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-144">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="8f75a-145">Команда</span><span class="sxs-lookup"><span data-stu-id="8f75a-145">Command</span></span>                             | <span data-ttu-id="8f75a-146">Функция</span><span class="sxs-lookup"><span data-stu-id="8f75a-146">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="8f75a-147">dotnet build</span><span class="sxs-lookup"><span data-stu-id="8f75a-147">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="8f75a-148">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f75a-148">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="8f75a-149">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="8f75a-149">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="8f75a-150">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="8f75a-150">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="8f75a-151">dotnet help</span><span class="sxs-lookup"><span data-stu-id="8f75a-151">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="8f75a-152">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="8f75a-152">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="8f75a-153">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="8f75a-153">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="8f75a-154">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="8f75a-154">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="8f75a-155">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="8f75a-155">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="8f75a-156">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8f75a-156">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="8f75a-157">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8f75a-157">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="8f75a-158">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="8f75a-158">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="8f75a-159">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="8f75a-159">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="8f75a-160">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="8f75a-160">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="8f75a-161">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="8f75a-161">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="8f75a-162">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="8f75a-162">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="8f75a-163">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="8f75a-163">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="8f75a-164">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-164">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="8f75a-165">dotnet run</span><span class="sxs-lookup"><span data-stu-id="8f75a-165">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="8f75a-166">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="8f75a-166">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="8f75a-167">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="8f75a-167">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="8f75a-168">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-168">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="8f75a-169">dotnet store</span><span class="sxs-lookup"><span data-stu-id="8f75a-169">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="8f75a-170">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-170">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="8f75a-171">dotnet test</span><span class="sxs-lookup"><span data-stu-id="8f75a-171">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="8f75a-172">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="8f75a-172">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8f75a-173">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-173">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="8f75a-174">Команда</span><span class="sxs-lookup"><span data-stu-id="8f75a-174">Command</span></span>                             | <span data-ttu-id="8f75a-175">Функция</span><span class="sxs-lookup"><span data-stu-id="8f75a-175">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="8f75a-176">dotnet build</span><span class="sxs-lookup"><span data-stu-id="8f75a-176">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="8f75a-177">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f75a-177">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="8f75a-178">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="8f75a-178">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="8f75a-179">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="8f75a-179">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="8f75a-180">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="8f75a-180">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="8f75a-181">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="8f75a-181">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="8f75a-182">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="8f75a-182">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="8f75a-183">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8f75a-183">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="8f75a-184">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8f75a-184">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="8f75a-185">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="8f75a-185">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="8f75a-186">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="8f75a-186">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="8f75a-187">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="8f75a-187">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="8f75a-188">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="8f75a-188">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="8f75a-189">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="8f75a-189">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="8f75a-190">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="8f75a-190">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="8f75a-191">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-191">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="8f75a-192">dotnet run</span><span class="sxs-lookup"><span data-stu-id="8f75a-192">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="8f75a-193">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="8f75a-193">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="8f75a-194">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="8f75a-194">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="8f75a-195">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-195">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="8f75a-196">dotnet test</span><span class="sxs-lookup"><span data-stu-id="8f75a-196">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="8f75a-197">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="8f75a-197">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="8f75a-198">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="8f75a-198">Project references</span></span>

<span data-ttu-id="8f75a-199">Команда</span><span class="sxs-lookup"><span data-stu-id="8f75a-199">Command</span></span> | <span data-ttu-id="8f75a-200">Функция</span><span class="sxs-lookup"><span data-stu-id="8f75a-200">Function</span></span>
--- | ---
[<span data-ttu-id="8f75a-201">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="8f75a-201">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="8f75a-202">Добавление ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="8f75a-202">Add a project reference.</span></span>
[<span data-ttu-id="8f75a-203">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="8f75a-203">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="8f75a-204">Перечисление ссылок на проект.</span><span class="sxs-lookup"><span data-stu-id="8f75a-204">List project references.</span></span>
[<span data-ttu-id="8f75a-205">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="8f75a-205">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="8f75a-206">Удаление ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="8f75a-206">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="8f75a-207">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="8f75a-207">NuGet packages</span></span>

<span data-ttu-id="8f75a-208">Команда</span><span class="sxs-lookup"><span data-stu-id="8f75a-208">Command</span></span> | <span data-ttu-id="8f75a-209">Функция</span><span class="sxs-lookup"><span data-stu-id="8f75a-209">Function</span></span>
--- | ---
[<span data-ttu-id="8f75a-210">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="8f75a-210">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="8f75a-211">Добавление пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="8f75a-211">Add a NuGet package.</span></span>
[<span data-ttu-id="8f75a-212">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="8f75a-212">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="8f75a-213">Удаление пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="8f75a-213">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="8f75a-214">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="8f75a-214">NuGet commands</span></span>

<span data-ttu-id="8f75a-215">Команда</span><span class="sxs-lookup"><span data-stu-id="8f75a-215">Command</span></span> | <span data-ttu-id="8f75a-216">Функция</span><span class="sxs-lookup"><span data-stu-id="8f75a-216">Function</span></span>
--- | ---
[<span data-ttu-id="8f75a-217">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="8f75a-217">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="8f75a-218">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="8f75a-218">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="8f75a-219">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="8f75a-219">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="8f75a-220">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="8f75a-220">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="8f75a-221">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="8f75a-221">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="8f75a-222">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="8f75a-222">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="8f75a-223">Примеры</span><span class="sxs-lookup"><span data-stu-id="8f75a-223">Examples</span></span>

<span data-ttu-id="8f75a-224">Инициализация образца консольного приложения .NET Core, которое можно скомпилировать и запустить:</span><span class="sxs-lookup"><span data-stu-id="8f75a-224">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="8f75a-225">Восстановление зависимостей для данного приложения:</span><span class="sxs-lookup"><span data-stu-id="8f75a-225">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="8f75a-226">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="8f75a-226">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="8f75a-227">Запуск платформозависимого приложения `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="8f75a-227">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="8f75a-228">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="8f75a-228">Environment variables</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8f75a-229">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-229">.NET Core 2.x</span></span>](#tab/netcore2x)

`DOTNET_PACKAGES`

<span data-ttu-id="8f75a-230">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="8f75a-230">The primary package cache.</span></span> <span data-ttu-id="8f75a-231">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="8f75a-231">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="8f75a-232">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-232">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="8f75a-233">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f75a-233">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="8f75a-234">Задайте значение `true`, чтобы отказаться от функции телеметрии (принимаются значения `true`, `1` или `yes`), в противном случае задайте значение `false`, чтобы согласиться на функции телеметрии (принимаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="8f75a-234">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="8f75a-235">Если значение не задано, то по умолчанию используется `false` и функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="8f75a-235">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="8f75a-236">Указывает, разрешается ли среда выполнения .NET Core, общая платформа или пакет SDK из глобального расположения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-236">Specifies whether .NET Core runtime, shared framework or SDK are resolved from the global location.</span></span> <span data-ttu-id="8f75a-237">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="8f75a-237">If not set, it defaults to `true`.</span></span> <span data-ttu-id="8f75a-238">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="8f75a-238">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="8f75a-239">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="8f75a-239">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8f75a-240">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8f75a-240">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="8f75a-241">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="8f75a-241">The primary package cache.</span></span> <span data-ttu-id="8f75a-242">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="8f75a-242">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="8f75a-243">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f75a-243">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="8f75a-244">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f75a-244">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="8f75a-245">Задайте значение `true`, чтобы отказаться от функции телеметрии (принимаются значения `true`, `1` или `yes`), в противном случае задайте значение `false`, чтобы согласиться на функции телеметрии (принимаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="8f75a-245">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="8f75a-246">Если значение не задано, то по умолчанию используется `false` и функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="8f75a-246">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

---
