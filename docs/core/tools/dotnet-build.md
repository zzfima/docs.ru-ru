---
title: Команда dotnet build
description: Команда dotnet build выполняет сборку проекта и всех его зависимостей.
ms.date: 04/24/2019
ms.openlocfilehash: df264fe830259832e5c75db9fd71230ba70a9f18
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959191"
---
# <a name="dotnet-build"></a><span data-ttu-id="9c8fb-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="9c8fb-103">dotnet build</span></span>

<span data-ttu-id="9c8fb-104">**Эта статья относится к ✓** SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="9c8fb-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="9c8fb-105">name</span><span class="sxs-lookup"><span data-stu-id="9c8fb-105">Name</span></span>

<span data-ttu-id="9c8fb-106">`dotnet build` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9c8fb-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9c8fb-107">Synopsis</span></span>

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--nologo] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9c8fb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="9c8fb-108">Description</span></span>

<span data-ttu-id="9c8fb-109">Команда `dotnet build` выполняет сборку проекта и его зависимостей в набор двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="9c8fb-110">Эти двоичные файлы содержат код проекта в виде файлов на промежуточном языке с расширением *DLL*, а также файлы символов для отладки с расширением *PDB*.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="9c8fb-111">Создается JSON-файл зависимостей ( *\*.deps.json*), содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-111">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="9c8fb-112">Создает файл *\*.runtimeconfig.json*, указывающий общую среду выполнения и ее версию для приложения.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-112">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="9c8fb-113">Если проект имеет зависимости от сторонних компонентов, таких как библиотеки из NuGet, они разрешаются из кэша NuGet и недоступны в выходных данных сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="9c8fb-114">Учитывая это, продукт `dotnet build` не готов к переносу на другой компьютер для выполнения.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="9c8fb-115">Это отличается от поведения в .NET Framework, где сборка исполняемого проекта (приложения) создает выходные данные, которые можно запустить на любом компьютере с установленной платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="9c8fb-116">Чтобы обеспечить аналогичное поведение в .NET Core, необходимо использовать команду [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="9c8fb-117">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="9c8fb-118">Для сборки нужен файл *project.assets.json*, содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="9c8fb-119">Он создается при выполнении команды [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="9c8fb-120">В отсутствие файла ресурсов инструментарий не может разрешать доступ к ссылочным сборкам, что приводит к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="9c8fb-121">При использовании пакета SDK для .NET Core 1.x необходимо было явным образом выполнять команду `dotnet restore` перед выполнением `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-121">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="9c8fb-122">Начиная с версии SDK для .NET Core 2.0 команда `dotnet restore` выполняется автоматически при выполнении `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="9c8fb-123">Чтобы отключить неявное восстановление при выполнении команды сборки, можно передать параметр `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="9c8fb-124">То, является ли проект исполняемым, определяется свойством `<OutputType>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="9c8fb-125">Следующий пример описывает проект, который создает исполняемый код:</span><span class="sxs-lookup"><span data-stu-id="9c8fb-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="9c8fb-126">Чтобы создать библиотеку, опустите свойство `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="9c8fb-127">Основное различие в выходных данных заключается в том, что библиотека DLL на промежуточном языке не содержит ни одной точки входа и ее нельзя выполнить.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="9c8fb-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="9c8fb-128">MSBuild</span></span>

<span data-ttu-id="9c8fb-129">`dotnet build` использует MSBuild для сборки проекта, поддерживая при этом как параллельные, так и инкрементные сборки.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="9c8fb-130">Дополнительные сведения см. в разделе [Инкрементные сборки](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="9c8fb-131">Помимо своих параметров, команда `dotnet build` принимает и параметры MSBuild, например `-p` для задания свойств или `-l` для определения средства ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="9c8fb-132">Дополнительные сведения об этих параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="9c8fb-133">Либо же вы можете использовать команду [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="9c8fb-134">Выполнение `dotnet build` эквивалентно `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="9c8fb-135">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9c8fb-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="9c8fb-136">Файл проекта или решения для сборки.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-136">The project or solution file to build.</span></span> <span data-ttu-id="9c8fb-137">Если файл проекта или решения не указан, MSBuild ищет текущий рабочий каталог для файла с расширением, которое заканчивается либо на *proj*, либо на *sln*, и использует этот файл.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="9c8fb-138">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c8fb-138">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="9c8fb-139">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-139">Defines the build configuration.</span></span> <span data-ttu-id="9c8fb-140">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-140">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9c8fb-141">Выполняет компиляцию для конкретной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="9c8fb-142">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-142">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="9c8fb-143">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="9c8fb-144">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="9c8fb-145">Доступно, начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-145">Available since .NET Core 2.0 SDK.</span></span>

* **`-h|--help`**

  <span data-ttu-id="9c8fb-146">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-146">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="9c8fb-147">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="9c8fb-148">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-148">For example, to complete authentication.</span></span> <span data-ttu-id="9c8fb-149">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-149">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="9c8fb-150">Межпроектные (P2P) ссылки игнорируются, и выполняется сборка только указанного корневого проекта.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="9c8fb-151">Помечает сборку как небезопасную для добавочной сборки.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="9c8fb-152">Этот флаг отключает инкрементную компиляцию и запускает принудительную полную перестройку схемы зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-logo`**

  <span data-ttu-id="9c8fb-153">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-153">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="9c8fb-154">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-154">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-restore`**

  <span data-ttu-id="9c8fb-155">Во время сборки не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-155">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="9c8fb-156">Доступно, начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-156">Available since .NET Core 2.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="9c8fb-157">Каталог, в который будут помещаться собранные двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="9c8fb-158">При указании этого параметра также необходимо определить `--framework`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="9c8fb-159">Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="9c8fb-160">Указывает целевую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-160">Specifies the target runtime.</span></span> <span data-ttu-id="9c8fb-161">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="9c8fb-162">Задает уровень детализации MSBuild.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="9c8fb-163">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="9c8fb-164">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-164">The default is `minimal`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="9c8fb-165">Задает значение свойства `$(VersionSuffix)`, которое используется при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="9c8fb-166">Работает, только если свойство `$(Version)` не задано.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="9c8fb-167">После этого параметру `$(Version)` присваиваются значения `$(VersionPrefix)` и `$(VersionSuffix)`, разделенные дефисом.</span><span class="sxs-lookup"><span data-stu-id="9c8fb-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="9c8fb-168">Примеры</span><span class="sxs-lookup"><span data-stu-id="9c8fb-168">Examples</span></span>

* <span data-ttu-id="9c8fb-169">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="9c8fb-169">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="9c8fb-170">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="9c8fb-170">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="9c8fb-171">Сборка проекта и его зависимостей для конкретной среды выполнения (в данном примере Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="9c8fb-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.18.04-x64
  ```

* <span data-ttu-id="9c8fb-172">Выполните сборку проекта и используйте указанный источник пакета NuGet во время операции восстановления (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="9c8fb-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="9c8fb-173">Выполните сборку проекта и задайте версию 1.2.3.4 для сборки с помощью [параметра MSBuild](#msbuild) `-p`:</span><span class="sxs-lookup"><span data-stu-id="9c8fb-173">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```
