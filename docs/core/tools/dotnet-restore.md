---
title: Команда dotnet restore
description: Вы узнаете, как восстановить зависимости и связанные с проектом средства при помощи команды dotnet restore.
ms.date: 02/27/2020
ms.openlocfilehash: e74027ba70ddf6905a12f9691caeb0a406428ad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157028"
---
# <a name="dotnet-restore"></a><span data-ttu-id="5a120-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="5a120-103">dotnet restore</span></span>

<span data-ttu-id="5a120-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5a120-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5a120-105">name</span><span class="sxs-lookup"><span data-stu-id="5a120-105">Name</span></span>

<span data-ttu-id="5a120-106">`dotnet restore` — восстанавливает зависимости и средства проекта.</span><span class="sxs-lookup"><span data-stu-id="5a120-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5a120-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5a120-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel]
    [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime]
    [-s|--source] [-v|--verbosity] [--interactive]

dotnet restore [-h|--help]
```

## <a name="description"></a><span data-ttu-id="5a120-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5a120-108">Description</span></span>

<span data-ttu-id="5a120-109">Команда `dotnet restore` использует NuGet для восстановления зависимостей, а также связанных с проектом средств, которые указаны в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5a120-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="5a120-110">По умолчанию восстановление зависимостей и средств производится параллельно.</span><span class="sxs-lookup"><span data-stu-id="5a120-110">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

<span data-ttu-id="5a120-111">Для восстановления зависимостей NuGet требуются каналы, где находятся пакеты.</span><span class="sxs-lookup"><span data-stu-id="5a120-111">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="5a120-112">Каналы обычно предоставляются посредством файла конфигурации *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="5a120-112">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="5a120-113">Файл конфигурации по умолчанию предоставляется при установке пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5a120-113">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="5a120-114">Вы можете указать дополнительные веб-каналы, создав собственный файл *nuget.config* в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="5a120-114">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="5a120-115">Вы можете переопределить веб-каналы *nuget.config* с помощью параметра `-s`.</span><span class="sxs-lookup"><span data-stu-id="5a120-115">You can override the *nuget.config* feeds with the - `-s` option.</span></span>

<span data-ttu-id="5a120-116">Для зависимостей можно указать, куда помещаются восстанавливаемые пакеты во время операции восстановления, с помощью аргумента `--packages`.</span><span class="sxs-lookup"><span data-stu-id="5a120-116">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="5a120-117">Если значение не указано, используется кэш пакетов NuGet по умолчанию. Он находится в каталоге `.nuget/packages` в домашнем каталоге пользователя во всех операционных системах.</span><span class="sxs-lookup"><span data-stu-id="5a120-117">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="5a120-118">Например, */home/user1* на Linux или *C:\Users\user1* в Windows.</span><span class="sxs-lookup"><span data-stu-id="5a120-118">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="5a120-119">Для связанных с проектом средств `dotnet restore` сначала восстанавливает пакет, в котором упаковано средство, а затем — зависимости средства, указанные в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5a120-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="5a120-120">Различия nuget.config</span><span class="sxs-lookup"><span data-stu-id="5a120-120">nuget.config differences</span></span>

<span data-ttu-id="5a120-121">На поведение команды `dotnet restore` влияют параметры в файле *nuget.config*, если он существует.</span><span class="sxs-lookup"><span data-stu-id="5a120-121">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="5a120-122">Например, если установить параметр `globalPackagesFolder` в файле *nuget.config*, то восстановленные пакеты NuGet будут помещены в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="5a120-122">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="5a120-123">Для получения того же результата можно указать параметр `--packages` команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="5a120-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="5a120-124">Дополнительные сведения см. в [справочнике по файлу nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="5a120-124">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="5a120-125">Существует три конкретных параметра, которые `dotnet restore` игнорирует:</span><span class="sxs-lookup"><span data-stu-id="5a120-125">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="5a120-126">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="5a120-126">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="5a120-127">Перенаправления привязок не работают с элементами `<PackageReference>`, а .NET Core поддерживает только элементы `<PackageReference>` для пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="5a120-127">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="5a120-128">solution</span><span class="sxs-lookup"><span data-stu-id="5a120-128">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="5a120-129">Этот параметр относится только к Visual Studio и не применяется к .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5a120-129">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="5a120-130">.NET Core не использует файл `packages.config`. Вместо этого он использует элементы `<PackageReference>` для пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="5a120-130">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="5a120-131">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="5a120-131">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="5a120-132">Этот параметр не применяется, так как [NuGet пока не поддерживает кроссплатформенную проверку](https://github.com/NuGet/Home/issues/7939) доверенных пакетов.</span><span class="sxs-lookup"><span data-stu-id="5a120-132">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-restore"></a><span data-ttu-id="5a120-133">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="5a120-133">Implicit restore</span></span>

<span data-ttu-id="5a120-134">При необходимости команда `dotnet restore` выполняется неявно при выполнении следующих команд:</span><span class="sxs-lookup"><span data-stu-id="5a120-134">The `dotnet restore` command is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="5a120-135">В большинстве случаев использовать команду `dotnet restore` явным образом не требуется.</span><span class="sxs-lookup"><span data-stu-id="5a120-135">In most cases, you don't need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="5a120-136">Иногда неудобно запускать `dotnet restore` неявным образом.</span><span class="sxs-lookup"><span data-stu-id="5a120-136">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="5a120-137">Например, некоторые автоматизированные системы, такие как системы сборки, должны явно вызывать `dotnet restore`, чтобы контролировать процесс восстановления и, следовательно, отслеживать использование сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5a120-137">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="5a120-138">Чтобы избежать неявного выполнения команды `dotnet restore`, с любой из приведенных выше команд можно использовать флаг `--no-restore` для отключения неявного восстановления.</span><span class="sxs-lookup"><span data-stu-id="5a120-138">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="5a120-139">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5a120-139">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="5a120-140">Дополнительный путь к файлу проекта для восстановления.</span><span class="sxs-lookup"><span data-stu-id="5a120-140">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="5a120-141">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a120-141">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="5a120-142">Файл конфигурации NuGet (*nuget.config*), используемый для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="5a120-142">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="5a120-143">Отключает параллельное восстановление нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="5a120-143">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="5a120-144">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="5a120-144">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="5a120-145">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="5a120-145">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5a120-146">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="5a120-146">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="5a120-147">Предупреждение о сбоях источников выдается только при наличии пакетов, соответствующих требованию к версии.</span><span class="sxs-lookup"><span data-stu-id="5a120-147">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--no-cache`**

  <span data-ttu-id="5a120-148">Отключает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="5a120-148">Specifies to not cache packages and HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="5a120-149">При восстановлении проекта с перекрестными ссылками между проектами восстанавливает только корневой проект, но не ссылки.</span><span class="sxs-lookup"><span data-stu-id="5a120-149">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="5a120-150">Задает каталог для восстановленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="5a120-150">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="5a120-151">Задает среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="5a120-151">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="5a120-152">Это позволяет восстановить пакеты для сред выполнения, явно не указанных в теге `<RuntimeIdentifiers>` файла *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="5a120-152">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="5a120-153">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5a120-153">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="5a120-154">Чтобы указать несколько идентификаторов RID, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="5a120-154">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="5a120-155">Указывает источник пакета NuGet для использования во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="5a120-155">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="5a120-156">Этот параметр переопределяет все источники, указанные в файлах *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="5a120-156">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="5a120-157">Чтобы указать несколько источников, задайте этот параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="5a120-157">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--verbosity <LEVEL>`**

  <span data-ttu-id="5a120-158">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="5a120-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5a120-159">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5a120-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="5a120-160">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="5a120-160">Default value is `minimal`.</span></span>

- **`--interactive`**

  <span data-ttu-id="5a120-161">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="5a120-161">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="5a120-162">Начиная с .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="5a120-162">Since .NET Core 2.1.400.</span></span>

## <a name="examples"></a><span data-ttu-id="5a120-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="5a120-163">Examples</span></span>

- <span data-ttu-id="5a120-164">Восстановление зависимостей и средств для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="5a120-164">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="5a120-165">Восстановление зависимостей и средств для проекта `app1` по указанному пути:</span><span class="sxs-lookup"><span data-stu-id="5a120-165">Restore dependencies and tools for the `app1` project found in the   given path:</span></span>

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="5a120-166">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием пути к файлу, заданного в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="5a120-166">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="5a120-167">Восстановление зависимостей и средств для проекта в текущем каталоге с использованием двух путей к файлу, заданных в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="5a120-167">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="5a120-168">Восстановление зависимостей и средств для проекта в текущем каталоге с подробными выходными данными:</span><span class="sxs-lookup"><span data-stu-id="5a120-168">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
