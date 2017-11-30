---
title: "Команда dotnet publish — CLI .NET Core"
description: "Команда dotnet publish публикует проект .NET Core в каталоге."
author: mairaw
ms.author: mairaw
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: d59ba8cf74a63c7d4a2234989477b5778fa0148f
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-publish"></a><span data-ttu-id="c88e3-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c88e3-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c88e3-104">Имя</span><span class="sxs-lookup"><span data-stu-id="c88e3-104">Name</span></span>

<span data-ttu-id="c88e3-105">`dotnet publish` — упаковывает приложение и его зависимости в папку для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="c88e3-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c88e3-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c88e3-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c88e3-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c88e3-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c88e3-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c88e3-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="c88e3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c88e3-109">Description</span></span>

<span data-ttu-id="c88e3-110">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="c88e3-110">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="c88e3-111">Выходные данные будут содержать следующее.</span><span class="sxs-lookup"><span data-stu-id="c88e3-111">The output will contain the following:</span></span>

* <span data-ttu-id="c88e3-112">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="c88e3-112">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="c88e3-113">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="c88e3-113">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="c88e3-114">Файл *.runtime.config.json*, указывающий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="c88e3-114">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="c88e3-115">Зависимости приложения.</span><span class="sxs-lookup"><span data-stu-id="c88e3-115">The application's dependencies.</span></span> <span data-ttu-id="c88e3-116">Они копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="c88e3-116">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="c88e3-117">Выходных данных команды `dotnet publish` готовы к развертыванию на размещающей системе (например, на сервере, компьютере, ноутбуке Mac) для выполнения и являются единственным официально поддерживаемым способом подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c88e3-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="c88e3-118">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c88e3-118">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="c88e3-119">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-119">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="c88e3-120">Структуру каталогов опубликованного приложения см. в разделе [Структура каталогов](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="c88e3-120">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="c88e3-121">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c88e3-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c88e3-122">Публикуемый проект. Если параметр не задан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c88e3-122">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="c88e3-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="c88e3-123">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c88e3-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c88e3-124">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c88e3-125">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="c88e3-125">Defines the build configuration.</span></span> <span data-ttu-id="c88e3-126">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="c88e3-126">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c88e3-127">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-127">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c88e3-128">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="c88e3-128">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="c88e3-129">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="c88e3-129">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c88e3-130">Равносильно удалению файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c88e3-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="c88e3-131">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c88e3-131">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="c88e3-132">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="c88e3-132">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="c88e3-133">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-133">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="c88e3-134">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="c88e3-134">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="c88e3-135">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="c88e3-135">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="c88e3-136">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="c88e3-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="c88e3-137">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="c88e3-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c88e3-138">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="c88e3-138">Specifies the path for the output directory.</span></span> <span data-ttu-id="c88e3-139">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.</span><span class="sxs-lookup"><span data-stu-id="c88e3-139">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="c88e3-140">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, не в текущем рабочем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c88e3-140">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="c88e3-141">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c88e3-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="c88e3-142">Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="c88e3-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="c88e3-143">Дополнительные сведения о типах развертывания см. в разделе [развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-143">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c88e3-144">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c88e3-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="c88e3-145">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="c88e3-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="c88e3-146">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c88e3-147">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="c88e3-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c88e3-148">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="c88e3-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c88e3-149">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c88e3-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="c88e3-150">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="c88e3-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c88e3-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c88e3-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c88e3-152">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="c88e3-152">Defines the build configuration.</span></span> <span data-ttu-id="c88e3-153">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="c88e3-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c88e3-154">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c88e3-155">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="c88e3-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="c88e3-156">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c88e3-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="c88e3-157">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="c88e3-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="c88e3-158">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="c88e3-159">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="c88e3-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="c88e3-160">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="c88e3-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c88e3-161">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="c88e3-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="c88e3-162">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.</span><span class="sxs-lookup"><span data-stu-id="c88e3-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="c88e3-163">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, не в текущем рабочем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c88e3-163">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c88e3-164">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c88e3-164">Publishes the application for a given runtime.</span></span> <span data-ttu-id="c88e3-165">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="c88e3-165">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="c88e3-166">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c88e3-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c88e3-167">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="c88e3-167">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c88e3-168">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="c88e3-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c88e3-169">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c88e3-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="c88e3-170">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="c88e3-170">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c88e3-171">Примеры</span><span class="sxs-lookup"><span data-stu-id="c88e3-171">Examples</span></span>

<span data-ttu-id="c88e3-172">Публикация проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c88e3-172">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="c88e3-173">Публикация приложения с использованием указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="c88e3-173">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="c88e3-174">Публикация проекта в текущем каталоге с использованием платформы `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="c88e3-174">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="c88e3-175">Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (вам нужно указать этот идентификатор RID в файле проекта).</span><span class="sxs-lookup"><span data-stu-id="c88e3-175">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="c88e3-176">См. также</span><span class="sxs-lookup"><span data-stu-id="c88e3-176">See also</span></span>

* [<span data-ttu-id="c88e3-177">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="c88e3-177">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="c88e3-178">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="c88e3-178">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
