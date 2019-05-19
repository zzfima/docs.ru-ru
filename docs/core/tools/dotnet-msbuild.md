---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: 983fae6f4ecf875da0b155a668009984b5df50de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632031"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="4b2a3-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4b2a3-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4b2a3-104">name</span><span class="sxs-lookup"><span data-stu-id="4b2a3-104">Name</span></span>

<span data-ttu-id="4b2a3-105">`dotnet msbuild` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b2a3-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b2a3-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="4b2a3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4b2a3-107">Description</span></span>

<span data-ttu-id="4b2a3-108">Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="4b2a3-109">Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проекта в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="4b2a3-110">Все параметры одинаковы.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-110">The options are all the same.</span></span> <span data-ttu-id="4b2a3-111">Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="4b2a3-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="4b2a3-112">Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="4b2a3-113">Обычно для сборки проектов используется `dotnet build`, но `dotnet msbuild` дает больше возможностей управления.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="4b2a3-114">Например, если вам нужно выполнить конкретный целевой объект (без выполнения целевого объекта сборки), возможно, потребуется использовать `dotnet msbuild`.</span><span class="sxs-lookup"><span data-stu-id="4b2a3-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="4b2a3-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b2a3-115">Examples</span></span>

* <span data-ttu-id="4b2a3-116">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="4b2a3-116">Build a project and its dependencies:</span></span>

  ```console
  dotnet msbuild
  ```

* <span data-ttu-id="4b2a3-117">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="4b2a3-117">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="4b2a3-118">Запустите цель публикации и публикацию для RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="4b2a3-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="4b2a3-119">Весь проект со всеми целевыми объектами, включенными в пакет SDK:</span><span class="sxs-lookup"><span data-stu-id="4b2a3-119">See the whole project with all targets included by the SDK:</span></span>

  ```console
  dotnet msbuild -pp
  ```
