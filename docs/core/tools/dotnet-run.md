---
title: "Команда dotnet run — CLI .NET Core"
description: "Команда dotnet run — это удобное средство для запуска приложения из исходного кода."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 30dd1a7715c8573062837aaf71344258d0036b5d
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-run"></a><span data-ttu-id="7fa9c-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="7fa9c-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7fa9c-104">Имя</span><span class="sxs-lookup"><span data-stu-id="7fa9c-104">Name</span></span>

<span data-ttu-id="7fa9c-105">`dotnet run` — выполняет исходный код без дополнительных явных команд компиляции или запуска.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7fa9c-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7fa9c-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7fa9c-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7fa9c-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7fa9c-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7fa9c-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="7fa9c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7fa9c-109">Description</span></span>

<span data-ttu-id="7fa9c-110">`dotnet run` — это удобное средство для запуска приложения из исходного кода одной командой.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="7fa9c-111">Это полезно для быстрой последовательной разработки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="7fa9c-112">В отношении сборки кода эта команда зависима от команды [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="7fa9c-113">Любые требования к сборке, например, то, что проект сначала нужно восстановить, применяются и к `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span> 

<span data-ttu-id="7fa9c-114">Выходные файлы записываются в расположение по умолчанию, которым является `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="7fa9c-115">Например, если у вас есть приложение `netcoreapp1.0` и вы запускаете `dotnet run`, выходные данные помещаются в `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="7fa9c-116">При необходимости файлы перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-116">Files are overwritten as needed.</span></span> <span data-ttu-id="7fa9c-117">Временные файлы помещаются в каталог `obj`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-117">Temporary files are placed in the `obj` directory.</span></span> 

<span data-ttu-id="7fa9c-118">Когда в проекте задано несколько платформ, выполнение `dotnet run` приводит к ошибке, если только для указания платформы не используется параметр `-f|--framework <FRAMEWORK>`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="7fa9c-119">Команда `dotnet run` используется в контексте проектов, а не созданных сборок.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="7fa9c-120">Если вместо этого вы пытаетесь запустить библиотеку DLL платформозависимого приложения, следует использовать [dotnet](dotnet.md) без команды.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="7fa9c-121">Например, для выполнения `myapp.dll` используйте:</span><span class="sxs-lookup"><span data-stu-id="7fa9c-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="7fa9c-122">Дополнительные сведения о драйвере `dotnet` см. в разделе [Средства интерфейса командной строки (CLI) .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="7fa9c-123">Для запуска приложения команда `dotnet run` разрешает зависимости приложения, выходящие за пределы общей среды выполнения, из кэша NuGet.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="7fa9c-124">Из-за использования кэшированных зависимостей не рекомендуется применять команду `dotnet run` для запуска приложений в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="7fa9c-125">Вместо этого [создайте развертывание](../deploying/index.md) с помощью команды [`dotnet publish`](dotnet-publish.md) и разверните опубликованные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

## <a name="options"></a><span data-ttu-id="7fa9c-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="7fa9c-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7fa9c-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7fa9c-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="7fa9c-128">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="7fa9c-129">Все аргументы после этого передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7fa9c-130">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-130">Defines the build configuration.</span></span> <span data-ttu-id="7fa9c-131">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7fa9c-132">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="7fa9c-133">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-133">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="7fa9c-134">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-134">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="7fa9c-135">Имя профиля запуска (при его наличии), который следует использовать при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-135">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="7fa9c-136">Профили запуска обычно определяются в файле *launchSettings.json* и, как правило, называются `Development`, `Staging` и `Production`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-136">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="7fa9c-137">Дополнительные сведения см. в разделе [Работа с несколькими средами](/aspnetcore/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-137">For more information, see [Working with multiple environments](/aspnetcore/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="7fa9c-138">Не выполняет сборку проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-138">Doesn't build the project before running.</span></span>

`--no-launch-profile`

<span data-ttu-id="7fa9c-139">Не пытается использовать файл *launchSettings.json* для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-139">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="7fa9c-140">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-140">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="7fa9c-141">Задает путь к запускаемому файлу проекта (имя папки или полный путь).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-141">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="7fa9c-142">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-142">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="7fa9c-143">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-143">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="7fa9c-144">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-144">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7fa9c-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7fa9c-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="7fa9c-146">Отделяет аргументы, предназначенные для `dotnet run`, от аргументов для выполняемого приложения.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-146">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="7fa9c-147">Все аргументы после этого передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-147">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7fa9c-148">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-148">Defines the build configuration.</span></span> <span data-ttu-id="7fa9c-149">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-149">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7fa9c-150">Выполняет сборку и запуск приложения с использованием указанной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-150">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="7fa9c-151">Эта платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-151">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="7fa9c-152">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-152">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="7fa9c-153">Указывает путь и имя файла проекта.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-153">Specifies the path and name of the project file.</span></span> <span data-ttu-id="7fa9c-154">(См. примечание.) Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-154">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="7fa9c-155">Используйте путь и имя файла проекта с параметром `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-155">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="7fa9c-156">Регрессия в интерфейсе командной строки не позволяет указать путь к папке в пакете SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="7fa9c-156">A regression in the CLI prevents providing a folder path with .NET Core 1.x SDK.</span></span> <span data-ttu-id="7fa9c-157">Дополнительные сведения об этой проблеме см. в разделе [dotnet run -p, не удается запустить проект (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="7fa9c-157">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="7fa9c-158">Примеры</span><span class="sxs-lookup"><span data-stu-id="7fa9c-158">Examples</span></span>

<span data-ttu-id="7fa9c-159">Выполнение проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="7fa9c-159">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="7fa9c-160">Выполнение указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="7fa9c-160">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="7fa9c-161">Выполнение проекта в текущем каталоге (аргумент `--help` в этом примере передается приложению, так как используется аргумент `--`):</span><span class="sxs-lookup"><span data-stu-id="7fa9c-161">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

