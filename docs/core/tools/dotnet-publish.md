---
title: Команда dotnet publish — CLI .NET Core
description: Команда dotnet publish публикует проект .NET Core в каталоге.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: a60777d613573076f41fba3e5ed610b236884063
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511428"
---
# <a name="dotnet-publish"></a><span data-ttu-id="2680d-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2680d-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2680d-104">name</span><span class="sxs-lookup"><span data-stu-id="2680d-104">Name</span></span>

<span data-ttu-id="2680d-105">`dotnet publish` — упаковывает приложение и его зависимости в папку для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="2680d-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2680d-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2680d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2680d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2680d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2680d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2680d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2680d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2680d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="2680d-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="2680d-110">Description</span></span>

<span data-ttu-id="2680d-111">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="2680d-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="2680d-112">Выходные данные включают следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="2680d-112">The output includes the following assets:</span></span>

* <span data-ttu-id="2680d-113">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="2680d-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="2680d-114">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="2680d-115">Файл *.runtime.config.json*, указывающий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="2680d-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="2680d-116">Зависимости приложения, которые копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="2680d-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="2680d-117">Выходные данные команды `dotnet publish` готовы к развертыванию в размещающей системе (например, на сервере, ПК, Mac, ноутбуке) для выполнения.</span><span class="sxs-lookup"><span data-stu-id="2680d-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="2680d-118">Это единственный официальный способ подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2680d-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="2680d-119">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2680d-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="2680d-120">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="2680d-121">Структуру каталогов опубликованного приложения см. в разделе [Структура каталогов](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="2680d-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="2680d-122">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2680d-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="2680d-123">Проект для публикации.</span><span class="sxs-lookup"><span data-stu-id="2680d-123">The project to publish.</span></span> <span data-ttu-id="2680d-124">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="2680d-124">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="2680d-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="2680d-125">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2680d-126">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2680d-126">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2680d-127">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="2680d-127">Defines the build configuration.</span></span> <span data-ttu-id="2680d-128">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2680d-128">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2680d-129">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-129">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2680d-130">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-130">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="2680d-131">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="2680d-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2680d-132">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2680d-132">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2680d-133">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="2680d-133">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="2680d-134">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="2680d-134">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="2680d-135">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-135">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="2680d-136">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="2680d-136">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="2680d-137">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2680d-137">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="2680d-138">Не выполняет сборку проекта перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="2680d-138">Doesn't build the project before publishing.</span></span> <span data-ttu-id="2680d-139">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="2680d-139">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="2680d-140">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="2680d-140">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="2680d-141">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="2680d-141">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2680d-142">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="2680d-142">Specifies the path for the output directory.</span></span> <span data-ttu-id="2680d-143">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/publish/* для зависимого от платформы развертывания или *./bin/[configuration]/[framework]/[runtime]/publish/* для автономного.</span><span class="sxs-lookup"><span data-stu-id="2680d-143">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="2680d-144">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="2680d-144">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="2680d-145">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2680d-145">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="2680d-146">Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="2680d-146">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="2680d-147">Дополнительные сведения о различных типах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-147">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2680d-148">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2680d-148">Publishes the application for a given runtime.</span></span> <span data-ttu-id="2680d-149">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="2680d-149">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="2680d-150">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-150">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2680d-151">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="2680d-151">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2680d-152">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="2680d-152">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2680d-153">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2680d-153">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="2680d-154">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-154">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2680d-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2680d-155">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2680d-156">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="2680d-156">Defines the build configuration.</span></span> <span data-ttu-id="2680d-157">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2680d-157">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2680d-158">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-158">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2680d-159">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-159">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="2680d-160">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="2680d-160">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2680d-161">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2680d-161">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2680d-162">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="2680d-162">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="2680d-163">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="2680d-163">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="2680d-164">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-164">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="2680d-165">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="2680d-165">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="2680d-166">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2680d-166">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="2680d-167">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="2680d-167">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="2680d-168">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="2680d-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2680d-169">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="2680d-169">Specifies the path for the output directory.</span></span> <span data-ttu-id="2680d-170">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/publish/* для зависимого от платформы развертывания или *./bin/[configuration]/[framework]/[runtime]/publish/* для автономного.</span><span class="sxs-lookup"><span data-stu-id="2680d-170">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="2680d-171">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="2680d-171">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="2680d-172">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2680d-172">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="2680d-173">Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="2680d-173">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="2680d-174">Дополнительные сведения о различных типах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-174">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2680d-175">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2680d-175">Publishes the application for a given runtime.</span></span> <span data-ttu-id="2680d-176">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="2680d-176">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="2680d-177">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2680d-178">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="2680d-178">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2680d-179">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="2680d-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2680d-180">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2680d-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="2680d-181">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-181">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2680d-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2680d-182">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2680d-183">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="2680d-183">Defines the build configuration.</span></span> <span data-ttu-id="2680d-184">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2680d-184">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2680d-185">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-185">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2680d-186">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-186">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="2680d-187">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="2680d-187">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="2680d-188">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="2680d-188">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="2680d-189">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-189">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="2680d-190">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="2680d-190">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="2680d-191">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2680d-191">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2680d-192">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="2680d-192">Specifies the path for the output directory.</span></span> <span data-ttu-id="2680d-193">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/publish/* для зависимого от платформы развертывания или *./bin/[configuration]/[framework]/[runtime]/publish/* для автономного.</span><span class="sxs-lookup"><span data-stu-id="2680d-193">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="2680d-194">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="2680d-194">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2680d-195">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2680d-195">Publishes the application for a given runtime.</span></span> <span data-ttu-id="2680d-196">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="2680d-196">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="2680d-197">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2680d-197">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2680d-198">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="2680d-198">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2680d-199">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="2680d-199">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2680d-200">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2680d-200">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="2680d-201">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="2680d-201">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="2680d-202">Примеры</span><span class="sxs-lookup"><span data-stu-id="2680d-202">Examples</span></span>

<span data-ttu-id="2680d-203">Публикация проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="2680d-203">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="2680d-204">Публикация приложения с использованием указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="2680d-204">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="2680d-205">Публикация проекта в текущем каталоге с использованием платформы `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="2680d-205">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="2680d-206">Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (вам нужно указать этот идентификатор RID в файле проекта).</span><span class="sxs-lookup"><span data-stu-id="2680d-206">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="2680d-207">Публикация текущего приложения с обработкой только корневого проекта, без восстановления ссылок между проектами (P2P), во время операции восстановления (пакет SDK для .NET Core 2.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="2680d-207">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="2680d-208">См. также</span><span class="sxs-lookup"><span data-stu-id="2680d-208">See also</span></span>

* [<span data-ttu-id="2680d-209">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="2680d-209">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="2680d-210">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="2680d-210">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
