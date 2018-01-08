---
title: "Команда dotnet build — CLI .NET Core"
description: "Команда dotnet build выполняет сборку проекта и всех его зависимостей."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 403dc2262e2aba29fc432581a4b325092cdfb25e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-build"></a><span data-ttu-id="3fee1-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="3fee1-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3fee1-104">name</span><span class="sxs-lookup"><span data-stu-id="3fee1-104">Name</span></span>

<span data-ttu-id="3fee1-105">`dotnet build` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="3fee1-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3fee1-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3fee1-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3fee1-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3fee1-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3fee1-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3fee1-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="3fee1-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="3fee1-109">Description</span></span>

<span data-ttu-id="3fee1-110">Команда `dotnet build` выполняет сборку проекта и его зависимостей в набор двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="3fee1-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="3fee1-111">Эти двоичные файлы содержат код проекта в виде файлов на промежуточном языке с расширением *DLL*, а также файлы символов для отладки с расширением *PDB*.</span><span class="sxs-lookup"><span data-stu-id="3fee1-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="3fee1-112">Создается JSON-файл зависимостей (*\*.deps.json*), содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="3fee1-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="3fee1-113">Создает файл *\*.runtimeconfig.json*, указывающий общую среду выполнения и ее версию для приложения.</span><span class="sxs-lookup"><span data-stu-id="3fee1-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="3fee1-114">Если проект имеет зависимости от сторонних компонентов, таких как библиотеки из NuGet, они разрешаются из кэша NuGet и недоступны в выходных данных сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="3fee1-115">Учитывая это, продукт `dotnet build` не готов к переносу на другой компьютер для выполнения.</span><span class="sxs-lookup"><span data-stu-id="3fee1-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="3fee1-116">Это отличается от поведения в .NET Framework, где сборка исполняемого проекта (приложения) создает выходные данные, которые можно запустить на любом компьютере с установленной платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3fee1-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="3fee1-117">Чтобы обеспечить аналогичное поведение в .NET Core, необходимо использовать команду [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="3fee1-118">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="3fee1-119">Для сборки нужен файл *project.assets.json*, содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="3fee1-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="3fee1-120">Он создается при выполнении команды [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="3fee1-121">Без файла ресурсов инструментарий не способен разрешать базовые сборки, что приводит к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="3fee1-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="3fee1-122">При использовании пакета SDK для .NET Core 1.x необходимо было явным образом выполнять команду `dotnet restore` перед выполнением `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-122">With .NET Core 1.x SDK, you needed to explicitily run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="3fee1-123">Начиная с версии SDK для .NET Core 2.0 команда `dotnet restore` выполняется автоматически при выполнении `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitily when you run `dotnet build`.</span></span> <span data-ttu-id="3fee1-124">Чтобы отключить неявное восстановление при выполнении команды сборки, можно передать параметр `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="3fee1-125">`dotnet build` использует MSBuild для сборки проекта, поддерживая при этом как параллельные, так и инкрементные сборки.</span><span class="sxs-lookup"><span data-stu-id="3fee1-125">`dotnet build` uses MSBuild to build the project; thus, it supports both parallel and incremental builds.</span></span> <span data-ttu-id="3fee1-126">Дополнительные сведения см. в разделе [Инкрементные сборки](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="3fee1-126">Refer to [Incremental Builds](/visualstudio/msbuild/incremental-builds) for more information.</span></span>

<span data-ttu-id="3fee1-127">Помимо своих параметров, команда `dotnet build` принимает и параметры MSBuild, например `/p` для задания свойств или `/l` для определения средства ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="3fee1-127">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `/p` for setting properties or `/l` to define a logger.</span></span> <span data-ttu-id="3fee1-128">Дополнительные сведения об этих параметрах см. в разделе [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="3fee1-128">Learn more about these options in the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> 

<span data-ttu-id="3fee1-129">То, является ли проект исполняемым, определяется свойством `<OutputType>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="3fee1-130">Следующий пример описывает проект, который создаст исполняемый код:</span><span class="sxs-lookup"><span data-stu-id="3fee1-130">The following example shows a project that will produce executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="3fee1-131">Чтобы создать библиотеку, опустите свойство `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-131">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="3fee1-132">Основное различие в выходных данных заключается в том, что библиотека DLL на промежуточном языке не содержит ни одной точки входа и ее нельзя выполнить.</span><span class="sxs-lookup"><span data-stu-id="3fee1-132">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span> 

## <a name="arguments"></a><span data-ttu-id="3fee1-133">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3fee1-133">Arguments</span></span>

`PROJECT`

<span data-ttu-id="3fee1-134">Файл проекта для сборки.</span><span class="sxs-lookup"><span data-stu-id="3fee1-134">The project file to build.</span></span> <span data-ttu-id="3fee1-135">Если файл проекта не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="3fee1-135">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="3fee1-136">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fee1-136">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="3fee1-137">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3fee1-137">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="3fee1-138">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="3fee1-138">Defines the build configuration.</span></span> <span data-ttu-id="3fee1-139">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-139">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="3fee1-140">Выполняет компиляцию для конкретной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-140">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="3fee1-141">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-141">The framework must be defined in the [project file](csproj.md).</span></span>

`--force`

 <span data-ttu-id="3fee1-142">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="3fee1-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="3fee1-143">Равносильно удалению файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="3fee1-143">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="3fee1-144">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="3fee1-144">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="3fee1-145">Межпроектные (P2P) ссылки игнорируются, и выполняется сборка только указанного корневого проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-145">Ignores project-to-project (P2P) references and only builds the root project specified to build.</span></span>

`--no-incremental`

<span data-ttu-id="3fee1-146">Помечает сборку как небезопасную для добавочной сборки.</span><span class="sxs-lookup"><span data-stu-id="3fee1-146">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="3fee1-147">Это приводит к отключению инкрементной компиляции и принудительной полной перестройке схемы зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-147">This turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-restore`

<span data-ttu-id="3fee1-148">Во время сборки не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="3fee1-148">Doesn't perform an implicit restore during build.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3fee1-149">Каталог, в который будут помещаться собранные двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="3fee1-149">Directory in which to place the built binaries.</span></span> <span data-ttu-id="3fee1-150">При указании этого параметра также необходимо определить `--framework`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-150">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="3fee1-151">Указывает целевую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="3fee1-151">Specifies the target runtime.</span></span> <span data-ttu-id="3fee1-152">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="3fee1-153">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="3fee1-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3fee1-154">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="3fee1-155">Определяет суффикс версии для звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-155">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="3fee1-156">Формат соответствует рекомендациям в отношении версий NuGet.</span><span class="sxs-lookup"><span data-stu-id="3fee1-156">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3fee1-157">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3fee1-157">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="3fee1-158">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="3fee1-158">Defines the build configuration.</span></span> <span data-ttu-id="3fee1-159">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-159">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="3fee1-160">Выполняет компиляцию для конкретной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-160">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="3fee1-161">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-161">The framework must be defined in the [project file](csproj.md).</span></span>

`-h|--help`

<span data-ttu-id="3fee1-162">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="3fee1-162">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="3fee1-163">Межпроектные (P2P) ссылки игнорируются, и выполняется сборка только указанного корневого проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-163">Ignores project-to-project (P2P) references and only builds the root project specified to build.</span></span>

`--no-incremental`

<span data-ttu-id="3fee1-164">Помечает сборку как небезопасную для добавочной сборки.</span><span class="sxs-lookup"><span data-stu-id="3fee1-164">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="3fee1-165">Это приводит к отключению инкрементной компиляции и принудительной полной перестройке схемы зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-165">This turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3fee1-166">Каталог, в который будут помещаться собранные двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="3fee1-166">Directory in which to place the built binaries.</span></span> <span data-ttu-id="3fee1-167">При указании этого параметра также необходимо определить `--framework`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-167">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="3fee1-168">Указывает целевую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="3fee1-168">Specifies the target runtime.</span></span> <span data-ttu-id="3fee1-169">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="3fee1-169">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="3fee1-170">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="3fee1-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3fee1-171">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fee1-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="3fee1-172">Определяет суффикс версии для звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="3fee1-172">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="3fee1-173">Формат соответствует рекомендациям в отношении версий NuGet.</span><span class="sxs-lookup"><span data-stu-id="3fee1-173">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="3fee1-174">Примеры</span><span class="sxs-lookup"><span data-stu-id="3fee1-174">Examples</span></span>

<span data-ttu-id="3fee1-175">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="3fee1-175">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="3fee1-176">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="3fee1-176">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="3fee1-177">Сборка проекта и его зависимостей для определенной среды выполнения (в этом примере это Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="3fee1-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`