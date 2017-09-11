---
title: "Команда dotnet — CLI .NET Core"
description: "Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: fa2e5ecbf41dc2a8cd90aabc6f7291db597e657e
ms.openlocfilehash: 4c1c0e4ed1b1222abbcd104b2c10a44b1b99be8d
ms.contentlocale: ru-ru
ms.lasthandoff: 08/17/2017

---
# <a name="dotnet-command"></a><span data-ttu-id="89ec1-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="89ec1-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="89ec1-104">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec1-104">Name</span></span>

<span data-ttu-id="89ec1-105">`dotnet` — универсальный драйвер для выполнения команд командной строки.</span><span class="sxs-lookup"><span data-stu-id="89ec1-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89ec1-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="89ec1-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="89ec1-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="89ec1-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89ec1-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89ec1-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a><span data-ttu-id="89ec1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec1-109">Description</span></span>

<span data-ttu-id="89ec1-110">`dotnet` — это универсальный драйвер для цепочки инструментов интерфейса командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="89ec1-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="89ec1-111">Если вызвать его без указания команды, выводятся краткие инструкции по использованию.</span><span class="sxs-lookup"><span data-stu-id="89ec1-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="89ec1-112">Каждая отдельная функция реализуется в виде команды.</span><span class="sxs-lookup"><span data-stu-id="89ec1-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="89ec1-113">Для использования функции необходимо указать команду после `dotnet`, например [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="89ec1-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="89ec1-114">Все аргументы после команды относятся именно к ней.</span><span class="sxs-lookup"><span data-stu-id="89ec1-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="89ec1-115">Единственный случай, когда `dotnet` используется в качестве команды самостоятельно, — это запуск [платформозависимых приложений](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="89ec1-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="89ec1-116">Просто укажите библиотеку DLL приложения после команды `dotnet`, чтобы выполнить приложение (Например, `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="89ec1-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="89ec1-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="89ec1-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="89ec1-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="89ec1-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additionaldeps <PATH>`

<span data-ttu-id="89ec1-119">Путь к дополнительному файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="89ec1-119">Path to additonal *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="89ec1-120">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="89ec1-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="89ec1-121">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="89ec1-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="89ec1-122">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="89ec1-123">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="89ec1-123">Prints out a short help for the command.</span></span> <span data-ttu-id="89ec1-124">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="89ec1-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="89ec1-125">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="89ec1-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="89ec1-126">Выполняет накат при отсутствии подходящей общей платформы.</span><span class="sxs-lookup"><span data-stu-id="89ec1-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbose`

<span data-ttu-id="89ec1-127">Включает подробные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="89ec1-127">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="89ec1-128">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89ec1-128">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89ec1-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89ec1-129">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="89ec1-130">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="89ec1-130">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="89ec1-131">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="89ec1-131">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="89ec1-132">Версия установленной среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-132">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="89ec1-133">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="89ec1-133">Prints out a short help for the command.</span></span> <span data-ttu-id="89ec1-134">При использовании с `dotnet` также выводится список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="89ec1-134">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="89ec1-135">Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.</span><span class="sxs-lookup"><span data-stu-id="89ec1-135">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbose`

<span data-ttu-id="89ec1-136">Включает подробные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="89ec1-136">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="89ec1-137">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89ec1-137">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="89ec1-138">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="89ec1-138">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="89ec1-139">Общие</span><span class="sxs-lookup"><span data-stu-id="89ec1-139">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="89ec1-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="89ec1-140">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="89ec1-141">Команда</span><span class="sxs-lookup"><span data-stu-id="89ec1-141">Command</span></span>                             | <span data-ttu-id="89ec1-142">Функция</span><span class="sxs-lookup"><span data-stu-id="89ec1-142">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="89ec1-143">dotnet build</span><span class="sxs-lookup"><span data-stu-id="89ec1-143">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="89ec1-144">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89ec1-144">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="89ec1-145">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="89ec1-145">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="89ec1-146">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="89ec1-146">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="89ec1-147">dotnet help</span><span class="sxs-lookup"><span data-stu-id="89ec1-147">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="89ec1-148">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="89ec1-148">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="89ec1-149">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="89ec1-149">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="89ec1-150">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="89ec1-150">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="89ec1-151">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="89ec1-151">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="89ec1-152">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="89ec1-152">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="89ec1-153">dotnet new</span><span class="sxs-lookup"><span data-stu-id="89ec1-153">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="89ec1-154">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="89ec1-154">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="89ec1-155">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="89ec1-155">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="89ec1-156">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="89ec1-156">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="89ec1-157">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="89ec1-157">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="89ec1-158">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="89ec1-158">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="89ec1-159">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="89ec1-159">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="89ec1-160">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-160">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="89ec1-161">dotnet run</span><span class="sxs-lookup"><span data-stu-id="89ec1-161">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="89ec1-162">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="89ec1-162">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="89ec1-163">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="89ec1-163">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="89ec1-164">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-164">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="89ec1-165">dotnet store</span><span class="sxs-lookup"><span data-stu-id="89ec1-165">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="89ec1-166">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-166">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="89ec1-167">dotnet test</span><span class="sxs-lookup"><span data-stu-id="89ec1-167">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="89ec1-168">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="89ec1-168">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89ec1-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89ec1-169">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="89ec1-170">Команда</span><span class="sxs-lookup"><span data-stu-id="89ec1-170">Command</span></span>                             | <span data-ttu-id="89ec1-171">Функция</span><span class="sxs-lookup"><span data-stu-id="89ec1-171">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="89ec1-172">dotnet build</span><span class="sxs-lookup"><span data-stu-id="89ec1-172">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="89ec1-173">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89ec1-173">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="89ec1-174">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="89ec1-174">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="89ec1-175">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="89ec1-175">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="89ec1-176">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="89ec1-176">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="89ec1-177">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="89ec1-177">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="89ec1-178">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="89ec1-178">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="89ec1-179">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="89ec1-179">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="89ec1-180">dotnet new</span><span class="sxs-lookup"><span data-stu-id="89ec1-180">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="89ec1-181">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="89ec1-181">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="89ec1-182">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="89ec1-182">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="89ec1-183">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="89ec1-183">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="89ec1-184">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="89ec1-184">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="89ec1-185">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="89ec1-185">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="89ec1-186">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="89ec1-186">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="89ec1-187">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-187">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="89ec1-188">dotnet run</span><span class="sxs-lookup"><span data-stu-id="89ec1-188">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="89ec1-189">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="89ec1-189">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="89ec1-190">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="89ec1-190">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="89ec1-191">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-191">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="89ec1-192">dotnet test</span><span class="sxs-lookup"><span data-stu-id="89ec1-192">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="89ec1-193">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="89ec1-193">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="89ec1-194">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="89ec1-194">Project references</span></span>

<span data-ttu-id="89ec1-195">Команда</span><span class="sxs-lookup"><span data-stu-id="89ec1-195">Command</span></span> | <span data-ttu-id="89ec1-196">Функция</span><span class="sxs-lookup"><span data-stu-id="89ec1-196">Function</span></span>
--- | ---
[<span data-ttu-id="89ec1-197">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="89ec1-197">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="89ec1-198">Добавление ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="89ec1-198">Add a project reference.</span></span>
[<span data-ttu-id="89ec1-199">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="89ec1-199">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="89ec1-200">Перечисление ссылок на проект.</span><span class="sxs-lookup"><span data-stu-id="89ec1-200">List project references.</span></span>
[<span data-ttu-id="89ec1-201">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="89ec1-201">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="89ec1-202">Удаление ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="89ec1-202">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="89ec1-203">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="89ec1-203">NuGet packages</span></span>

<span data-ttu-id="89ec1-204">Команда</span><span class="sxs-lookup"><span data-stu-id="89ec1-204">Command</span></span> | <span data-ttu-id="89ec1-205">Функция</span><span class="sxs-lookup"><span data-stu-id="89ec1-205">Function</span></span>
--- | ---
[<span data-ttu-id="89ec1-206">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="89ec1-206">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="89ec1-207">Добавление пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="89ec1-207">Add a NuGet package.</span></span>
[<span data-ttu-id="89ec1-208">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="89ec1-208">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="89ec1-209">Удаление пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="89ec1-209">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="89ec1-210">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="89ec1-210">NuGet commands</span></span>

<span data-ttu-id="89ec1-211">Команда</span><span class="sxs-lookup"><span data-stu-id="89ec1-211">Command</span></span> | <span data-ttu-id="89ec1-212">Функция</span><span class="sxs-lookup"><span data-stu-id="89ec1-212">Function</span></span>
--- | ---
[<span data-ttu-id="89ec1-213">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="89ec1-213">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="89ec1-214">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="89ec1-214">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="89ec1-215">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="89ec1-215">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="89ec1-216">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="89ec1-216">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="89ec1-217">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="89ec1-217">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="89ec1-218">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="89ec1-218">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="89ec1-219">Примеры</span><span class="sxs-lookup"><span data-stu-id="89ec1-219">Examples</span></span>

<span data-ttu-id="89ec1-220">Инициализация образца консольного приложения .NET Core, которое можно скомпилировать и запустить:</span><span class="sxs-lookup"><span data-stu-id="89ec1-220">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="89ec1-221">Восстановление зависимостей для данного приложения:</span><span class="sxs-lookup"><span data-stu-id="89ec1-221">Restore dependencies for a given application:</span></span>

`dotnet restore`

<span data-ttu-id="89ec1-222">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="89ec1-222">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="89ec1-223">Запуск платформозависимого приложения `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="89ec1-223">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="89ec1-224">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="89ec1-224">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="89ec1-225">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="89ec1-225">The primary package cache.</span></span> <span data-ttu-id="89ec1-226">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.</span><span class="sxs-lookup"><span data-stu-id="89ec1-226">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="89ec1-227">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="89ec1-227">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="89ec1-228">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="89ec1-228">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="89ec1-229">Задайте значение `true`, чтобы отказаться от функции телеметрии (принимаются значения `true`, `1` или `yes`), в противном случае задайте значение `false`, чтобы согласиться на функции телеметрии (принимаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="89ec1-229">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="89ec1-230">Если значение не задано, то по умолчанию используется `false` и функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="89ec1-230">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

