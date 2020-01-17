---
title: Команда dotnet restore
description: Вы узнаете, как восстановить зависимости и связанные с проектом средства при помощи команды dotnet restore.
ms.date: 05/29/2018
ms.openlocfilehash: 82dd85e340a4cb520f781d977b0798b0f532a088
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75340438"
---
# <a name="dotnet-restore"></a><span data-ttu-id="03445-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="03445-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="03445-104">name</span><span class="sxs-lookup"><span data-stu-id="03445-104">Name</span></span>

<span data-ttu-id="03445-105">`dotnet restore` — восстанавливает зависимости и средства проекта.</span><span class="sxs-lookup"><span data-stu-id="03445-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="03445-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="03445-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="03445-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="03445-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="03445-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="03445-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="03445-109">Описание</span><span class="sxs-lookup"><span data-stu-id="03445-109">Description</span></span>

<span data-ttu-id="03445-110">Команда `dotnet restore` использует NuGet для восстановления зависимостей, а также связанных с проектом средств, которые указаны в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="03445-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="03445-111">По умолчанию восстановление зависимостей и средств производится параллельно.</span><span class="sxs-lookup"><span data-stu-id="03445-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="03445-112">Для восстановления зависимостей NuGet требуются каналы, где находятся пакеты.</span><span class="sxs-lookup"><span data-stu-id="03445-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="03445-113">Каналы обычно предоставляются посредством файла конфигурации *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="03445-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="03445-114">Файл конфигурации по умолчанию предоставляется при установке средств CLI.</span><span class="sxs-lookup"><span data-stu-id="03445-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="03445-115">Вы можете указать дополнительные веб-каналы, создав собственный файл *nuget.config* в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="03445-115">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="03445-116">Вы можете переопределить веб-каналы *nuget.config* с помощью свойства `-s`.</span><span class="sxs-lookup"><span data-stu-id="03445-116">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="03445-117">Для зависимостей можно указать, куда помещаются восстанавливаемые пакеты во время операции восстановления, с помощью аргумента `--packages`.</span><span class="sxs-lookup"><span data-stu-id="03445-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="03445-118">Если значение не указано, используется кэш пакетов NuGet по умолчанию. Он находится в каталоге `.nuget/packages` в домашнем каталоге пользователя во всех операционных системах.</span><span class="sxs-lookup"><span data-stu-id="03445-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="03445-119">Например, */home/user1* на Linux или *C:\Users\user1* в Windows.</span><span class="sxs-lookup"><span data-stu-id="03445-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="03445-120">Для связанных с проектом средств `dotnet restore` сначала восстанавливает пакет, в котором упаковано средство, а затем — зависимости средства, указанные в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="03445-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="03445-121">Различия nuget.config</span><span class="sxs-lookup"><span data-stu-id="03445-121">nuget.config differences</span></span>

<span data-ttu-id="03445-122">На поведение команды `dotnet restore` влияют параметры в файле *nuget.config*, если он существует.</span><span class="sxs-lookup"><span data-stu-id="03445-122">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="03445-123">Например, если установить параметр `globalPackagesFolder` в файле *nuget.config*, то восстановленные пакеты NuGet будут помещены в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="03445-123">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="03445-124">Для получения того же результата можно указать параметр `--packages` команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="03445-124">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="03445-125">Дополнительные сведения см. в [справочнике по файлу nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="03445-125">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="03445-126">Существует три конкретных параметра, которые `dotnet restore` игнорирует:</span><span class="sxs-lookup"><span data-stu-id="03445-126">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="03445-127">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="03445-127">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="03445-128">Перенаправления привязок не работают с элементами `<PackageReference>`, а .NET Core поддерживает только элементы `<PackageReference>` для пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="03445-128">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="03445-129">solution</span><span class="sxs-lookup"><span data-stu-id="03445-129">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="03445-130">Этот параметр относится только к Visual Studio и не применяется к .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03445-130">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="03445-131">.NET Core не использует файл `packages.config`. Вместо этого он использует элементы `<PackageReference>` для пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="03445-131">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="03445-132">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="03445-132">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="03445-133">Этот параметр не применяется, так как [NuGet пока не поддерживает кроссплатформенную проверку](https://github.com/NuGet/Home/issues/7939) доверенных пакетов.</span><span class="sxs-lookup"><span data-stu-id="03445-133">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="03445-134">Неявное выполнение `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="03445-134">Implicit `dotnet restore`</span></span>

<span data-ttu-id="03445-135">Начиная с версии .NET Core 2.0, команда `dotnet restore` выполняется неявно при выполнении следующих команд:</span><span class="sxs-lookup"><span data-stu-id="03445-135">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="03445-136">В большинстве случаев использовать команду `dotnet restore` явным образом не требуется.</span><span class="sxs-lookup"><span data-stu-id="03445-136">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="03445-137">Иногда неудобно запускать `dotnet restore` неявным образом.</span><span class="sxs-lookup"><span data-stu-id="03445-137">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="03445-138">Например, некоторые автоматизированные системы, такие как системы сборки, должны явно вызывать `dotnet restore`, чтобы контролировать процесс восстановления и, следовательно, отслеживать использование сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="03445-138">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="03445-139">Чтобы избежать неявного выполнения команды `dotnet restore`, с любой из приведенных выше команд можно использовать флаг `--no-restore` для отключения неявного восстановления.</span><span class="sxs-lookup"><span data-stu-id="03445-139">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="03445-140">Аргументы</span><span class="sxs-lookup"><span data-stu-id="03445-140">Arguments</span></span>

`ROOT`

<span data-ttu-id="03445-141">Дополнительный путь к файлу проекта для восстановления.</span><span class="sxs-lookup"><span data-stu-id="03445-141">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="03445-142">Параметры</span><span class="sxs-lookup"><span data-stu-id="03445-142">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="03445-143">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="03445-143">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="03445-144">Файл конфигурации NuGet (*nuget.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="03445-144">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="03445-145">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="03445-145">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="03445-146">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="03445-146">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="03445-147">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="03445-147">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="03445-148">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="03445-148">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="03445-149">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="03445-149">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="03445-150">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="03445-150">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="03445-151">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="03445-151">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="03445-152">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="03445-152">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="03445-153">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="03445-153">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="03445-154">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="03445-154">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="03445-155">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="03445-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="03445-156">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="03445-156">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="03445-157">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="03445-157">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="03445-158">Этот параметр переопределяет все источники, указанные в файлах *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="03445-158">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="03445-159">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="03445-159">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="03445-160">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="03445-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="03445-161">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="03445-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="03445-162">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="03445-162">Default value is `minimal`.</span></span>

`--interactive`

<span data-ttu-id="03445-163">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="03445-163">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="03445-164">Начиная с .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="03445-164">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="03445-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="03445-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="03445-166">Файл конфигурации NuGet (*nuget.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="03445-166">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="03445-167">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="03445-167">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="03445-168">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="03445-168">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="03445-169">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="03445-169">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="03445-170">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="03445-170">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="03445-171">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="03445-171">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="03445-172">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="03445-172">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="03445-173">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="03445-173">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="03445-174">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="03445-174">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="03445-175">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="03445-175">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="03445-176">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="03445-176">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="03445-177">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="03445-177">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="03445-178">Это переопределяет все источники, указанные в файлах *nuget.config*, фактически файл *nuget.config* считывается так, как если бы элемент `<packageSource>` отсутствовал.</span><span class="sxs-lookup"><span data-stu-id="03445-178">This overrides all of the sources specified in the *nuget.config* files, effectively reading the *nuget.config* file as if the `<packageSource>` element was not there.</span></span> <span data-ttu-id="03445-179">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="03445-179">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="03445-180">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="03445-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="03445-181">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="03445-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="03445-182">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="03445-182">The default is `minimal`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="03445-183">Примеры</span><span class="sxs-lookup"><span data-stu-id="03445-183">Examples</span></span>

<span data-ttu-id="03445-184">Восстановление зависимостей и средств для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="03445-184">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="03445-185">Восстановление зависимостей и средств для проекта `app1` по указанному пути:</span><span class="sxs-lookup"><span data-stu-id="03445-185">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="03445-186">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием пути к файлу, заданного в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="03445-186">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="03445-187">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием двух путей к файлу, заданных в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="03445-187">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="03445-188">Восстановление зависимостей и средств для проекта в текущем каталоге с подробными выходными данными:</span><span class="sxs-lookup"><span data-stu-id="03445-188">Restore dependencies and tools for the project in the current directory showing detailed output:</span></span>

`dotnet restore --verbosity detailed`
