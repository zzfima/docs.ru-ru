---
title: Команда dotnet pack — CLI .NET Core
description: Команда dotnet pack создает пакеты NuGet для проекта .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 8c2569ec7598b21fe9b673176143d0e54b9eb065
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696823"
---
# <a name="dotnet-pack"></a><span data-ttu-id="d2351-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="d2351-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d2351-104">name</span><span class="sxs-lookup"><span data-stu-id="d2351-104">Name</span></span>

<span data-ttu-id="d2351-105">`dotnet pack` — упаковывает код в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="d2351-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2351-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d2351-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d2351-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d2351-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2351-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2351-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d2351-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="d2351-109">Description</span></span>

<span data-ttu-id="d2351-110">Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="d2351-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="d2351-111">Результат выполнения команды — пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="d2351-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="d2351-112">При наличии параметра `--include-symbols` создается другой пакет, содержащий отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="d2351-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="d2351-113">Зависимости NuGet упакованного проекта добавляются в файл *NUSPEC*, чтобы их можно было разрешить при установке пакета.</span><span class="sxs-lookup"><span data-stu-id="d2351-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="d2351-114">Межпроектные ссылки не упаковываются в проекте.</span><span class="sxs-lookup"><span data-stu-id="d2351-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="d2351-115">Сейчас при наличии межпроектных зависимостей требуется один пакет на каждый проект.</span><span class="sxs-lookup"><span data-stu-id="d2351-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="d2351-116">`dotnet pack` по умолчанию сначала выполняет сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="d2351-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="d2351-117">Чтобы избежать этого, передайте параметр `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="d2351-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="d2351-118">Этот вариант часто бывает полезен, например в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был собран недавно.</span><span class="sxs-lookup"><span data-stu-id="d2351-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="d2351-119">Может предоставлять свойства MSBuild команде `dotnet pack` для процесса упаковки.</span><span class="sxs-lookup"><span data-stu-id="d2351-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="d2351-120">Дополнительные сведения см. в разделах [Свойства метаданных NuGet](csproj.md#nuget-metadata-properties) и [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="d2351-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="d2351-121">В разделе [Примеры](#examples) показано, как использовать параметр MSBuild /p в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="d2351-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="d2351-122">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d2351-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d2351-123">Упаковываемый проект.</span><span class="sxs-lookup"><span data-stu-id="d2351-123">The project to pack.</span></span> <span data-ttu-id="d2351-124">Это путь к файлу [CSPROJ](csproj.md) или каталогу.</span><span class="sxs-lookup"><span data-stu-id="d2351-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="d2351-125">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d2351-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="d2351-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2351-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d2351-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d2351-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d2351-128">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="d2351-128">Defines the build configuration.</span></span> <span data-ttu-id="d2351-129">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d2351-129">The default value is `Debug`.</span></span>

`--force`

<span data-ttu-id="d2351-130">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="d2351-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d2351-131">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d2351-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="d2351-132">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d2351-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="d2351-133">Включает исходные файлы в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="d2351-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="d2351-134">Исходные файлы включены в папку `src` пакета `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="d2351-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="d2351-135">Создает символы `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="d2351-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="d2351-136">Не выполняет сборку проекта перед упаковкой.</span><span class="sxs-lookup"><span data-stu-id="d2351-136">Doesn't build the project before packing.</span></span> <span data-ttu-id="d2351-137">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="d2351-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="d2351-138">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="d2351-138">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="d2351-139">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="d2351-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2351-140">Собранные пакеты помещаются в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="d2351-140">Places the built packages in the directory specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d2351-141">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="d2351-141">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="d2351-142">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d2351-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="d2351-143">Задает флаг "подлежит обслуживанию" в пакете.</span><span class="sxs-lookup"><span data-stu-id="d2351-143">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="d2351-144">Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="d2351-144">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="d2351-145">Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.</span><span class="sxs-lookup"><span data-stu-id="d2351-145">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d2351-146">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d2351-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d2351-147">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2351-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2351-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2351-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d2351-149">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="d2351-149">Defines the build configuration.</span></span> <span data-ttu-id="d2351-150">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d2351-150">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="d2351-151">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d2351-151">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="d2351-152">Включает исходные файлы в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="d2351-152">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="d2351-153">Исходные файлы включены в папку `src` пакета `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="d2351-153">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="d2351-154">Создает символы `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="d2351-154">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="d2351-155">Не выполняет сборку проекта перед упаковкой.</span><span class="sxs-lookup"><span data-stu-id="d2351-155">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2351-156">Собранные пакеты помещаются в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="d2351-156">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="d2351-157">Задает флаг "подлежит обслуживанию" в пакете.</span><span class="sxs-lookup"><span data-stu-id="d2351-157">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="d2351-158">Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="d2351-158">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="d2351-159">Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.</span><span class="sxs-lookup"><span data-stu-id="d2351-159">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d2351-160">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d2351-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d2351-161">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2351-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d2351-162">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2351-162">Examples</span></span>

<span data-ttu-id="d2351-163">Упаковка проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d2351-163">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="d2351-164">Упаковка проекта `app1`:</span><span class="sxs-lookup"><span data-stu-id="d2351-164">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`

<span data-ttu-id="d2351-165">Упаковка проекта в текущем каталоге; полученные пакеты помещаются в папку `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="d2351-165">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="d2351-166">Упаковка проекта в текущем каталоге в папку `nupkgs` и пропуск этапа сборки:</span><span class="sxs-lookup"><span data-stu-id="d2351-166">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="d2351-167">Если суффикс версии пакета в файле *CSPROJ* настроен как `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`, упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса:</span><span class="sxs-lookup"><span data-stu-id="d2351-167">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="d2351-168">Устанавливает версию пакета в `2.1.0` с использованием свойства MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="d2351-168">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="d2351-169">Упакуйте проект для [требуемой версии .NET Framework](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="d2351-169">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`

<span data-ttu-id="d2351-170">Упакуйте проект и используйте определенную среду выполнения (Windows 10) для операции восстановления (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="d2351-170">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet pack --runtime win10-x64`