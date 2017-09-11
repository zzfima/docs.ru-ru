---
title: "Команда dotnet publish — CLI .NET Core"
description: "Команда dotnet publish публикует проект .NET Core в каталоге."
keywords: "dotnet-publish, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: db6e527a6132be0b6362c68945bb68884f5ad619
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-publish"></a><span data-ttu-id="60f77-104">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="60f77-104">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="60f77-105">Имя</span><span class="sxs-lookup"><span data-stu-id="60f77-105">Name</span></span>

<span data-ttu-id="60f77-106">`dotnet publish` — упаковывает приложение и его зависимости в папку для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="60f77-106">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="60f77-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="60f77-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="60f77-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="60f77-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="60f77-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="60f77-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="60f77-110">Описание</span><span class="sxs-lookup"><span data-stu-id="60f77-110">Description</span></span>

<span data-ttu-id="60f77-111">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="60f77-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="60f77-112">Выходные данные будут содержать следующее.</span><span class="sxs-lookup"><span data-stu-id="60f77-112">The output will contain the following:</span></span>

* <span data-ttu-id="60f77-113">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="60f77-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="60f77-114">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="60f77-114">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="60f77-115">Файл *.runtime.config.json*, указывающий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="60f77-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="60f77-116">Зависимости приложения.</span><span class="sxs-lookup"><span data-stu-id="60f77-116">The application's dependencies.</span></span> <span data-ttu-id="60f77-117">Они копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="60f77-117">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="60f77-118">Выходных данных команды `dotnet publish` готовы к развертыванию на размещающей системе (например, на сервере, компьютере, ноутбуке Mac) для выполнения и являются единственным официально поддерживаемым способом подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="60f77-118">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="60f77-119">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="60f77-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="60f77-120">Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="60f77-121">Структуру каталогов опубликованного приложения см. в разделе [Структура каталогов](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="60f77-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="60f77-122">Аргументы</span><span class="sxs-lookup"><span data-stu-id="60f77-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="60f77-123">Публикуемый проект. Если параметр не задан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="60f77-123">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="60f77-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="60f77-124">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="60f77-125">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="60f77-125">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="60f77-126">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="60f77-126">Defines the build configuration.</span></span> <span data-ttu-id="60f77-127">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="60f77-127">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="60f77-128">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="60f77-129">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="60f77-129">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="60f77-130">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="60f77-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="60f77-131">Равносильно удалению файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="60f77-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="60f77-132">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="60f77-132">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="60f77-133">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="60f77-133">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="60f77-134">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-134">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="60f77-135">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="60f77-135">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="60f77-136">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="60f77-136">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="60f77-137">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="60f77-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="60f77-138">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="60f77-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="60f77-139">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="60f77-139">Specifies the path for the output directory.</span></span> <span data-ttu-id="60f77-140">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.</span><span class="sxs-lookup"><span data-stu-id="60f77-140">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`--self-contained`

<span data-ttu-id="60f77-141">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="60f77-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="60f77-142">Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="60f77-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="60f77-143">Дополнительные сведения о различных типах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-143">For more infomation about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="60f77-144">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="60f77-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="60f77-145">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="60f77-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="60f77-146">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="60f77-147">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="60f77-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="60f77-148">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="60f77-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="60f77-149">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="60f77-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="60f77-150">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="60f77-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="60f77-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="60f77-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="60f77-152">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="60f77-152">Defines the build configuration.</span></span> <span data-ttu-id="60f77-153">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="60f77-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="60f77-154">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="60f77-155">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="60f77-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="60f77-156">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="60f77-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="60f77-157">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="60f77-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="60f77-158">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="60f77-159">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="60f77-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="60f77-160">Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="60f77-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="60f77-161">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="60f77-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="60f77-162">Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.</span><span class="sxs-lookup"><span data-stu-id="60f77-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="60f77-163">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="60f77-163">Publishes the application for a given runtime.</span></span> <span data-ttu-id="60f77-164">Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="60f77-164">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="60f77-165">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="60f77-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="60f77-166">По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="60f77-166">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="60f77-167">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="60f77-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="60f77-168">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="60f77-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="60f77-169">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="60f77-169">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="60f77-170">Примеры</span><span class="sxs-lookup"><span data-stu-id="60f77-170">Examples</span></span>

<span data-ttu-id="60f77-171">Публикация проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="60f77-171">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="60f77-172">Публикация приложения с использованием указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="60f77-172">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="60f77-173">Публикация проекта в текущем каталоге с использованием платформы `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="60f77-173">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="60f77-174">Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (вам нужно указать этот идентификатор RID в файле проекта).</span><span class="sxs-lookup"><span data-stu-id="60f77-174">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="60f77-175">См. также</span><span class="sxs-lookup"><span data-stu-id="60f77-175">See also</span></span>

* [<span data-ttu-id="60f77-176">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="60f77-176">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="60f77-177">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="60f77-177">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

