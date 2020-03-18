---
title: Команда dotnet clean
description: Команда dotnet clean очищает текущий каталог.
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503757"
---
# <a name="dotnet-clean"></a><span data-ttu-id="c9e28-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c9e28-103">dotnet clean</span></span>

<span data-ttu-id="c9e28-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c9e28-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c9e28-105">Имя</span><span class="sxs-lookup"><span data-stu-id="c9e28-105">Name</span></span>

<span data-ttu-id="c9e28-106">`dotnet clean` — очищает выходные данные проекта.</span><span class="sxs-lookup"><span data-stu-id="c9e28-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c9e28-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c9e28-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c9e28-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="c9e28-108">Description</span></span>

<span data-ttu-id="c9e28-109">Команда `dotnet clean` очищает выходные данные предыдущей сборки.</span><span class="sxs-lookup"><span data-stu-id="c9e28-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="c9e28-110">Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку.</span><span class="sxs-lookup"><span data-stu-id="c9e28-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="c9e28-111">Очищаются только выходные данные, созданные во время сборки.</span><span class="sxs-lookup"><span data-stu-id="c9e28-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="c9e28-112">Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).</span><span class="sxs-lookup"><span data-stu-id="c9e28-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="c9e28-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c9e28-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="c9e28-114">Проект или решение MSBuild, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="c9e28-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="c9e28-115">Если файл проекта или решения не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ* или *SLN*, и использует его.</span><span class="sxs-lookup"><span data-stu-id="c9e28-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="c9e28-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9e28-116">Options</span></span>

* **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="c9e28-117">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="c9e28-117">Defines the build configuration.</span></span> <span data-ttu-id="c9e28-118">По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="c9e28-118">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span> <span data-ttu-id="c9e28-119">Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.</span><span class="sxs-lookup"><span data-stu-id="c9e28-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c9e28-120">[Платформа](../../standard/frameworks.md), указанная во время сборки.</span><span class="sxs-lookup"><span data-stu-id="c9e28-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="c9e28-121">Платформа должна быть определена в [файле проекта](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="c9e28-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="c9e28-122">Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.</span><span class="sxs-lookup"><span data-stu-id="c9e28-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="c9e28-123">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c9e28-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="c9e28-124">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="c9e28-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="c9e28-125">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9e28-125">For example, to complete authentication.</span></span> <span data-ttu-id="c9e28-126">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c9e28-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="c9e28-127">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="c9e28-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="c9e28-128">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c9e28-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c9e28-129">Каталог, содержащий артефакты сборки, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="c9e28-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="c9e28-130">Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.</span><span class="sxs-lookup"><span data-stu-id="c9e28-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c9e28-131">Очищает выходную папку указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9e28-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="c9e28-132">Используется, если было создано [автономное развертывание](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="c9e28-132">This is used when a [self-contained deployment](../deploying/index.md#publish-self-contained) was created.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c9e28-133">Задает уровень детализации MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c9e28-133">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="c9e28-134">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c9e28-134">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c9e28-135">Значение по умолчанию: `normal`.</span><span class="sxs-lookup"><span data-stu-id="c9e28-135">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="c9e28-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="c9e28-136">Examples</span></span>

* <span data-ttu-id="c9e28-137">Очистите сборку проекта по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="c9e28-137">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="c9e28-138">Очистите сборку проекта с помощью конфигурации выпуска:</span><span class="sxs-lookup"><span data-stu-id="c9e28-138">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
