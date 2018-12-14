---
title: Команда dotnet clean — CLI .NET Core
description: Команда dotnet clean очищает текущий каталог.
ms.date: 12/04/2018
ms.openlocfilehash: 9930d2905f234e7125f27367cda36aa85ae23b87
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144459"
---
# <a name="dotnet-clean"></a><span data-ttu-id="092a3-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="092a3-103">dotnet clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="092a3-104">name</span><span class="sxs-lookup"><span data-stu-id="092a3-104">Name</span></span>

<span data-ttu-id="092a3-105">`dotnet clean` — очищает выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="092a3-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="092a3-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="092a3-106">Synopsis</span></span>

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="092a3-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="092a3-107">Description</span></span>

<span data-ttu-id="092a3-108">Команда `dotnet clean` очищает выходные данные предыдущей сборки.</span><span class="sxs-lookup"><span data-stu-id="092a3-108">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="092a3-109">Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку.</span><span class="sxs-lookup"><span data-stu-id="092a3-109">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="092a3-110">Очищаются только выходные данные, созданные во время сборки.</span><span class="sxs-lookup"><span data-stu-id="092a3-110">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="092a3-111">Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).</span><span class="sxs-lookup"><span data-stu-id="092a3-111">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="092a3-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="092a3-112">Arguments</span></span>

`PROJECT`

<span data-ttu-id="092a3-113">Очищаемый проект MSBuild.</span><span class="sxs-lookup"><span data-stu-id="092a3-113">The MSBuild project to clean.</span></span> <span data-ttu-id="092a3-114">Если файл проекта не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="092a3-114">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="092a3-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="092a3-115">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="092a3-116">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="092a3-116">Defines the build configuration.</span></span> <span data-ttu-id="092a3-117">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="092a3-117">The default value is `Debug`.</span></span> <span data-ttu-id="092a3-118">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="092a3-118">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="092a3-119">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="092a3-119">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="092a3-120">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="092a3-120">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="092a3-121">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="092a3-121">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="092a3-122">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="092a3-122">Prints out a short help for the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="092a3-123">Каталог, куда помещаются выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="092a3-123">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="092a3-124">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="092a3-124">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="092a3-125">Очищает выходную папку указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="092a3-125">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="092a3-126">Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="092a3-126">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="092a3-127">Параметр доступен, начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="092a3-127">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="092a3-128">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="092a3-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="092a3-129">Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="092a3-129">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="092a3-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="092a3-130">Examples</span></span>

* <span data-ttu-id="092a3-131">Очистите сборку проекта по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="092a3-131">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="092a3-132">Очистите сборку проекта с помощью конфигурации выпуска:</span><span class="sxs-lookup"><span data-stu-id="092a3-132">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```