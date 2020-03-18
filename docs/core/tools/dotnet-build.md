---
title: Команда dotnet build
description: Команда dotnet build выполняет сборку проекта и всех его зависимостей.
ms.date: 02/14/2020
ms.openlocfilehash: 9f9a78ec0a6a25c54c8a727c05081ce6835514ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503761"
---
# <a name="dotnet-build"></a><span data-ttu-id="7c1a8-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="7c1a8-103">dotnet build</span></span>

<span data-ttu-id="7c1a8-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="7c1a8-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7c1a8-105">Имя</span><span class="sxs-lookup"><span data-stu-id="7c1a8-105">Name</span></span>

<span data-ttu-id="7c1a8-106">`dotnet build` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7c1a8-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7c1a8-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force]
    [--interactive] [--no-dependencies] [--no-incremental] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7c1a8-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="7c1a8-108">Description</span></span>

<span data-ttu-id="7c1a8-109">Команда `dotnet build` выполняет сборку проекта и его зависимостей в набор двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="7c1a8-110">Эти двоичные файлы содержат код проекта в виде файлов на промежуточном языке (IL) с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="7c1a8-111">В зависимости от типа и параметров проекта могут быть включены другие файлы, например:</span><span class="sxs-lookup"><span data-stu-id="7c1a8-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="7c1a8-112">Исполняемый файл, который может использоваться для запуска приложения, если тип проекта является исполняемым файлом, предназначенным для .NET Core 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="7c1a8-113">Файлы символов, используемые для отладки с помощью расширения *PDB*.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="7c1a8-114">Файл *.deps.json*, в котором перечислены зависимости приложения или библиотеки.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="7c1a8-115">Файл *.runtimeconfig.json*, определяющий общую среду выполнения и ее версию для приложения.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="7c1a8-116">Другие библиотеки, от которых зависит проект (через ссылки на проект или ссылки на пакеты NuGet).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="7c1a8-117">Для исполняемых проектов, предназначенных для более ранних версий, чем .NET Core 3.0, зависимости библиотек от NuGet обычно НЕ копируются в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="7c1a8-118">Они разрешаются из папки глобальных пакетов NuGet во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="7c1a8-119">Учитывая это, продукт `dotnet build` не готов к переносу на другой компьютер для выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="7c1a8-120">Чтобы создать версию приложения, которая может быть развернута, необходимо опубликовать ее (например, с помощью команды [dotnet publish](dotnet-publish.md)).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="7c1a8-121">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="7c1a8-122">Для исполняемых проектов, предназначенных для .NET Core 3.0 и более поздних версий, зависимости библиотек копируются в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="7c1a8-123">Это означает, что если нет никакой другой логики для публикации (например, как у веб-проектов), выходные данные сборки можно развертывать.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

<span data-ttu-id="7c1a8-124">Для сборки нужен файл *project.assets.json*, содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-124">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="7c1a8-125">Он создается при выполнении команды [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-125">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="7c1a8-126">В отсутствие файла ресурсов инструментарий не может разрешать доступ к ссылочным сборкам, что приводит к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-126">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="7c1a8-127">При использовании пакета SDK для .NET Core 1.x необходимо было явным образом выполнять команду `dotnet restore` перед выполнением `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-127">With .NET Core 1.x SDK, you needed to explicitly run `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="7c1a8-128">Начиная с версии SDK для .NET Core 2.0 команда `dotnet restore` выполняется автоматически при выполнении `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-128">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="7c1a8-129">Чтобы отключить неявное восстановление при выполнении команды сборки, можно передать параметр `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-129">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="7c1a8-130">То, является ли проект исполняемым, определяется свойством `<OutputType>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-130">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="7c1a8-131">Следующий пример описывает проект, который создает исполняемый код:</span><span class="sxs-lookup"><span data-stu-id="7c1a8-131">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="7c1a8-132">Чтобы создать библиотеку, опустите свойство `<OutputType>` или измените его значение на `Library`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-132">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="7c1a8-133">Библиотека DLL на промежуточном языке не содержит ни одной точки входа, и ее нельзя выполнить.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-133">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="7c1a8-134">MSBuild</span><span class="sxs-lookup"><span data-stu-id="7c1a8-134">MSBuild</span></span>

<span data-ttu-id="7c1a8-135">`dotnet build` использует MSBuild для сборки проекта, поддерживая при этом как параллельные, так и инкрементные сборки.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-135">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="7c1a8-136">Дополнительные сведения см. в разделе [Инкрементные сборки](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-136">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="7c1a8-137">Помимо своих параметров, команда `dotnet build` принимает и параметры MSBuild, например `-p` для задания свойств или `-l` для определения средства ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-137">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="7c1a8-138">Дополнительные сведения об этих параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-138">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="7c1a8-139">Либо же вы можете использовать команду [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-139">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="7c1a8-140">Выполнение `dotnet build` эквивалентно выполнению `dotnet msbuild -restore`; однако уровень детализации выходных данных по умолчанию отличается.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-140">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="7c1a8-141">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7c1a8-141">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="7c1a8-142">Файл проекта или решения для сборки.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-142">The project or solution file to build.</span></span> <span data-ttu-id="7c1a8-143">Если файл проекта или решения не указан, MSBuild ищет текущий рабочий каталог для файла с расширением, которое заканчивается либо на *proj*, либо на *sln*, и использует этот файл.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-143">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="7c1a8-144">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c1a8-144">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="7c1a8-145">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-145">Defines the build configuration.</span></span> <span data-ttu-id="7c1a8-146">По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-146">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="7c1a8-147">Выполняет компиляцию для конкретной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-147">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="7c1a8-148">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-148">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="7c1a8-149">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-149">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="7c1a8-150">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-150">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="7c1a8-151">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-151">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="7c1a8-152">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-152">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="7c1a8-153">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-153">For example, to complete authentication.</span></span> <span data-ttu-id="7c1a8-154">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-154">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="7c1a8-155">Межпроектные (P2P) ссылки игнорируются, и выполняется сборка только указанного корневого проекта.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-155">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="7c1a8-156">Помечает сборку как небезопасную для добавочной сборки.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-156">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="7c1a8-157">Этот флаг отключает инкрементную компиляцию и запускает принудительную полную перестройку схемы зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-157">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="7c1a8-158">Во время сборки не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-158">Doesn't execute an implicit restore during build.</span></span>

- **`--nologo`**

  <span data-ttu-id="7c1a8-159">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-159">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="7c1a8-160">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-160">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="7c1a8-161">Каталог, в который будут помещаться собранные двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-161">Directory in which to place the built binaries.</span></span> <span data-ttu-id="7c1a8-162">Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="7c1a8-163">Для проектов с несколькими целевыми платформами (с помощью свойства `TargetFrameworks`) необходимо также определить `--framework` при указании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="7c1a8-164">Указывает целевую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-164">Specifies the target runtime.</span></span> <span data-ttu-id="7c1a8-165">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="7c1a8-166">Задает уровень детализации MSBuild.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-166">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="7c1a8-167">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-167">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7c1a8-168">Значение по умолчанию: `minimal`.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-168">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="7c1a8-169">Задает значение свойства `$(VersionSuffix)`, которое используется при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-169">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="7c1a8-170">Работает, только если свойство `$(Version)` не задано.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-170">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="7c1a8-171">После этого параметру `$(Version)` присваиваются значения `$(VersionPrefix)` и `$(VersionSuffix)`, разделенные дефисом.</span><span class="sxs-lookup"><span data-stu-id="7c1a8-171">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="7c1a8-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="7c1a8-172">Examples</span></span>

- <span data-ttu-id="7c1a8-173">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="7c1a8-173">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="7c1a8-174">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="7c1a8-174">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="7c1a8-175">Сборка проекта и его зависимостей для конкретной среды выполнения (в данном примере Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="7c1a8-175">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="7c1a8-176">Выполните сборку проекта и используйте указанный источник пакета NuGet во время операции восстановления (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-176">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="7c1a8-177">Выполните сборку проекта и задайте версию 1.2.3.4 для сборки с помощью параметра `-p` [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="7c1a8-177">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
