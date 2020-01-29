---
title: Команда dotnet clean
description: Команда dotnet clean очищает текущий каталог.
ms.date: 06/26/2019
ms.openlocfilehash: 736c0bba5d156e919534f1ad811641e815b3ffac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734249"
---
# <a name="dotnet-clean"></a><span data-ttu-id="d2c9b-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="d2c9b-103">dotnet clean</span></span>

<span data-ttu-id="d2c9b-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d2c9b-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="d2c9b-105">name</span><span class="sxs-lookup"><span data-stu-id="d2c9b-105">Name</span></span>

<span data-ttu-id="d2c9b-106">`dotnet clean` — очищает выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2c9b-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d2c9b-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="d2c9b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d2c9b-108">Description</span></span>

<span data-ttu-id="d2c9b-109">Команда `dotnet clean` очищает выходные данные предыдущей сборки.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="d2c9b-110">Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="d2c9b-111">Очищаются только выходные данные, созданные во время сборки.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="d2c9b-112">Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).</span><span class="sxs-lookup"><span data-stu-id="d2c9b-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="d2c9b-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d2c9b-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="d2c9b-114">Проект или решение MSBuild, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="d2c9b-115">Если файл проекта или решения не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ* или *SLN*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="d2c9b-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2c9b-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="d2c9b-117">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-117">Defines the build configuration.</span></span> <span data-ttu-id="d2c9b-118">Значение по умолчанию — `Debug`.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-118">The default value is `Debug`.</span></span> <span data-ttu-id="d2c9b-119">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2c9b-120">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="d2c9b-121">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="d2c9b-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="d2c9b-122">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="d2c9b-123">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="d2c9b-124">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="d2c9b-125">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-125">For example, to complete authentication.</span></span> <span data-ttu-id="d2c9b-126">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="d2c9b-127">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="d2c9b-128">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="d2c9b-129">Каталог, содержащий артефакты сборки, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="d2c9b-130">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="d2c9b-131">Очищает выходную папку указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="d2c9b-132">Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="d2c9b-132">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="d2c9b-133">Параметр доступен, начиная с пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-133">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d2c9b-134">Задает уровень детализации MSBuild.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-134">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="d2c9b-135">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-135">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d2c9b-136">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="d2c9b-136">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="d2c9b-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2c9b-137">Examples</span></span>

* <span data-ttu-id="d2c9b-138">Очистите сборку проекта по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="d2c9b-138">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="d2c9b-139">Очистите сборку проекта с помощью конфигурации выпуска:</span><span class="sxs-lookup"><span data-stu-id="d2c9b-139">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
