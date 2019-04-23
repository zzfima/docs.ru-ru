---
title: Команда dotnet build
description: Команда dotnet build выполняет сборку проекта и всех его зависимостей.
ms.date: 12/04/2018
ms.openlocfilehash: 6a701ee371221c780a878e64b996df95f709371f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612697"
---
# <a name="dotnet-build"></a><span data-ttu-id="f0665-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f0665-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f0665-104">name</span><span class="sxs-lookup"><span data-stu-id="f0665-104">Name</span></span>

<span data-ttu-id="f0665-105">`dotnet build` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="f0665-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f0665-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f0665-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f0665-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f0665-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f0665-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f0665-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="f0665-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f0665-109">Description</span></span>

<span data-ttu-id="f0665-110">Команда `dotnet build` выполняет сборку проекта и его зависимостей в набор двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="f0665-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="f0665-111">Эти двоичные файлы содержат код проекта в виде файлов на промежуточном языке с расширением *DLL*, а также файлы символов для отладки с расширением *PDB*.</span><span class="sxs-lookup"><span data-stu-id="f0665-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="f0665-112">Создается JSON-файл зависимостей (*\*.deps.json*), содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="f0665-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="f0665-113">Создает файл *\*.runtimeconfig.json*, указывающий общую среду выполнения и ее версию для приложения.</span><span class="sxs-lookup"><span data-stu-id="f0665-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="f0665-114">Если проект имеет зависимости от сторонних компонентов, таких как библиотеки из NuGet, они разрешаются из кэша NuGet и недоступны в выходных данных сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="f0665-115">Учитывая это, продукт `dotnet build` не готов к переносу на другой компьютер для выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0665-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="f0665-116">Это отличается от поведения в .NET Framework, где сборка исполняемого проекта (приложения) создает выходные данные, которые можно запустить на любом компьютере с установленной платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0665-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="f0665-117">Чтобы обеспечить аналогичное поведение в .NET Core, необходимо использовать команду [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="f0665-118">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="f0665-119">Для сборки нужен файл *project.assets.json*, содержащий список зависимостей приложения.</span><span class="sxs-lookup"><span data-stu-id="f0665-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="f0665-120">Он создается при выполнении команды [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="f0665-121">Без файла ресурсов инструментарий не способен разрешать базовые сборки, что приводит к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="f0665-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="f0665-122">При использовании пакета SDK для .NET Core 1.x необходимо было явным образом выполнять команду `dotnet restore` перед выполнением `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="f0665-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="f0665-123">Начиная с версии SDK для .NET Core 2.0 команда `dotnet restore` выполняется автоматически при выполнении `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="f0665-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="f0665-124">Чтобы отключить неявное восстановление при выполнении команды сборки, можно передать параметр `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="f0665-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="f0665-125">То, является ли проект исполняемым, определяется свойством `<OutputType>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-125">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="f0665-126">Следующий пример описывает проект, который создает исполняемый код:</span><span class="sxs-lookup"><span data-stu-id="f0665-126">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="f0665-127">Чтобы создать библиотеку, опустите свойство `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="f0665-127">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="f0665-128">Основное различие в выходных данных заключается в том, что библиотека DLL на промежуточном языке не содержит ни одной точки входа и ее нельзя выполнить.</span><span class="sxs-lookup"><span data-stu-id="f0665-128">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="f0665-129">MSBuild</span><span class="sxs-lookup"><span data-stu-id="f0665-129">MSBuild</span></span>

<span data-ttu-id="f0665-130">`dotnet build` использует MSBuild для сборки проекта, поддерживая при этом как параллельные, так и инкрементные сборки.</span><span class="sxs-lookup"><span data-stu-id="f0665-130">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="f0665-131">Дополнительные сведения см. в разделе [Инкрементные сборки](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="f0665-131">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="f0665-132">Помимо своих параметров, команда `dotnet build` принимает и параметры MSBuild, например `-p` для задания свойств или `-l` для определения средства ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="f0665-132">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="f0665-133">Дополнительные сведения об этих параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="f0665-133">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="f0665-134">Либо же вы можете использовать команду [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-134">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="f0665-135">Выполнение `dotnet build` эквивалентно `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="f0665-135">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="f0665-136">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f0665-136">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="f0665-137">Файл проекта или решения для сборки.</span><span class="sxs-lookup"><span data-stu-id="f0665-137">The project or solution file to build.</span></span> <span data-ttu-id="f0665-138">Если файл проекта или решения не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ* или *SLN*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="f0665-138">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="f0665-139">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0665-139">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f0665-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f0665-140">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="f0665-141">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="f0665-141">Defines the build configuration.</span></span> <span data-ttu-id="f0665-142">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f0665-142">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f0665-143">Выполняет компиляцию для конкретной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-143">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f0665-144">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-144">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="f0665-145">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="f0665-145">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="f0665-146">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="f0665-146">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="f0665-147">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="f0665-147">Prints out a short help for the command.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="f0665-148">Межпроектные (P2P) ссылки игнорируются, и выполняется сборка только указанного корневого проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-148">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="f0665-149">Помечает сборку как небезопасную для добавочной сборки.</span><span class="sxs-lookup"><span data-stu-id="f0665-149">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="f0665-150">Этот флаг отключает инкрементную компиляцию и запускает принудительную полную перестройку схемы зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-150">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-restore`**

  <span data-ttu-id="f0665-151">Во время сборки не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f0665-151">Doesn't execute an implicit restore during build.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f0665-152">Каталог, в который будут помещаться собранные двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="f0665-152">Directory in which to place the built binaries.</span></span> <span data-ttu-id="f0665-153">При указании этого параметра также необходимо определить `--framework`.</span><span class="sxs-lookup"><span data-stu-id="f0665-153">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="f0665-154">Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="f0665-154">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="f0665-155">Указывает целевую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0665-155">Specifies the target runtime.</span></span> <span data-ttu-id="f0665-156">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-156">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f0665-157">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="f0665-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f0665-158">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f0665-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="f0665-159">Определяет суффикс версии для звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-159">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="f0665-160">Формат соответствует рекомендациям в отношении версий NuGet.</span><span class="sxs-lookup"><span data-stu-id="f0665-160">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f0665-161">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f0665-161">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="f0665-162">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="f0665-162">Defines the build configuration.</span></span> <span data-ttu-id="f0665-163">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f0665-163">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f0665-164">Выполняет компиляцию для конкретной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-164">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f0665-165">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-165">The framework must be defined in the [project file](csproj.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="f0665-166">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="f0665-166">Prints out a short help for the command.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="f0665-167">Межпроектные (P2P) ссылки игнорируются, и выполняется сборка только указанного корневого проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-167">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="f0665-168">Помечает сборку как небезопасную для добавочной сборки.</span><span class="sxs-lookup"><span data-stu-id="f0665-168">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="f0665-169">Этот флаг отключает инкрементную компиляцию и запускает принудительную полную перестройку схемы зависимостей проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-169">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f0665-170">Каталог, в который будут помещаться собранные двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="f0665-170">Directory in which to place the built binaries.</span></span> <span data-ttu-id="f0665-171">При указании этого параметра также необходимо определить `--framework`.</span><span class="sxs-lookup"><span data-stu-id="f0665-171">You also need to define `--framework` when you specify this option.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="f0665-172">Указывает целевую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0665-172">Specifies the target runtime.</span></span> <span data-ttu-id="f0665-173">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f0665-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f0665-174">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="f0665-174">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f0665-175">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f0665-175">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="f0665-176">Определяет суффикс версии для звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="f0665-176">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="f0665-177">Формат соответствует рекомендациям в отношении версий NuGet.</span><span class="sxs-lookup"><span data-stu-id="f0665-177">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="f0665-178">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0665-178">Examples</span></span>

* <span data-ttu-id="f0665-179">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="f0665-179">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="f0665-180">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="f0665-180">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="f0665-181">Сборка проекта и его зависимостей для определенной среды выполнения (в этом примере это Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="f0665-181">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.16.04-x64
  ```

* <span data-ttu-id="f0665-182">Выполните сборку проекта и используйте указанный источник пакета NuGet во время операции восстановления (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="f0665-182">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="f0665-183">Создайте проект и задайте версию 1.2.3.4 как параметр сборки:</span><span class="sxs-lookup"><span data-stu-id="f0665-183">Build the project and set 1.2.3.4 version as a build parameter:</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```