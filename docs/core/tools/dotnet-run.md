---
title: Команда dotnet run
description: Команда dotnet run — это удобное средство для запуска приложения из исходного кода.
ms.date: 05/29/2018
ms.openlocfilehash: 489429e2371c807e09f9fb8c2de6f96d091edc6d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632013"
---
# <a name="dotnet-run"></a><span data-ttu-id="46eeb-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="46eeb-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="46eeb-104">name</span><span class="sxs-lookup"><span data-stu-id="46eeb-104">Name</span></span>

<span data-ttu-id="46eeb-105">`dotnet run` — выполняет исходный код без дополнительных явных команд компиляции или запуска.</span><span class="sxs-lookup"><span data-stu-id="46eeb-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="46eeb-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="46eeb-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="46eeb-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="46eeb-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="46eeb-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="46eeb-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="46eeb-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="46eeb-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="46eeb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="46eeb-110">Description</span></span>

<span data-ttu-id="46eeb-111">`dotnet run` — это удобное средство для запуска приложения из исходного кода одной командой.</span><span class="sxs-lookup"><span data-stu-id="46eeb-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="46eeb-112">Это полезно для быстрой последовательной разработки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="46eeb-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="46eeb-113">В отношении сборки кода эта команда зависима от команды [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="46eeb-114">Любые требования к сборке, например, то, что проект сначала нужно восстановить, применяются и к `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="46eeb-115">Выходные файлы записываются в расположение по умолчанию, которым является `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="46eeb-116">Например, если у вас есть приложение `netcoreapp2.1` и вы запускаете `dotnet run`, выходные данные помещаются в `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-116">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="46eeb-117">При необходимости файлы перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="46eeb-117">Files are overwritten as needed.</span></span> <span data-ttu-id="46eeb-118">Временные файлы помещаются в каталог `obj`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="46eeb-119">Когда в проекте задано несколько платформ, выполнение `dotnet run` приводит к ошибке, если только для указания платформы не используется параметр `-f|--framework <FRAMEWORK>`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="46eeb-120">Команда `dotnet run` используется в контексте проектов, а не созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="46eeb-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="46eeb-121">Если вместо этого вы пытаетесь запустить библиотеку DLL платформозависимого приложения, следует использовать [dotnet](dotnet.md) без команды.</span><span class="sxs-lookup"><span data-stu-id="46eeb-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="46eeb-122">Например, для выполнения `myapp.dll` используйте:</span><span class="sxs-lookup"><span data-stu-id="46eeb-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="46eeb-123">Дополнительные сведения о драйвере `dotnet` см. в разделе [Средства интерфейса командной строки (CLI) .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="46eeb-124">Для запуска приложения команда `dotnet run` разрешает зависимости приложения, выходящие за пределы общей среды выполнения, из кэша NuGet.</span><span class="sxs-lookup"><span data-stu-id="46eeb-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="46eeb-125">Из-за использования кэшированных зависимостей не рекомендуется применять команду `dotnet run` для запуска приложений в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="46eeb-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="46eeb-126">Вместо этого [создайте развертывание](../deploying/index.md) с помощью команды [`dotnet publish`](dotnet-publish.md) и разверните опубликованные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="46eeb-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="46eeb-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="46eeb-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="46eeb-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="46eeb-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="46eeb-129">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="46eeb-130">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="46eeb-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="46eeb-131">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="46eeb-131">Defines the build configuration.</span></span> <span data-ttu-id="46eeb-132">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="46eeb-133">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="46eeb-134">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="46eeb-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="46eeb-135">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="46eeb-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="46eeb-136">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="46eeb-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="46eeb-137">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="46eeb-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="46eeb-138">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="46eeb-139">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="46eeb-140">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="46eeb-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="46eeb-141">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="46eeb-141">Doesn't build the project before running.</span></span> <span data-ttu-id="46eeb-142">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="46eeb-143">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="46eeb-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="46eeb-144">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="46eeb-145">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="46eeb-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="46eeb-146">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="46eeb-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="46eeb-147">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="46eeb-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="46eeb-148">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="46eeb-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="46eeb-149">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="46eeb-150">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="46eeb-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="46eeb-151">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="46eeb-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="46eeb-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="46eeb-153">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="46eeb-154">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="46eeb-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="46eeb-155">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="46eeb-155">Defines the build configuration.</span></span> <span data-ttu-id="46eeb-156">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="46eeb-157">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="46eeb-158">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="46eeb-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="46eeb-159">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="46eeb-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="46eeb-160">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="46eeb-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="46eeb-161">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="46eeb-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="46eeb-162">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="46eeb-163">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="46eeb-164">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="46eeb-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="46eeb-165">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="46eeb-165">Doesn't build the project before running.</span></span> <span data-ttu-id="46eeb-166">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="46eeb-167">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="46eeb-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="46eeb-168">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="46eeb-169">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="46eeb-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="46eeb-170">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="46eeb-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="46eeb-171">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="46eeb-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="46eeb-172">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="46eeb-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="46eeb-173">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="46eeb-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="46eeb-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="46eeb-175">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="46eeb-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="46eeb-176">Все аргументы после разделителя передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="46eeb-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="46eeb-177">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="46eeb-177">Defines the build configuration.</span></span> <span data-ttu-id="46eeb-178">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="46eeb-179">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="46eeb-180">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="46eeb-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="46eeb-181">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="46eeb-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="46eeb-182">Указывает путь и имя файла проекта.</span><span class="sxs-lookup"><span data-stu-id="46eeb-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="46eeb-183">(См. примечание.) Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="46eeb-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="46eeb-184">Используйте путь и имя файла проекта с параметром `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="46eeb-185">Регрессия в интерфейсе командной строки не позволяет указать путь к папке в пакете SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="46eeb-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="46eeb-186">Дополнительные сведения об этой проблеме см. в разделе [dotnet run -p, не удается запустить проект (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="46eeb-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="46eeb-187">Примеры</span><span class="sxs-lookup"><span data-stu-id="46eeb-187">Examples</span></span>

<span data-ttu-id="46eeb-188">Выполнение проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="46eeb-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="46eeb-189">Выполнение указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="46eeb-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="46eeb-190">Выполнение проекта в текущем каталоге (аргумент `--help` в этом примере передается приложению, так как используется пустой параметр `--`):</span><span class="sxs-lookup"><span data-stu-id="46eeb-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="46eeb-191">Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных и последующим запуском проекта (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="46eeb-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
