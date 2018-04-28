---
title: Команда dotnet clean — CLI .NET Core
description: Команда dotnet clean очищает текущий каталог.
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 92db35df770b1e1d2438127c4b529d4cb480c8df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-clean"></a><span data-ttu-id="a64b7-103">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="a64b7-103">dotnet-clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a64b7-104">name</span><span class="sxs-lookup"><span data-stu-id="a64b7-104">Name</span></span>

<span data-ttu-id="a64b7-105">`dotnet clean` — очищает выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="a64b7-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a64b7-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a64b7-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="a64b7-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a64b7-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a64b7-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a64b7-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="a64b7-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="a64b7-109">Description</span></span>

<span data-ttu-id="a64b7-110">Команда `dotnet clean` очищает выходные данные предыдущей сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-110">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="a64b7-111">Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку.</span><span class="sxs-lookup"><span data-stu-id="a64b7-111">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="a64b7-112">Очищаются только выходные данные, созданные во время сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-112">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="a64b7-113">Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).</span><span class="sxs-lookup"><span data-stu-id="a64b7-113">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="a64b7-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a64b7-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="a64b7-115">Очищаемый проект MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a64b7-115">The MSBuild project to clean.</span></span> <span data-ttu-id="a64b7-116">Если файл проекта не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="a64b7-116">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="a64b7-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="a64b7-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="a64b7-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a64b7-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a64b7-119">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-119">Defines the build configuration.</span></span> <span data-ttu-id="a64b7-120">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a64b7-120">The default value is `Debug`.</span></span> <span data-ttu-id="a64b7-121">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-121">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a64b7-122">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-122">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="a64b7-123">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="a64b7-123">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="a64b7-124">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="a64b7-124">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="a64b7-125">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a64b7-125">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a64b7-126">Каталог, куда помещаются выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-126">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="a64b7-127">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="a64b7-127">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="a64b7-128">Очищает выходную папку указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a64b7-128">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="a64b7-129">Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="a64b7-129">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a64b7-130">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="a64b7-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a64b7-131">Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="a64b7-131">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a64b7-132">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a64b7-132">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a64b7-133">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-133">Defines the build configuration.</span></span> <span data-ttu-id="a64b7-134">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a64b7-134">The default value is `Debug`.</span></span> <span data-ttu-id="a64b7-135">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-135">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a64b7-136">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-136">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="a64b7-137">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="a64b7-137">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="a64b7-138">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="a64b7-138">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="a64b7-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="a64b7-139">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a64b7-140">Каталог, куда помещаются выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="a64b7-140">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="a64b7-141">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="a64b7-141">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a64b7-142">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="a64b7-142">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a64b7-143">Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="a64b7-143">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

---

## <a name="examples"></a><span data-ttu-id="a64b7-144">Примеры</span><span class="sxs-lookup"><span data-stu-id="a64b7-144">Examples</span></span>

<span data-ttu-id="a64b7-145">Очистите сборку проекта по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a64b7-145">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="a64b7-146">Очистите сборку проекта с помощью конфигурации выпуска:</span><span class="sxs-lookup"><span data-stu-id="a64b7-146">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`
