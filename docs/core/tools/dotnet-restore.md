---
title: Команда dotnet restore
description: Вы узнаете, как восстановить зависимости и связанные с проектом средства при помощи команды dotnet restore.
ms.date: 05/29/2018
ms.openlocfilehash: 3ddb9f679cfcab972483a4cb53ffe2b075867614
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613974"
---
# <a name="dotnet-restore"></a><span data-ttu-id="552f1-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="552f1-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="552f1-104">name</span><span class="sxs-lookup"><span data-stu-id="552f1-104">Name</span></span>

<span data-ttu-id="552f1-105">`dotnet restore` — восстанавливает зависимости и средства проекта.</span><span class="sxs-lookup"><span data-stu-id="552f1-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="552f1-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="552f1-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="552f1-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="552f1-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="552f1-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="552f1-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="552f1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="552f1-109">Description</span></span>

<span data-ttu-id="552f1-110">Команда `dotnet restore` использует NuGet для восстановления зависимостей, а также связанных с проектом средств, которые указаны в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="552f1-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="552f1-111">По умолчанию восстановление зависимостей и средств производится параллельно.</span><span class="sxs-lookup"><span data-stu-id="552f1-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="552f1-112">Для восстановления зависимостей NuGet требуются каналы, где находятся пакеты.</span><span class="sxs-lookup"><span data-stu-id="552f1-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="552f1-113">Каналы обычно предоставляются посредством файла конфигурации *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="552f1-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="552f1-114">Файл конфигурации по умолчанию предоставляется при установке средств CLI.</span><span class="sxs-lookup"><span data-stu-id="552f1-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="552f1-115">Вы можете указать дополнительные веб-каналы, создав собственный файл *NuGet.config* в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="552f1-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="552f1-116">Можно также указать дополнительные веб-каналы на вызов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="552f1-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="552f1-117">Для зависимостей можно указать, куда помещаются восстанавливаемые пакеты во время операции восстановления, с помощью аргумента `--packages`.</span><span class="sxs-lookup"><span data-stu-id="552f1-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="552f1-118">Если значение не указано, используется кэш пакетов NuGet по умолчанию. Он находится в каталоге `.nuget/packages` в домашнем каталоге пользователя во всех операционных системах.</span><span class="sxs-lookup"><span data-stu-id="552f1-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="552f1-119">Например, */home/user1* на Linux или *C:\Users\user1* в Windows.</span><span class="sxs-lookup"><span data-stu-id="552f1-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="552f1-120">Для связанных с проектом средств `dotnet restore` сначала восстанавливает пакет, в котором упаковано средство, а затем — зависимости средства, указанные в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="552f1-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="552f1-121">На поведение команды `dotnet restore` влияют некоторые из параметров в файле *Nuget.Config*, если он существует.</span><span class="sxs-lookup"><span data-stu-id="552f1-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="552f1-122">Например, если установить параметр `globalPackagesFolder` в файле *NuGet.Config*, то восстановленные пакеты NuGet будут помещены в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="552f1-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="552f1-123">Для получения того же результата можно указать параметр `--packages` команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="552f1-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="552f1-124">Дополнительные сведения см. в [справочнике по файлу NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="552f1-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="552f1-125">Неявное выполнение `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="552f1-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="552f1-126">Начиная с версии .NET Core 2.0, команда `dotnet restore` выполняется неявно при выполнении следующих команд:</span><span class="sxs-lookup"><span data-stu-id="552f1-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="552f1-127">В большинстве случаев использовать команду `dotnet restore` явным образом не требуется.</span><span class="sxs-lookup"><span data-stu-id="552f1-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="552f1-128">Иногда неудобно запускать `dotnet restore` неявным образом.</span><span class="sxs-lookup"><span data-stu-id="552f1-128">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="552f1-129">Например, некоторые автоматизированные системы, такие как системы сборки, должны явно вызывать `dotnet restore`, чтобы контролировать процесс восстановления и, следовательно, отслеживать использование сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="552f1-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="552f1-130">Чтобы избежать неявного выполнения команды `dotnet restore`, с любой из приведенных выше команд можно использовать флаг `--no-restore` для отключения неявного восстановления.</span><span class="sxs-lookup"><span data-stu-id="552f1-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="552f1-131">Аргументы</span><span class="sxs-lookup"><span data-stu-id="552f1-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="552f1-132">Дополнительный путь к файлу проекта для восстановления.</span><span class="sxs-lookup"><span data-stu-id="552f1-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="552f1-133">Параметры</span><span class="sxs-lookup"><span data-stu-id="552f1-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="552f1-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="552f1-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="552f1-135">Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="552f1-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="552f1-136">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="552f1-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="552f1-137">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="552f1-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="552f1-138">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="552f1-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="552f1-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="552f1-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="552f1-140">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="552f1-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="552f1-141">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="552f1-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="552f1-142">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="552f1-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="552f1-143">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="552f1-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="552f1-144">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="552f1-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="552f1-145">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="552f1-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="552f1-146">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="552f1-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="552f1-147">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="552f1-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="552f1-148">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="552f1-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="552f1-149">Этот параметр переопределяет все источники, указанные в файлах *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="552f1-149">This setting overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="552f1-150">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="552f1-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="552f1-151">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="552f1-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="552f1-152">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="552f1-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--interactive`

<span data-ttu-id="552f1-153">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="552f1-153">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="552f1-154">Начиная с .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="552f1-154">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="552f1-155">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="552f1-155">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="552f1-156">Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="552f1-156">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="552f1-157">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="552f1-157">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="552f1-158">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="552f1-158">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="552f1-159">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="552f1-159">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="552f1-160">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="552f1-160">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="552f1-161">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="552f1-161">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="552f1-162">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="552f1-162">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="552f1-163">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="552f1-163">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="552f1-164">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="552f1-164">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="552f1-165">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="552f1-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="552f1-166">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="552f1-166">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="552f1-167">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="552f1-167">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="552f1-168">Переопределяет все источники, указанные в файлах *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="552f1-168">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="552f1-169">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="552f1-169">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="552f1-170">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="552f1-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="552f1-171">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="552f1-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="552f1-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="552f1-172">Examples</span></span>

<span data-ttu-id="552f1-173">Восстановление зависимостей и средств для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="552f1-173">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="552f1-174">Восстановление зависимостей и средств для проекта `app1` по указанному пути:</span><span class="sxs-lookup"><span data-stu-id="552f1-174">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="552f1-175">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием пути к файлу, заданного в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="552f1-175">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="552f1-176">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием двух путей к файлу, заданных в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="552f1-176">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="552f1-177">Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных:</span><span class="sxs-lookup"><span data-stu-id="552f1-177">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
