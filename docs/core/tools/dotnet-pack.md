---
title: "Команда dotnet pack — CLI .NET Core"
description: "Команда dotnet pack создает пакеты NuGet для проекта .NET Core."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 8594c863d67baf0237b63e61f28ca9ee315eeddf
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-pack"></a><span data-ttu-id="93182-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="93182-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="93182-104">Имя</span><span class="sxs-lookup"><span data-stu-id="93182-104">Name</span></span>

<span data-ttu-id="93182-105">`dotnet pack` — упаковывает код в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="93182-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="93182-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="93182-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="93182-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="93182-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies] [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="93182-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="93182-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="93182-109">Описание</span><span class="sxs-lookup"><span data-stu-id="93182-109">Description</span></span>

<span data-ttu-id="93182-110">Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="93182-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="93182-111">Результат выполнения команды — пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="93182-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="93182-112">При наличии параметра `--include-symbols` создается другой пакет, содержащий отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="93182-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="93182-113">Зависимости NuGet упакованного проекта добавляются в файл *NUSPEC*, чтобы их можно было разрешить при установке пакета.</span><span class="sxs-lookup"><span data-stu-id="93182-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="93182-114">Межпроектные ссылки не упаковываются в проекте.</span><span class="sxs-lookup"><span data-stu-id="93182-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="93182-115">Сейчас при наличии межпроектных зависимостей требуется один пакет на каждый проект.</span><span class="sxs-lookup"><span data-stu-id="93182-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="93182-116">`dotnet pack` по умолчанию сначала выполняет сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="93182-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="93182-117">Чтобы избежать этого, передайте параметр `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="93182-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="93182-118">Это часто бывает полезно, например, в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был собран недавно.</span><span class="sxs-lookup"><span data-stu-id="93182-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="93182-119">Может предоставлять свойства MSBuild команде `dotnet pack` для процесса упаковки.</span><span class="sxs-lookup"><span data-stu-id="93182-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="93182-120">Дополнительные сведения см. в разделах [Свойства метаданных NuGet](csproj.md#nuget-metadata-properties) и [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="93182-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="arguments"></a><span data-ttu-id="93182-121">Аргументы</span><span class="sxs-lookup"><span data-stu-id="93182-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="93182-122">Упаковываемый проект.</span><span class="sxs-lookup"><span data-stu-id="93182-122">The project to pack.</span></span> <span data-ttu-id="93182-123">Это путь к файлу [CSPROJ](csproj.md) или каталогу.</span><span class="sxs-lookup"><span data-stu-id="93182-123">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="93182-124">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="93182-124">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="93182-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="93182-125">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="93182-126">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="93182-126">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="93182-127">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="93182-127">Defines the build configuration.</span></span> <span data-ttu-id="93182-128">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="93182-128">The default value is `Debug`.</span></span>

<span data-ttu-id="93182-129">`--force` — принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="93182-129">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="93182-130">Равносильно удалению файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="93182-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="93182-131">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="93182-131">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="93182-132">Включает исходные файлы в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="93182-132">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="93182-133">Исходные файлы включены в папку `src` пакета `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="93182-133">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="93182-134">Создает символы `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="93182-134">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="93182-135">Не выполняет сборку проекта перед упаковкой.</span><span class="sxs-lookup"><span data-stu-id="93182-135">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="93182-136">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="93182-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="93182-137">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="93182-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="93182-138">Собранные пакеты помещаются в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="93182-138">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="93182-139">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="93182-139">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="93182-140">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="93182-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="93182-141">Задает флаг "подлежит обслуживанию" в пакете.</span><span class="sxs-lookup"><span data-stu-id="93182-141">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="93182-142">Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="93182-142">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="93182-143">Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.</span><span class="sxs-lookup"><span data-stu-id="93182-143">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="93182-144">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="93182-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="93182-145">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="93182-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="93182-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="93182-146">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="93182-147">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="93182-147">Defines the build configuration.</span></span> <span data-ttu-id="93182-148">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="93182-148">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="93182-149">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="93182-149">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="93182-150">Включает исходные файлы в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="93182-150">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="93182-151">Исходные файлы включены в папку `src` пакета `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="93182-151">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="93182-152">Создает символы `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="93182-152">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="93182-153">Не выполняет сборку проекта перед упаковкой.</span><span class="sxs-lookup"><span data-stu-id="93182-153">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="93182-154">Собранные пакеты помещаются в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="93182-154">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="93182-155">Задает флаг "подлежит обслуживанию" в пакете.</span><span class="sxs-lookup"><span data-stu-id="93182-155">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="93182-156">Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="93182-156">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="93182-157">Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.</span><span class="sxs-lookup"><span data-stu-id="93182-157">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="93182-158">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="93182-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="93182-159">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="93182-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="93182-160">Примеры</span><span class="sxs-lookup"><span data-stu-id="93182-160">Examples</span></span>

<span data-ttu-id="93182-161">Упаковка проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="93182-161">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="93182-162">Упаковка проекта `app1`:</span><span class="sxs-lookup"><span data-stu-id="93182-162">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="93182-163">Упаковка проекта в текущем каталоге; полученные пакеты помещаются в папку `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="93182-163">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="93182-164">Упаковка проекта в текущем каталоге в папку `nupkgs` и пропуск этапа сборки:</span><span class="sxs-lookup"><span data-stu-id="93182-164">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="93182-165">Если суффикс версии пакета в файле *CSPROJ* настроен как `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`, упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса:</span><span class="sxs-lookup"><span data-stu-id="93182-165">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="93182-166">Устанавливает версию пакета в `2.1.0` с использованием свойства MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="93182-166">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

