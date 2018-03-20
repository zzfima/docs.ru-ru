---
title: "Команда dotnet restore — CLI .NET Core"
description: "Вы узнаете, как восстановить зависимости и связанные с проектом средства при помощи команды dotnet restore."
keywords: "dotnet-restore, CLI, команда CLI, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 50e8d5c335386c41e36a490263a4f4ebd2bd39ba
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="dotnet-restore"></a><span data-ttu-id="d9e96-104">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="d9e96-104">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d9e96-105">name</span><span class="sxs-lookup"><span data-stu-id="d9e96-105">Name</span></span>

<span data-ttu-id="d9e96-106">`dotnet restore` — восстанавливает зависимости и средства проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e96-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d9e96-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d9e96-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d9e96-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d9e96-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d9e96-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d9e96-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="d9e96-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="d9e96-110">Description</span></span>

<span data-ttu-id="d9e96-111">Команда `dotnet restore` использует NuGet для восстановления зависимостей, а также связанных с проектом средств, которые указаны в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e96-111">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="d9e96-112">По умолчанию восстановление зависимостей и средств производится параллельно.</span><span class="sxs-lookup"><span data-stu-id="d9e96-112">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="d9e96-113">Для восстановления зависимостей NuGet требуются каналы, где находятся пакеты.</span><span class="sxs-lookup"><span data-stu-id="d9e96-113">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="d9e96-114">Каналы обычно предоставляются посредством файла конфигурации *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="d9e96-114">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="d9e96-115">Файл конфигурации по умолчанию предоставляется при установке средств CLI.</span><span class="sxs-lookup"><span data-stu-id="d9e96-115">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="d9e96-116">Вы можете указать дополнительные веб-каналы, создав собственный файл *NuGet.config* в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e96-116">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="d9e96-117">Можно также указать дополнительные веб-каналы на вызов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d9e96-117">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="d9e96-118">Для зависимостей можно указать, куда помещаются восстанавливаемые пакеты во время операции восстановления, с помощью аргумента `--packages`.</span><span class="sxs-lookup"><span data-stu-id="d9e96-118">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="d9e96-119">Если значение не указано, используется кэш пакетов NuGet по умолчанию. Он находится в каталоге `.nuget/packages` в домашнем каталоге пользователя во всех операционных системах (например, */home/user1* в Linux или *C:\Users\user1* в Windows).</span><span class="sxs-lookup"><span data-stu-id="d9e96-119">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="d9e96-120">Для связанных с проектом средств `dotnet restore` сначала восстанавливает пакет, в котором упаковано средство, а затем — зависимости средства, указанные в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e96-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="d9e96-121">На поведение команды `dotnet restore` влияют некоторые из параметров в файле *Nuget.Config*, если он существует.</span><span class="sxs-lookup"><span data-stu-id="d9e96-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="d9e96-122">Например, если установить параметр `globalPackagesFolder` в файле *NuGet.Config*, то восстановленные пакеты NuGet будут помещены в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="d9e96-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="d9e96-123">Для получения того же результата можно указать параметр `--packages` команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="d9e96-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="d9e96-124">Дополнительные сведения см. в [справочнике по файлу NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="d9e96-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="d9e96-125">Неявное выполнение `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="d9e96-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="d9e96-126">Начиная с версии .NET Core 2.0, команда `dotnet restore` выполняется неявно при выполнении следующих команд:</span><span class="sxs-lookup"><span data-stu-id="d9e96-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="d9e96-127">В большинстве случаев использовать команду `dotnet restore` явным образом не требуется.</span><span class="sxs-lookup"><span data-stu-id="d9e96-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span> 

<span data-ttu-id="d9e96-128">В некоторых случаях выполнять команду `dotnet restore` явным образом неудобно.</span><span class="sxs-lookup"><span data-stu-id="d9e96-128">In some cases, it is inconvenient for `dotnet restore` to run implicitly.</span></span> <span data-ttu-id="d9e96-129">Например, некоторые автоматизированные системы, такие как системы сборки, должны явно вызывать `dotnet restore`, чтобы контролировать процесс восстановления и, следовательно, отслеживать использование сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="d9e96-130">Чтобы избежать неявного выполнения команды `dotnet restore`, с любой из приведенных выше команд можно использовать параметр `--no-restore` для отключения неявного восстановления.</span><span class="sxs-lookup"><span data-stu-id="d9e96-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` switch with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="d9e96-131">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d9e96-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="d9e96-132">Дополнительный путь к файлу проекта для восстановления.</span><span class="sxs-lookup"><span data-stu-id="d9e96-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="d9e96-133">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9e96-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d9e96-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d9e96-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="d9e96-135">Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="d9e96-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="d9e96-136">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="d9e96-137">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="d9e96-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d9e96-138">Равносильно удалению файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d9e96-138">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="d9e96-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d9e96-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="d9e96-140">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="d9e96-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="d9e96-141">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="d9e96-142">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="d9e96-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="d9e96-143">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d9e96-144">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="d9e96-145">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="d9e96-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="d9e96-146">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d9e96-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d9e96-147">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="d9e96-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d9e96-148">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="d9e96-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="d9e96-149">Переопределяет все источники, указанные в файлах *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="d9e96-149">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="d9e96-150">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="d9e96-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="d9e96-151">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d9e96-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d9e96-152">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d9e96-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d9e96-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d9e96-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="d9e96-154">Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="d9e96-154">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="d9e96-155">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-155">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="d9e96-156">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d9e96-156">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="d9e96-157">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="d9e96-157">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="d9e96-158">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-158">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="d9e96-159">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="d9e96-159">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="d9e96-160">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-160">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d9e96-161">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9e96-161">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="d9e96-162">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="d9e96-162">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="d9e96-163">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d9e96-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d9e96-164">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="d9e96-164">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d9e96-165">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="d9e96-165">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="d9e96-166">Переопределяет все источники, указанные в файлах *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="d9e96-166">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="d9e96-167">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="d9e96-167">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="d9e96-168">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d9e96-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d9e96-169">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d9e96-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="d9e96-170">Примеры</span><span class="sxs-lookup"><span data-stu-id="d9e96-170">Examples</span></span>

<span data-ttu-id="d9e96-171">Восстановление зависимостей и средств для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d9e96-171">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="d9e96-172">Восстановление зависимостей и средств для проекта `app1` по указанному пути:</span><span class="sxs-lookup"><span data-stu-id="d9e96-172">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="d9e96-173">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием пути к файлу, заданного в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="d9e96-173">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="d9e96-174">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием двух путей к файлу, заданных в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="d9e96-174">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="d9e96-175">Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных:</span><span class="sxs-lookup"><span data-stu-id="d9e96-175">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
