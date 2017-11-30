---
title: "Команда dotnet run — CLI .NET Core"
description: "Команда dotnet run — это удобное средство для запуска приложения из исходного кода."
author: mairaw
ms.author: mairaw
ms.date: 09/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 7670934199d7d4b8a7c5e598142366ef1eb3ef1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-run"></a><span data-ttu-id="02339-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="02339-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="02339-104">Имя</span><span class="sxs-lookup"><span data-stu-id="02339-104">Name</span></span>

<span data-ttu-id="02339-105">`dotnet run` — выполняет исходный код без дополнительных явных команд компиляции или запуска.</span><span class="sxs-lookup"><span data-stu-id="02339-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="02339-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="02339-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="02339-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="02339-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="02339-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="02339-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="02339-109">Описание</span><span class="sxs-lookup"><span data-stu-id="02339-109">Description</span></span>

<span data-ttu-id="02339-110">`dotnet run` — это удобное средство для запуска приложения из исходного кода одной командой.</span><span class="sxs-lookup"><span data-stu-id="02339-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="02339-111">Это полезно для быстрой последовательной разработки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="02339-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="02339-112">В отношении сборки кода эта команда зависима от команды [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="02339-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="02339-113">Любые требования к сборке, например, то, что проект сначала нужно восстановить, применяются и к `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="02339-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span> 

<span data-ttu-id="02339-114">Выходные файлы записываются в расположение по умолчанию, которым является `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="02339-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="02339-115">Например, если у вас есть приложение `netcoreapp1.0` и вы запускаете `dotnet run`, выходные данные помещаются в `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="02339-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="02339-116">При необходимости файлы перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="02339-116">Files are overwritten as needed.</span></span> <span data-ttu-id="02339-117">Временные файлы помещаются в каталог `obj`.</span><span class="sxs-lookup"><span data-stu-id="02339-117">Temporary files are placed in the `obj` directory.</span></span> 

<span data-ttu-id="02339-118">Когда в проекте задано несколько платформ, выполнение `dotnet run` приводит к ошибке, если только для указания платформы не используется параметр `-f|--framework <FRAMEWORK>`.</span><span class="sxs-lookup"><span data-stu-id="02339-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="02339-119">Команда `dotnet run` используется в контексте проектов, а не созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="02339-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="02339-120">Если вместо этого вы пытаетесь запустить библиотеку DLL платформозависимого приложения, следует использовать [dotnet](dotnet.md) без команды.</span><span class="sxs-lookup"><span data-stu-id="02339-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="02339-121">Например, для выполнения `myapp.dll` используйте:</span><span class="sxs-lookup"><span data-stu-id="02339-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="02339-122">Дополнительные сведения о драйвере `dotnet` см. в разделе [Средства интерфейса командной строки (CLI) .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="02339-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="02339-123">Для запуска приложения команда `dotnet run` разрешает зависимости приложения, выходящие за пределы общей среды выполнения, из кэша NuGet.</span><span class="sxs-lookup"><span data-stu-id="02339-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="02339-124">Из-за использования кэшированных зависимостей не рекомендуется применять команду `dotnet run` для запуска приложений в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="02339-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="02339-125">Вместо этого [создайте развертывание](../deploying/index.md) с помощью команды [`dotnet publish`](dotnet-publish.md) и разверните опубликованные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="02339-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

## <a name="options"></a><span data-ttu-id="02339-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="02339-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="02339-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="02339-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="02339-128">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="02339-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="02339-129">Все аргументы после этого передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="02339-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="02339-130">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="02339-130">Defines the build configuration.</span></span> <span data-ttu-id="02339-131">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="02339-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="02339-132">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="02339-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="02339-133">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="02339-133">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="02339-134">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="02339-134">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="02339-135">Это эквивалентно удалению *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="02339-135">This is equivalent to deleting *project.assets.json*.</span></span>

`-h|--help`

<span data-ttu-id="02339-136">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="02339-136">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="02339-137">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="02339-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="02339-138">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="02339-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="02339-139">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="02339-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="02339-140">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="02339-140">Doesn't build the project before running.</span></span>

`--no-dependencies`

<span data-ttu-id="02339-141">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="02339-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="02339-142">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="02339-142">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="02339-143">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="02339-143">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="02339-144">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="02339-144">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="02339-145">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="02339-145">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="02339-146">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="02339-146">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="02339-147">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="02339-147">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="02339-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="02339-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="02339-149">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="02339-149">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="02339-150">Все аргументы после этого передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="02339-150">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="02339-151">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="02339-151">Defines the build configuration.</span></span> <span data-ttu-id="02339-152">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="02339-152">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="02339-153">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="02339-153">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="02339-154">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="02339-154">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="02339-155">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="02339-155">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="02339-156">Указывает путь и имя файла проекта.</span><span class="sxs-lookup"><span data-stu-id="02339-156">Specifies the path and name of the project file.</span></span> <span data-ttu-id="02339-157">(См. примечание.) Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="02339-157">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="02339-158">Используйте путь и имя файла проекта с параметром `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="02339-158">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="02339-159">Регрессия в интерфейсе командной строки не позволяет указать путь к папке в пакете SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="02339-159">A regression in the CLI prevents providing a folder path with .NET Core 1.x SDK.</span></span> <span data-ttu-id="02339-160">Дополнительные сведения об этой проблеме см. в разделе [dotnet run -p, не удается запустить проект (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="02339-160">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="02339-161">Примеры</span><span class="sxs-lookup"><span data-stu-id="02339-161">Examples</span></span>

<span data-ttu-id="02339-162">Выполнение проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="02339-162">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="02339-163">Выполнение указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="02339-163">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="02339-164">Выполнение проекта в текущем каталоге (аргумент `--help` в этом примере передается приложению, так как используется аргумент `--`):</span><span class="sxs-lookup"><span data-stu-id="02339-164">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`
