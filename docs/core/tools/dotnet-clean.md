---
title: "Команда dotnet clean — CLI .NET Core"
description: "Команда dotnet clean очищает текущий каталог."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: f56ccc485884114262cd1364cf9398e302f2c48a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-clean"></a><span data-ttu-id="805cc-103">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="805cc-103">dotnet-clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="805cc-104">name</span><span class="sxs-lookup"><span data-stu-id="805cc-104">Name</span></span>

<span data-ttu-id="805cc-105">`dotnet clean` — очищает выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="805cc-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="805cc-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="805cc-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="805cc-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="805cc-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="805cc-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="805cc-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="805cc-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="805cc-109">Description</span></span>

<span data-ttu-id="805cc-110">Команда `dotnet clean` очищает выходные данные предыдущей сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-110">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="805cc-111">Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку.</span><span class="sxs-lookup"><span data-stu-id="805cc-111">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="805cc-112">Очищаются только выходные данные, созданные во время сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-112">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="805cc-113">Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).</span><span class="sxs-lookup"><span data-stu-id="805cc-113">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="805cc-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="805cc-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="805cc-115">Очищаемый проект MSBuild.</span><span class="sxs-lookup"><span data-stu-id="805cc-115">The MSBuild project to clean.</span></span> <span data-ttu-id="805cc-116">Если файл проекта не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="805cc-116">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="805cc-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="805cc-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="805cc-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="805cc-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="805cc-119">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-119">Defines the build configuration.</span></span> <span data-ttu-id="805cc-120">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="805cc-120">The default value is `Debug`.</span></span> <span data-ttu-id="805cc-121">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-121">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="805cc-122">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-122">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="805cc-123">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="805cc-123">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="805cc-124">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="805cc-124">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="805cc-125">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="805cc-125">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="805cc-126">Каталог, куда помещаются выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-126">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="805cc-127">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="805cc-127">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="805cc-128">Очищает выходную папку указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="805cc-128">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="805cc-129">Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="805cc-129">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="805cc-130">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="805cc-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="805cc-131">Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="805cc-131">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="805cc-132">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="805cc-132">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="805cc-133">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-133">Defines the build configuration.</span></span> <span data-ttu-id="805cc-134">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="805cc-134">The default value is `Debug`.</span></span> <span data-ttu-id="805cc-135">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-135">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="805cc-136">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-136">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="805cc-137">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="805cc-137">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="805cc-138">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="805cc-138">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="805cc-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="805cc-139">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="805cc-140">Каталог, куда помещаются выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="805cc-140">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="805cc-141">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="805cc-141">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="805cc-142">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="805cc-142">Sets the verbosity level of the command.</span></span> <span data-ttu-id="805cc-143">Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="805cc-143">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

---

## <a name="examples"></a><span data-ttu-id="805cc-144">Примеры</span><span class="sxs-lookup"><span data-stu-id="805cc-144">Examples</span></span>

<span data-ttu-id="805cc-145">Очистите сборку проекта по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="805cc-145">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="805cc-146">Очистите сборку проекта с помощью конфигурации выпуска:</span><span class="sxs-lookup"><span data-stu-id="805cc-146">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`
