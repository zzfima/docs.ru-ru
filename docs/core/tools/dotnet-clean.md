---
title: Команда dotnet clean
description: Команда dotnet clean очищает текущий каталог.
ms.date: 04/14/2019
ms.openlocfilehash: 3e735c02c9be9b6f51a8cdf048c18eff34f838cb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754121"
---
# <a name="dotnet-clean"></a><span data-ttu-id="005b9-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="005b9-103">dotnet clean</span></span>

<span data-ttu-id="005b9-104">**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="005b9-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="005b9-105">name</span><span class="sxs-lookup"><span data-stu-id="005b9-105">Name</span></span>

<span data-ttu-id="005b9-106">`dotnet clean` — очищает выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="005b9-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="005b9-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="005b9-107">Synopsis</span></span>

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="005b9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="005b9-108">Description</span></span>

<span data-ttu-id="005b9-109">Команда `dotnet clean` очищает выходные данные предыдущей сборки.</span><span class="sxs-lookup"><span data-stu-id="005b9-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="005b9-110">Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку.</span><span class="sxs-lookup"><span data-stu-id="005b9-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="005b9-111">Очищаются только выходные данные, созданные во время сборки.</span><span class="sxs-lookup"><span data-stu-id="005b9-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="005b9-112">Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).</span><span class="sxs-lookup"><span data-stu-id="005b9-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="005b9-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="005b9-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="005b9-114">Проект или решение MSBuild, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="005b9-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="005b9-115">Если файл проекта или решения не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ* или *SLN*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="005b9-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="005b9-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="005b9-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="005b9-117">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="005b9-117">Defines the build configuration.</span></span> <span data-ttu-id="005b9-118">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="005b9-118">The default value is `Debug`.</span></span> <span data-ttu-id="005b9-119">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="005b9-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="005b9-120">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="005b9-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="005b9-121">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="005b9-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="005b9-122">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="005b9-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="005b9-123">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="005b9-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="005b9-124">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="005b9-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="005b9-125">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="005b9-125">For example, to complete authentication.</span></span> <span data-ttu-id="005b9-126">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="005b9-126">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="005b9-127">Каталог, содержащий артефакты сборки, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="005b9-127">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="005b9-128">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="005b9-128">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="005b9-129">Очищает выходную папку указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="005b9-129">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="005b9-130">Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="005b9-130">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="005b9-131">Параметр доступен, начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="005b9-131">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="005b9-132">Задает уровень детализации MSBuild.</span><span class="sxs-lookup"><span data-stu-id="005b9-132">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="005b9-133">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="005b9-133">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="005b9-134">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="005b9-134">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="005b9-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="005b9-135">Examples</span></span>

* <span data-ttu-id="005b9-136">Очистите сборку проекта по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="005b9-136">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="005b9-137">Очистите сборку проекта с помощью конфигурации выпуска:</span><span class="sxs-lookup"><span data-stu-id="005b9-137">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```