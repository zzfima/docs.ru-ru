---
title: Команда dotnet run
description: Команда dotnet run — это удобное средство для запуска приложения из исходного кода.
ms.date: 10/31/2019
ms.openlocfilehash: 5920f0d1f04204b286fdf6f51f5fd13644846390
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734104"
---
# <a name="dotnet-run"></a><span data-ttu-id="e0176-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e0176-103">dotnet run</span></span>

<span data-ttu-id="e0176-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e0176-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="e0176-105">name</span><span class="sxs-lookup"><span data-stu-id="e0176-105">Name</span></span>

<span data-ttu-id="e0176-106">`dotnet run` — выполняет исходный код без дополнительных явных команд компиляции или запуска.</span><span class="sxs-lookup"><span data-stu-id="e0176-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e0176-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e0176-107">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="e0176-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e0176-108">.NET Core 3.0</span></span>](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0176-109">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0176-109">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0176-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0176-110">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0176-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0176-111">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e0176-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e0176-112">Description</span></span>

<span data-ttu-id="e0176-113">`dotnet run` — это удобное средство для запуска приложения из исходного кода одной командой.</span><span class="sxs-lookup"><span data-stu-id="e0176-113">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="e0176-114">Это полезно для быстрой последовательной разработки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e0176-114">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="e0176-115">В отношении сборки кода эта команда зависима от команды [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-115">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="e0176-116">Любые требования к сборке, например, то, что проект сначала нужно восстановить, применяются и к `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="e0176-116">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="e0176-117">Выходные файлы записываются в расположение по умолчанию, которым является `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="e0176-117">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="e0176-118">Например, если у вас есть приложение `netcoreapp2.1` и вы запускаете `dotnet run`, выходные данные помещаются в `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="e0176-118">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="e0176-119">При необходимости файлы перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="e0176-119">Files are overwritten as needed.</span></span> <span data-ttu-id="e0176-120">Временные файлы помещаются в каталог `obj`.</span><span class="sxs-lookup"><span data-stu-id="e0176-120">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="e0176-121">Когда в проекте задано несколько платформ, выполнение `dotnet run` приводит к ошибке, если только для указания платформы не используется параметр `-f|--framework <FRAMEWORK>`.</span><span class="sxs-lookup"><span data-stu-id="e0176-121">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="e0176-122">Команда `dotnet run` используется в контексте проектов, а не созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="e0176-122">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="e0176-123">Если вместо этого вы пытаетесь запустить библиотеку DLL платформозависимого приложения, следует использовать [dotnet](dotnet.md) без команды.</span><span class="sxs-lookup"><span data-stu-id="e0176-123">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="e0176-124">Например, для выполнения `myapp.dll` используйте:</span><span class="sxs-lookup"><span data-stu-id="e0176-124">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="e0176-125">Дополнительные сведения о драйвере `dotnet` см. в разделе [Средства интерфейса командной строки (CLI) .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-125">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="e0176-126">Для запуска приложения команда `dotnet run` разрешает зависимости приложения, выходящие за пределы общей среды выполнения, из кэша NuGet.</span><span class="sxs-lookup"><span data-stu-id="e0176-126">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="e0176-127">Из-за использования кэшированных зависимостей не рекомендуется применять команду `dotnet run` для запуска приложений в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="e0176-127">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="e0176-128">Вместо этого [создайте развертывание](../deploying/index.md) с помощью команды [`dotnet publish`](dotnet-publish.md) и разверните опубликованные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e0176-128">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="e0176-129">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0176-129">Options</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="e0176-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e0176-130">.NET Core 3.0</span></span>](#tab/netcore30)

`--`

<span data-ttu-id="e0176-131">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-131">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e0176-132">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="e0176-132">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e0176-133">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="e0176-133">Defines the build configuration.</span></span> <span data-ttu-id="e0176-134">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e0176-134">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e0176-135">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-135">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e0176-136">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e0176-136">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="e0176-137">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="e0176-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e0176-138">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e0176-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="e0176-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e0176-139">Prints out a short help for the command.</span></span>

`--interactive`

<span data-ttu-id="e0176-140">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="e0176-140">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="e0176-141">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-141">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="e0176-142">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="e0176-142">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="e0176-143">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="e0176-143">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="e0176-144">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="e0176-144">Doesn't build the project before running.</span></span> <span data-ttu-id="e0176-145">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="e0176-145">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="e0176-146">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="e0176-146">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="e0176-147">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-147">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="e0176-148">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="e0176-148">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="e0176-149">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="e0176-149">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="e0176-150">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0176-150">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e0176-151">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="e0176-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="e0176-152">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0176-153">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="e0176-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0176-154">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e0176-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0176-155">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0176-155">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="e0176-156">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-156">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e0176-157">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="e0176-157">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e0176-158">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="e0176-158">Defines the build configuration.</span></span> <span data-ttu-id="e0176-159">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e0176-159">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e0176-160">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-160">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e0176-161">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e0176-161">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="e0176-162">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="e0176-162">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e0176-163">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e0176-163">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="e0176-164">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e0176-164">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="e0176-165">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-165">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="e0176-166">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="e0176-166">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="e0176-167">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="e0176-167">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="e0176-168">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="e0176-168">Doesn't build the project before running.</span></span> <span data-ttu-id="e0176-169">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="e0176-169">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="e0176-170">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="e0176-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="e0176-171">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-171">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="e0176-172">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="e0176-172">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="e0176-173">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="e0176-173">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="e0176-174">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0176-174">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e0176-175">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="e0176-175">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="e0176-176">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-176">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0176-177">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="e0176-177">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0176-178">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e0176-178">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0176-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0176-179">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="e0176-180">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-180">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e0176-181">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="e0176-181">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e0176-182">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="e0176-182">Defines the build configuration.</span></span> <span data-ttu-id="e0176-183">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e0176-183">The default for most projects value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e0176-184">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-184">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e0176-185">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e0176-185">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="e0176-186">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="e0176-186">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e0176-187">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e0176-187">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="e0176-188">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e0176-188">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="e0176-189">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-189">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="e0176-190">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="e0176-190">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="e0176-191">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="e0176-191">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="e0176-192">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="e0176-192">Doesn't build the project before running.</span></span> <span data-ttu-id="e0176-193">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="e0176-193">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="e0176-194">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="e0176-194">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="e0176-195">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-195">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="e0176-196">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="e0176-196">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="e0176-197">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="e0176-197">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="e0176-198">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0176-198">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e0176-199">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="e0176-199">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="e0176-200">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-200">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0176-201">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0176-201">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="e0176-202">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="e0176-202">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e0176-203">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="e0176-203">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e0176-204">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="e0176-204">Defines the build configuration.</span></span> <span data-ttu-id="e0176-205">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e0176-205">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e0176-206">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0176-206">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e0176-207">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e0176-207">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="e0176-208">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="e0176-208">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="e0176-209">Указывает путь и имя файла проекта.</span><span class="sxs-lookup"><span data-stu-id="e0176-209">Specifies the path and name of the project file.</span></span> <span data-ttu-id="e0176-210">(См. примечание.) Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0176-210">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="e0176-211">Используйте путь и имя файла проекта с параметром `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="e0176-211">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="e0176-212">Регрессия в интерфейсе командной строки не позволяет указать путь к папке в пакете SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="e0176-212">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="e0176-213">Дополнительные сведения об этой проблеме см. в разделе [dotnet run -p, не удается запустить проект (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="e0176-213">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="e0176-214">Примеры</span><span class="sxs-lookup"><span data-stu-id="e0176-214">Examples</span></span>

<span data-ttu-id="e0176-215">Выполнение проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="e0176-215">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="e0176-216">Выполнение указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="e0176-216">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="e0176-217">Выполнение проекта в текущем каталоге (аргумент `--help` в этом примере передается приложению, так как используется пустой параметр `--`):</span><span class="sxs-lookup"><span data-stu-id="e0176-217">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="e0176-218">Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных и последующим запуском проекта (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="e0176-218">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
