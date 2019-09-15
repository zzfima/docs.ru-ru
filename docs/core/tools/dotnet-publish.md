---
title: Команда dotnet publish
description: Команда dotnet publish публикует проект .NET Core в каталоге.
ms.date: 05/29/2018
ms.openlocfilehash: f9fea1a30e349ef949078e881756e2520d79ccbf
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969829"
---
# <a name="dotnet-publish"></a><span data-ttu-id="ac6e6-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ac6e6-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ac6e6-104">name</span><span class="sxs-lookup"><span data-stu-id="ac6e6-104">Name</span></span>

<span data-ttu-id="ac6e6-105">`dotnet publish` — упаковывает приложение и его зависимости в папку для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ac6e6-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ac6e6-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ac6e6-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ac6e6-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ac6e6-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ac6e6-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ac6e6-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ac6e6-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ac6e6-110">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ac6e6-110">Description</span></span>

<span data-ttu-id="ac6e6-111">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="ac6e6-112">Выходные данные включают следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="ac6e6-112">The output includes the following assets:</span></span>

- <span data-ttu-id="ac6e6-113">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="ac6e6-114">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="ac6e6-115">Файл *.runtimeconfig.json*, определяющий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-115">*.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="ac6e6-116">Зависимости приложения, которые копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="ac6e6-117">Выходные данные команды `dotnet publish` готовы к развертыванию в размещающей системе (например, на сервере, ПК, Mac, ноутбуке) для выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="ac6e6-118">Это единственный официальный способ подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="ac6e6-119">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="ac6e6-120">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="ac6e6-121">Структуру каталогов опубликованного приложения см. в разделе [Структура каталогов](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="ac6e6-122">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ac6e6-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ac6e6-123">Проект для публикации.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-123">The project to publish.</span></span> <span data-ttu-id="ac6e6-124">Это путь или имя файла проекта [C#](csproj.md), F# или Visual Basic либо же путь к папке, которая содержит файл проекта C#, F# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="ac6e6-125">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="ac6e6-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac6e6-126">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ac6e6-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ac6e6-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ac6e6-128">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-128">Defines the build configuration.</span></span> <span data-ttu-id="ac6e6-129">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ac6e6-130">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="ac6e6-131">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="ac6e6-132">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="ac6e6-133">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="ac6e6-134">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="ac6e6-135">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="ac6e6-136">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="ac6e6-137">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="ac6e6-138">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="ac6e6-139">Не выполняет сборку проекта перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="ac6e6-140">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="ac6e6-141">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="ac6e6-142">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ac6e6-143">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="ac6e6-144">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/publish/* для зависимого от платформы развертывания или *./bin/[configuration]/[framework]/[runtime]/publish/* для автономного.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="ac6e6-145">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="ac6e6-146">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="ac6e6-147">Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="ac6e6-148">Дополнительные сведения о различных типах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ac6e6-149">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="ac6e6-150">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="ac6e6-151">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ac6e6-152">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ac6e6-153">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ac6e6-154">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="ac6e6-155">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ac6e6-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ac6e6-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ac6e6-157">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-157">Defines the build configuration.</span></span> <span data-ttu-id="ac6e6-158">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ac6e6-159">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="ac6e6-160">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="ac6e6-161">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="ac6e6-162">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="ac6e6-163">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="ac6e6-164">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="ac6e6-165">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="ac6e6-166">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="ac6e6-167">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="ac6e6-168">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="ac6e6-169">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ac6e6-170">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="ac6e6-171">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/publish/* для зависимого от платформы развертывания или *./bin/[configuration]/[framework]/[runtime]/publish/* для автономного.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="ac6e6-172">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="ac6e6-173">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="ac6e6-174">Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="ac6e6-175">Дополнительные сведения о различных типах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ac6e6-176">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="ac6e6-177">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="ac6e6-178">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ac6e6-179">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ac6e6-180">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ac6e6-181">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="ac6e6-182">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ac6e6-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ac6e6-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ac6e6-184">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-184">Defines the build configuration.</span></span> <span data-ttu-id="ac6e6-185">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ac6e6-186">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="ac6e6-187">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="ac6e6-188">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="ac6e6-189">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="ac6e6-190">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="ac6e6-191">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="ac6e6-192">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ac6e6-193">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="ac6e6-194">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/publish/* для зависимого от платформы развертывания или *./bin/[configuration]/[framework]/[runtime]/publish/* для автономного.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="ac6e6-195">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ac6e6-196">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="ac6e6-197">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="ac6e6-198">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ac6e6-199">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ac6e6-200">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ac6e6-201">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="ac6e6-202">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="ac6e6-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="ac6e6-203">Примеры</span><span class="sxs-lookup"><span data-stu-id="ac6e6-203">Examples</span></span>

<span data-ttu-id="ac6e6-204">Публикация проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="ac6e6-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="ac6e6-205">Публикация приложения с использованием указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="ac6e6-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="ac6e6-206">Публикация проекта в текущем каталоге с использованием платформы `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="ac6e6-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="ac6e6-207">Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (вам нужно указать этот идентификатор RID в файле проекта).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="ac6e6-208">Публикация текущего приложения с обработкой только корневого проекта, без восстановления ссылок между проектами (P2P), во время операции восстановления (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="ac6e6-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="ac6e6-209">См. также</span><span class="sxs-lookup"><span data-stu-id="ac6e6-209">See also</span></span>

- [<span data-ttu-id="ac6e6-210">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="ac6e6-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="ac6e6-211">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="ac6e6-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
