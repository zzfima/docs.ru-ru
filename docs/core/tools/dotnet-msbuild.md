---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: b83f1272cdd4c5fcdb6b1e34aef7692e9acc01cd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117700"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="678f6-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="678f6-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="678f6-104">name</span><span class="sxs-lookup"><span data-stu-id="678f6-104">Name</span></span>

<span data-ttu-id="678f6-105">`dotnet msbuild` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="678f6-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="678f6-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="678f6-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="678f6-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="678f6-107">Description</span></span>

<span data-ttu-id="678f6-108">Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.</span><span class="sxs-lookup"><span data-stu-id="678f6-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="678f6-109">Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проекта в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="678f6-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="678f6-110">Все параметры одинаковы.</span><span class="sxs-lookup"><span data-stu-id="678f6-110">The options are all the same.</span></span> <span data-ttu-id="678f6-111">Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="678f6-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="678f6-112">Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="678f6-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="678f6-113">Обычно для сборки проектов используется `dotnet build`, но `dotnet msbuild` дает больше возможностей управления.</span><span class="sxs-lookup"><span data-stu-id="678f6-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="678f6-114">Например, если вам нужно выполнить конкретный целевой объект (без выполнения целевого объекта сборки), возможно, потребуется использовать `dotnet msbuild`.</span><span class="sxs-lookup"><span data-stu-id="678f6-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="678f6-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="678f6-115">Examples</span></span>

* <span data-ttu-id="678f6-116">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="678f6-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="678f6-117">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="678f6-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="678f6-118">Запустите цель публикации и публикацию для RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="678f6-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="678f6-119">Весь проект со всеми целевыми объектами, включенными в пакет SDK:</span><span class="sxs-lookup"><span data-stu-id="678f6-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -pp
  ```
