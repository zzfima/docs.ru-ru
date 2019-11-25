---
title: Команда dotnet run
description: Команда dotnet run — это удобное средство для запуска приложения из исходного кода.
ms.date: 10/31/2019
ms.openlocfilehash: 87e9a57e874116533951a9c5eb676be76be2c98d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454776"
---
# <a name="dotnet-run"></a><span data-ttu-id="8b683-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="8b683-103">dotnet run</span></span>

<span data-ttu-id="8b683-104">**Эта статья относится к ✓** SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8b683-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="8b683-105">name</span><span class="sxs-lookup"><span data-stu-id="8b683-105">Name</span></span>

<span data-ttu-id="8b683-106">`dotnet run` — выполняет исходный код без дополнительных явных команд компиляции или запуска.</span><span class="sxs-lookup"><span data-stu-id="8b683-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8b683-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8b683-107">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="8b683-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8b683-108">.NET Core 3.0</span></span>](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8b683-109">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8b683-109">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8b683-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8b683-110">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8b683-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8b683-111">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="8b683-112">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8b683-112">Description</span></span>

<span data-ttu-id="8b683-113">`dotnet run` — это удобное средство для запуска приложения из исходного кода одной командой.</span><span class="sxs-lookup"><span data-stu-id="8b683-113">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="8b683-114">Это полезно для быстрой последовательной разработки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="8b683-114">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="8b683-115">В отношении сборки кода эта команда зависима от команды [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-115">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="8b683-116">Любые требования к сборке, например, то, что проект сначала нужно восстановить, применяются и к `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="8b683-116">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="8b683-117">Выходные файлы записываются в расположение по умолчанию, которым является `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="8b683-117">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="8b683-118">Например, если у вас есть приложение `netcoreapp2.1` и вы запускаете `dotnet run`, выходные данные помещаются в `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="8b683-118">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="8b683-119">При необходимости файлы перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="8b683-119">Files are overwritten as needed.</span></span> <span data-ttu-id="8b683-120">Временные файлы помещаются в каталог `obj`.</span><span class="sxs-lookup"><span data-stu-id="8b683-120">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="8b683-121">Когда в проекте задано несколько платформ, выполнение `dotnet run` приводит к ошибке, если только для указания платформы не используется параметр `-f|--framework <FRAMEWORK>`.</span><span class="sxs-lookup"><span data-stu-id="8b683-121">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="8b683-122">Команда `dotnet run` используется в контексте проектов, а не созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="8b683-122">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="8b683-123">Если вместо этого вы пытаетесь запустить библиотеку DLL платформозависимого приложения, следует использовать [dotnet](dotnet.md) без команды.</span><span class="sxs-lookup"><span data-stu-id="8b683-123">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="8b683-124">Например, для выполнения `myapp.dll` используйте:</span><span class="sxs-lookup"><span data-stu-id="8b683-124">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="8b683-125">Дополнительные сведения о драйвере `dotnet` см. в разделе [Средства интерфейса командной строки (CLI) .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-125">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="8b683-126">Для запуска приложения команда `dotnet run` разрешает зависимости приложения, выходящие за пределы общей среды выполнения, из кэша NuGet.</span><span class="sxs-lookup"><span data-stu-id="8b683-126">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="8b683-127">Из-за использования кэшированных зависимостей не рекомендуется применять команду `dotnet run` для запуска приложений в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="8b683-127">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="8b683-128">Вместо этого [создайте развертывание](../deploying/index.md) с помощью команды [`dotnet publish`](dotnet-publish.md) и разверните опубликованные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8b683-128">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="8b683-129">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b683-129">Options</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="8b683-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8b683-130">.NET Core 3.0</span></span>](#tab/netcore30)

`--`

<span data-ttu-id="8b683-131">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-131">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8b683-132">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="8b683-132">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8b683-133">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="8b683-133">Defines the build configuration.</span></span> <span data-ttu-id="8b683-134">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8b683-134">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8b683-135">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-135">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8b683-136">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8b683-136">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="8b683-137">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="8b683-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8b683-138">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8b683-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="8b683-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8b683-139">Prints out a short help for the command.</span></span>

`--interactive`

<span data-ttu-id="8b683-140">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="8b683-140">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="8b683-141">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-141">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="8b683-142">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="8b683-142">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="8b683-143">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="8b683-143">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="8b683-144">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="8b683-144">Doesn't build the project before running.</span></span> <span data-ttu-id="8b683-145">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="8b683-145">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="8b683-146">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="8b683-146">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="8b683-147">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-147">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="8b683-148">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="8b683-148">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="8b683-149">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="8b683-149">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="8b683-150">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8b683-150">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="8b683-151">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="8b683-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="8b683-152">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="8b683-153">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="8b683-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8b683-154">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8b683-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8b683-155">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8b683-155">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="8b683-156">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-156">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8b683-157">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="8b683-157">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8b683-158">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="8b683-158">Defines the build configuration.</span></span> <span data-ttu-id="8b683-159">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8b683-159">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8b683-160">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-160">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8b683-161">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8b683-161">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="8b683-162">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="8b683-162">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8b683-163">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8b683-163">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="8b683-164">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8b683-164">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="8b683-165">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-165">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="8b683-166">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="8b683-166">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="8b683-167">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="8b683-167">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="8b683-168">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="8b683-168">Doesn't build the project before running.</span></span> <span data-ttu-id="8b683-169">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="8b683-169">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="8b683-170">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="8b683-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="8b683-171">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-171">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="8b683-172">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="8b683-172">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="8b683-173">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="8b683-173">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="8b683-174">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8b683-174">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="8b683-175">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="8b683-175">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="8b683-176">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-176">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="8b683-177">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="8b683-177">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8b683-178">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8b683-178">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8b683-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8b683-179">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="8b683-180">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-180">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8b683-181">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="8b683-181">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8b683-182">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="8b683-182">Defines the build configuration.</span></span> <span data-ttu-id="8b683-183">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8b683-183">The default for most projects value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8b683-184">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-184">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8b683-185">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8b683-185">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="8b683-186">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="8b683-186">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8b683-187">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8b683-187">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="8b683-188">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8b683-188">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="8b683-189">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-189">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="8b683-190">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="8b683-190">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="8b683-191">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="8b683-191">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="8b683-192">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="8b683-192">Doesn't build the project before running.</span></span> <span data-ttu-id="8b683-193">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="8b683-193">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="8b683-194">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="8b683-194">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="8b683-195">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-195">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="8b683-196">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="8b683-196">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="8b683-197">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="8b683-197">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="8b683-198">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8b683-198">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="8b683-199">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="8b683-199">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="8b683-200">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-200">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8b683-201">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8b683-201">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="8b683-202">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="8b683-202">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8b683-203">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="8b683-203">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8b683-204">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="8b683-204">Defines the build configuration.</span></span> <span data-ttu-id="8b683-205">Значение по умолчанию для большинства проектов — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8b683-205">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8b683-206">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8b683-206">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8b683-207">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="8b683-207">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="8b683-208">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8b683-208">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="8b683-209">Указывает путь и имя файла проекта.</span><span class="sxs-lookup"><span data-stu-id="8b683-209">Specifies the path and name of the project file.</span></span> <span data-ttu-id="8b683-210">(См. примечание.) Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8b683-210">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="8b683-211">Используйте путь и имя файла проекта с параметром `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="8b683-211">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="8b683-212">Регрессия в интерфейсе командной строки не позволяет указать путь к папке в пакете SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="8b683-212">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="8b683-213">Дополнительные сведения об этой проблеме см. в разделе [dotnet run -p, не удается запустить проект (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="8b683-213">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="8b683-214">Примеры</span><span class="sxs-lookup"><span data-stu-id="8b683-214">Examples</span></span>

<span data-ttu-id="8b683-215">Выполнение проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="8b683-215">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="8b683-216">Выполнение указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="8b683-216">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="8b683-217">Выполнение проекта в текущем каталоге (аргумент `--help` в этом примере передается приложению, так как используется пустой параметр `--`):</span><span class="sxs-lookup"><span data-stu-id="8b683-217">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="8b683-218">Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных и последующим запуском проекта (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="8b683-218">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
