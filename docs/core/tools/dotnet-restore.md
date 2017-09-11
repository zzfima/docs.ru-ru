---
title: "Команда dotnet restore — CLI .NET Core"
description: "Вы узнаете, как восстановить зависимости и связанные с проектом средства при помощи команды dotnet restore."
keywords: "dotnet-restore, CLI, команда CLI, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: e9f122c71330f93e02157e36f9fbbc92a0dddfce
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-restore"></a><span data-ttu-id="5ccd5-104">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="5ccd5-104">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5ccd5-105">Имя</span><span class="sxs-lookup"><span data-stu-id="5ccd5-105">Name</span></span>

<span data-ttu-id="5ccd5-106">`dotnet restore` — восстанавливает зависимости и средства проекта.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5ccd5-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5ccd5-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5ccd5-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5ccd5-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5ccd5-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5ccd5-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="5ccd5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5ccd5-110">Description</span></span>

<span data-ttu-id="5ccd5-111">Команда `dotnet restore` использует NuGet для восстановления зависимостей, а также связанных с проектом средств, которые указаны в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-111">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="5ccd5-112">По умолчанию восстановление зависимостей и средств производится параллельно.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-112">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

<span data-ttu-id="5ccd5-113">Для восстановления зависимостей NuGet требуются каналы, где находятся пакеты.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-113">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="5ccd5-114">Каналы обычно предоставляются посредством файла конфигурации *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-114">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="5ccd5-115">Файл конфигурации по умолчанию предоставляется при установке средств CLI.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-115">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="5ccd5-116">Вы можете указать дополнительные веб-каналы, создав собственный файл *NuGet.config* в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-116">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="5ccd5-117">Можно также указать дополнительные веб-каналы на вызов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-117">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="5ccd5-118">Для зависимостей можно указать, куда помещаются восстанавливаемые пакеты во время операции восстановления, с помощью аргумента `--packages`.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-118">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="5ccd5-119">Если значение не указано, используется кэш пакетов NuGet по умолчанию. Он находится в каталоге `.nuget/packages` в домашнем каталоге пользователя во всех операционных системах (например, */home/user1* в Linux или *C:\Users\user1* в Windows).</span><span class="sxs-lookup"><span data-stu-id="5ccd5-119">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="5ccd5-120">Для связанных с проектом средств `dotnet restore` сначала восстанавливает пакет, в котором упаковано средство, а затем — зависимости средства, указанные в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="5ccd5-121">На поведение команды `dotnet restore` влияют некоторые из параметров в файле *Nuget.Config*, если он существует.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="5ccd5-122">Например, если установить параметр `globalPackagesFolder` в файле *NuGet.Config*, то восстановленные пакеты NuGet будут помещены в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="5ccd5-123">Для получения того же результата можно указать параметр `--packages` команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="5ccd5-124">Дополнительные сведения см. в [справочнике по файлу NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="5ccd5-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="arguments"></a><span data-ttu-id="5ccd5-125">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5ccd5-125">Arguments</span></span>

`ROOT`

<span data-ttu-id="5ccd5-126">Дополнительный путь к файлу проекта для восстановления.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-126">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="5ccd5-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ccd5-127">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5ccd5-128">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5ccd5-128">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="5ccd5-129">Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-129">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="5ccd5-130">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-130">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="5ccd5-131">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="5ccd5-132">Равносильно удалению файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-132">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="5ccd5-133">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-133">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="5ccd5-134">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-134">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="5ccd5-135">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-135">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="5ccd5-136">Восстанавливая проект с перекрестными ссылками между проектами, не восстанавливайте ссылки, — только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-136">When restoring a project with project-to-project (P2P) references, restore the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="5ccd5-137">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-137">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="5ccd5-138">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-138">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="5ccd5-139">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-139">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="5ccd5-140">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5ccd5-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="5ccd5-141">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-141">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="5ccd5-142">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-142">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="5ccd5-143">Переопределяет все источники, указанные в файлах *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-143">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="5ccd5-144">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-144">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="5ccd5-145">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5ccd5-146">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5ccd5-147">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5ccd5-147">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="5ccd5-148">Файл конфигурации NuGet (*NuGet.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-148">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="5ccd5-149">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-149">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="5ccd5-150">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-150">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="5ccd5-151">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-151">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="5ccd5-152">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-152">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="5ccd5-153">Восстанавливая проект с перекрестными ссылками между проектами, не восстанавливайте ссылки, — только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-153">When restoring a project with project-to-project (P2P) references, restore the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="5ccd5-154">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-154">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="5ccd5-155">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-155">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="5ccd5-156">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-156">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="5ccd5-157">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5ccd5-157">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="5ccd5-158">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-158">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="5ccd5-159">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-159">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="5ccd5-160">Переопределяет все источники, указанные в файлах *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-160">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="5ccd5-161">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-161">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="5ccd5-162">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5ccd5-163">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5ccd5-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="5ccd5-164">Примеры</span><span class="sxs-lookup"><span data-stu-id="5ccd5-164">Examples</span></span>

<span data-ttu-id="5ccd5-165">Восстановление зависимостей и средств для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="5ccd5-165">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="5ccd5-166">Восстановление зависимостей и средств для проекта `app1` по указанному пути:</span><span class="sxs-lookup"><span data-stu-id="5ccd5-166">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="5ccd5-167">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием пути к файлу, заданного в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="5ccd5-167">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="5ccd5-168">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием двух путей к файлу, заданных в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="5ccd5-168">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="5ccd5-169">Восстановление зависимостей и средств для проекта в текущем каталоге с выводом минимального объема выходных данных:</span><span class="sxs-lookup"><span data-stu-id="5ccd5-169">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
