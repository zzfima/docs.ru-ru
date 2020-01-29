---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733194"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="5aca6-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="5aca6-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5aca6-104">name</span><span class="sxs-lookup"><span data-stu-id="5aca6-104">Name</span></span>

<span data-ttu-id="5aca6-105">`dotnet msbuild` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="5aca6-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5aca6-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5aca6-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="5aca6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5aca6-107">Description</span></span>

<span data-ttu-id="5aca6-108">Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.</span><span class="sxs-lookup"><span data-stu-id="5aca6-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="5aca6-109">Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проектов в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="5aca6-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="5aca6-110">Все параметры одинаковы.</span><span class="sxs-lookup"><span data-stu-id="5aca6-110">The options are all the same.</span></span> <span data-ttu-id="5aca6-111">Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="5aca6-111">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="5aca6-112">Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="5aca6-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="5aca6-113">Обычно для сборки проектов используется команда [dotnet build](dotnet-build.md). Так как команда `dotnet msbuild` всегда запускает целевой объект сборки, вы можете использовать ее, если не хотите выполнять сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="5aca6-113">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="5aca6-114">Например, если вам нужно запустить конкретный целевой объект, не выполняя сборку проекта, используйте `dotnet msbuild` и укажите целевой объект.</span><span class="sxs-lookup"><span data-stu-id="5aca6-114">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="5aca6-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="5aca6-115">Examples</span></span>

* <span data-ttu-id="5aca6-116">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="5aca6-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="5aca6-117">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="5aca6-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* <span data-ttu-id="5aca6-118">Запустите цель публикации и публикацию для RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="5aca6-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="5aca6-119">Весь проект со всеми целевыми объектами, включенными в пакет SDK:</span><span class="sxs-lookup"><span data-stu-id="5aca6-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
